---
name: glycoengineering
description: 分析和工程化 protein glycosylation。扫描 sequences 中的 N-glycosylation sequons（N-X-S/T）、预测 O-glycosylation hotspots，并访问 curated glycoengineering tools（NetOGlyc、GlycoShield、GlycoWorkbench）。用于 glycoprotein engineering、therapeutic antibody optimization 和 vaccine design。
license: Unknown
metadata:
    skill-author: Kuan-lin Huang
---

# Glycoengineering

## 概述

Glycosylation 是最常见且最复杂的 protein post-translational modification (PTM)，影响超过 50% 的人类 proteins。Glycans 调控 protein folding、stability、immune recognition、receptor interactions，以及 therapeutic proteins 的 pharmacokinetics。Glycoengineering 是对 glycosylation patterns 进行理性改造，以提高 therapeutic efficacy、stability 或 immune evasion。

**两种主要 glycosylation 类型：**
- **N-glycosylation**：连接到 sequon N-X-[S/T] 中的 asparagine (N)，其中 X ≠ Proline；发生在 ER/Golgi
- **O-glycosylation**：连接到 serine (S) 或 threonine (T)；没有严格 consensus motif；主要由 GalNAc 起始

## 何时使用此 Skill

以下情况使用此 skill：

- **Antibody engineering**：优化 Fc glycosylation，以增强 ADCC、CDC，或降低 immunogenicity
- **Therapeutic protein design**：识别影响 half-life、stability 或 immunogenicity 的 glycosylation sites
- **Vaccine antigen design**：工程化 glycan shields，将 immune responses 聚焦到 conserved epitopes
- **Biosimilar characterization**：比较 reference 和 biosimilar 的 glycan patterns
- **Drug target analysis**：glycosylation 是否影响 receptor 的 target engagement？
- **Protein stability**：N-glycans 通常稳定 proteins；识别可稳定化的 mutation sites

## N-Glycosylation Sequon Analysis

### 扫描 N-Glycosylation Sites

N-glycosylation 发生在 sequon **N-X-[S/T]**，其中 X ≠ Proline。

```python
import re
from typing import List, Tuple

def find_n_glycosylation_sequons(sequence: str) -> List[dict]:
    """
    Scan a protein sequence for canonical N-linked glycosylation sequons.
    Motif: N-X-[S/T], where X ≠ Proline.

    Args:
        sequence: Single-letter amino acid sequence

    Returns:
        List of dicts with position (1-based), motif, and context
    """
    seq = sequence.upper()
    results = []
    i = 0
    while i <= len(seq) - 3:
        triplet = seq[i:i+3]
        if triplet[0] == 'N' and triplet[1] != 'P' and triplet[2] in {'S', 'T'}:
            context = seq[max(0, i-3):i+6]  # ±3 residue context
            results.append({
                'position': i + 1,   # 1-based
                'motif': triplet,
                'context': context,
                'sequon_type': 'NXS' if triplet[2] == 'S' else 'NXT'
            })
            i += 3
        else:
            i += 1
    return results

def summarize_glycosylation_sites(sequence: str, protein_name: str = "") -> str:
    """Generate a research log summary of N-glycosylation sites."""
    sequons = find_n_glycosylation_sequons(sequence)

    lines = [f"# N-Glycosylation Sequon Analysis: {protein_name or 'Protein'}"]
    lines.append(f"Sequence length: {len(sequence)}")
    lines.append(f"Total N-glycosylation sequons: {len(sequons)}")

    if sequons:
        lines.append(f"\nN-X-S sites: {sum(1 for s in sequons if s['sequon_type'] == 'NXS')}")
        lines.append(f"N-X-T sites: {sum(1 for s in sequons if s['sequon_type'] == 'NXT')}")
        lines.append(f"\nSite details:")
        for s in sequons:
            lines.append(f"  Position {s['position']}: {s['motif']} (context: ...{s['context']}...)")
    else:
        lines.append("No canonical N-glycosylation sequons detected.")

    return "\n".join(lines)

# Example: IgG1 Fc region
fc_sequence = "APELLGGPSVFLFPPKPKDTLMISRTPEVTCVVVDVSHEDPEVKFNWYVDGVEVHNAKTKPREEQYNSTYRVVSVLTVLHQDWLNGKEYKCKVSNKALPAPIEKTISKAKGQPREPQVYTLPPSREEMTKNQVSLTCLVKGFYPSDIAVEWESNGQPENNYKTTPPVLDSDGSFFLYSKLTVDKSRWQQGNVFSCSVMHEALHNHYTQKSLSLSPGK"
print(summarize_glycosylation_sites(fc_sequence, "IgG1 Fc"))
```

### 突变 N-Glycosylation Sites

```python
def eliminate_glycosite(sequence: str, position: int, replacement: str = "Q") -> str:
    """
    Eliminate an N-glycosylation site by substituting Asn → Gln (conservative).

    Args:
        sequence: Protein sequence
        position: 1-based position of the Asn to mutate
        replacement: Amino acid to substitute (default Q = Gln; similar size, not glycosylated)

    Returns:
        Mutated sequence
    """
    seq = list(sequence.upper())
    idx = position - 1
    assert seq[idx] == 'N', f"Position {position} is '{seq[idx]}', not 'N'"
    seq[idx] = replacement.upper()
    return ''.join(seq)

def add_glycosite(sequence: str, position: int, flanking_context: str = "S") -> str:
    """
    Introduce an N-glycosylation site by mutating a residue to Asn,
    and ensuring X ≠ Pro and +2 = S/T.

    Args:
        position: 1-based position to introduce Asn
        flanking_context: 'S' or 'T' at position+2 (if modification needed)
    """
    seq = list(sequence.upper())
    idx = position - 1

    # Mutate to Asn
    seq[idx] = 'N'

    # Ensure X+1 != Pro (mutate to Ala if needed)
    if idx + 1 < len(seq) and seq[idx + 1] == 'P':
        seq[idx + 1] = 'A'

    # Ensure X+2 = S or T
    if idx + 2 < len(seq) and seq[idx + 2] not in ('S', 'T'):
        seq[idx + 2] = flanking_context

    return ''.join(seq)
```

## O-Glycosylation Analysis

### Heuristic O-Glycosylation Hotspot Prediction

```python
def predict_o_glycosylation_hotspots(
    sequence: str,
    window: int = 7,
    min_st_fraction: float = 0.4,
    disallow_proline_next: bool = True
) -> List[dict]:
    """
    Heuristic O-glycosylation hotspot scoring based on local S/T density.
    Not a substitute for NetOGlyc; use as fast baseline.

    Rules:
    - O-GalNAc glycosylation clusters on Ser/Thr-rich segments
    - Flag Ser/Thr residues in windows enriched for S/T
    - Avoid S/T immediately followed by Pro (TP/SP motifs inhibit GalNAc-T)

    Args:
        window: Odd window size for local S/T density
        min_st_fraction: Minimum fraction of S/T in window to flag site
    """
    if window % 2 == 0:
        window = 7
    seq = sequence.upper()
    half = window // 2
    candidates = []

    for i, aa in enumerate(seq):
        if aa not in ('S', 'T'):
            continue
        if disallow_proline_next and i + 1 < len(seq) and seq[i+1] == 'P':
            continue

        start = max(0, i - half)
        end = min(len(seq), i + half + 1)
        segment = seq[start:end]
        st_count = sum(1 for c in segment if c in ('S', 'T'))
        frac = st_count / len(segment)

        if frac >= min_st_fraction:
            candidates.append({
                'position': i + 1,
                'residue': aa,
                'st_fraction': round(frac, 3),
                'window': f"{start+1}-{end}",
                'segment': segment
            })

    return candidates
```

## External Glycoengineering Tools

### 1. NetOGlyc 4.0（O-glycosylation prediction）

用于高精度 O-GalNAc site prediction 的 Web service：
- **URL**: https://services.healthtech.dtu.dk/services/NetOGlyc-4.0/
- **Input**: FASTA protein sequence
- **Output**: Per-residue O-glycosylation probability scores
- **Method**: 在 experimentally verified O-GalNAc sites 上训练的 neural network

```python
import requests

def submit_netoglycv4(fasta_sequence: str) -> str:
    """
    Submit sequence to NetOGlyc 4.0 web service.
    Returns the job URL for result retrieval.

    Note: This uses the DTU Health Tech web service. Results take ~1-5 min.
    """
    url = "https://services.healthtech.dtu.dk/cgi-bin/webface2.cgi"
    # NetOGlyc submission (parameters may vary with web service version)
    # Recommend using the web interface directly for most use cases
    print("Submit sequence at: https://services.healthtech.dtu.dk/services/NetOGlyc-4.0/")
    return url

# Also: NetNGlyc for N-glycosylation prediction
# URL: https://services.healthtech.dtu.dk/services/NetNGlyc-1.0/
```

### 2. GlycoShield-MD（Glycan Shielding Analysis）

GlycoShield-MD 分析 MD simulations 期间 glycans 如何遮蔽 protein surfaces：
- **URL**: https://gitlab.mpcdf.mpg.de/dioscuri-biophysics/glycoshield-md/
- **Use**: 在 MD trajectory 上映射 protein surface 的 glycan shielding
- **Output**: Per-residue shielding fraction、visualization

```bash
# Installation
pip install glycoshield

# Basic usage: analyze glycan shielding from glycosylated protein MD trajectory
glycoshield \
    --topology glycoprotein.pdb \
    --trajectory glycoprotein.xtc \
    --glycan_resnames BGLCNA FUC \
    --output shielding_analysis/
```

### 3. GlycoWorkbench（Glycan Structure Drawing/Analysis）

- **URL**: https://www.eurocarbdb.org/project/glycoworkbench
- **Use**: 绘制 glycan structures、计算 masses、annotate MS spectra
- **Format**: GlycoCT、IUPAC condensed glycan notation

### 4. GlyConnect（Glycan-Protein Database）

- **URL**: https://glyconnect.expasy.org/
- **Use**: 查找 experimentally verified glycoproteins 和 glycosylation sites
- **Query**: 按 protein（UniProt ID）、glycan structure 或 tissue

```python
import requests

def query_glyconnect(uniprot_id: str) -> dict:
    """Query GlyConnect for glycosylation data for a protein."""
    url = f"https://glyconnect.expasy.org/api/proteins/uniprot/{uniprot_id}"
    response = requests.get(url, headers={"Accept": "application/json"})
    if response.status_code == 200:
        return response.json()
    return {}

# Example: query EGFR glycosylation
egfr_glyco = query_glyconnect("P00533")
```

### 5. UniCarbKB（Glycan Structure Database）

- **URL**: https://unicarbkb.org/
- **Use**: Browse glycan structures，按 mass 或 composition search
- **Format**: GlycoCT 或 IUPAC notation

## Key Glycoengineering Strategies

### For Therapeutic Antibodies

| Goal | Strategy | Notes |
|------|----------|-------|
| Enhance ADCC | Fc Asn297 去岩藻糖基化 | Afucosylated IgG1 的 FcγRIIIa binding 约提升 50× |
| Reduce immunogenicity | 移除 non-human glycans | 去除 α-Gal、NGNA epitopes |
| Improve PK half-life | Sialylation | Sialylated glycans 延长 half-life |
| Reduce inflammation | Hypersialylation | IVIG anti-inflammatory mechanism |
| Create glycan shield | 向表面添加 N-glycosites | 遮蔽 vulnerable epitopes（vaccine design） |

### 常用 Mutations

| Mutation | Effect |
|----------|--------|
| N297A/Q (IgG1) | 移除 Fc glycosylation（aglycosyl） |
| N297D (IgG1) | 移除 Fc glycosylation |
| S298A/E333A/K334A | 增强 FcγRIIIa binding |
| F243L (IgG1) | 增强 defucosylation |
| T299A | 移除 Fc glycosylation |

## Glycan Notation

### IUPAC Condensed Notation（Monosaccharide abbreviations）

| Symbol | Full Name | Type |
|--------|-----------|------|
| Glc | Glucose | Hexose |
| GlcNAc | N-Acetylglucosamine | HexNAc |
| Man | Mannose | Hexose |
| Gal | Galactose | Hexose |
| Fuc | Fucose | Deoxyhexose |
| Neu5Ac | N-Acetylneuraminic acid (Sialic acid) | Sialic acid |
| GalNAc | N-Acetylgalactosamine | HexNAc |

### Complex N-Glycan Structure

```
Typical complex biantennary N-glycan:
Neu5Ac-Gal-GlcNAc-Man\
                       Man-GlcNAc-GlcNAc-[Asn]
Neu5Ac-Gal-GlcNAc-Man/
(±Core Fuc at innermost GlcNAc)
```

## 最佳实践

- **先用 NetNGlyc/NetOGlyc** 进行 computational prediction，再做 experimental validation
- **用 mass spectrometry 验证**：Glycoproteomics（Byonic、Mascot）用于 site-specific glycan profiling
- **考虑 site context**：不是所有预测 sequons 都实际 glycosylated（accessibility、cell type、protein conformation）
- **对于 antibodies**：Fc N297 glycan 很关键，始终先 characterize 此位点
- **使用 GlyConnect** 检查目标 protein 是否有 experimentally verified glycosylation data

## 其他资源

- **GlyTouCan** (glycan structure repository): https://glytoucan.org/
- **GlyConnect**: https://glyconnect.expasy.org/
- **CFG Functional Glycomics**: http://www.functionalglycomics.org/
- **DTU Health Tech servers** (NetNGlyc, NetOGlyc): https://services.healthtech.dtu.dk/
- **GlycoWorkbench**: https://glycoworkbench.software.informer.com/
- **Review**: Apweiler R et al. (1999) Biochim Biophys Acta. PMID: 10564035
- **Therapeutic glycoengineering review**: Jefferis R (2009) Nature Reviews Drug Discovery. PMID: 19448661
