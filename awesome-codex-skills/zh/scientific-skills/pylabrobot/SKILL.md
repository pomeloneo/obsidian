---
name: pylabrobot
description: Vendor-agnostic lab automation framework。当控制多种 equipment types（Hamilton、Tecan、Opentrons、plate readers、pumps）或需要跨不同 vendors 的 unified programming 时使用。最适合 complex workflows、multi-vendor setups、simulation。对于只使用 official API 的 Opentrons-only protocols，opentrons-integration 可能更简单。
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# PyLabRobot

## 概览

PyLabRobot 是面向 automated and autonomous laboratories 的 hardware-agnostic、pure Python Software Development Kit。使用此 skill，通过跨平台（Windows、macOS、Linux）统一 Python interface 控制 liquid handling robots、plate readers、pumps、heater shakers、incubators、centrifuges 和其他 laboratory automation equipment。

## 何时使用此 Skill

在以下场景使用此 skill：
- Programming liquid handling robots（Hamilton STAR/STARlet、Opentrons OT-2、Tecan EVO）
- 自动化涉及 pipetting、sample preparation 或 analytical measurements 的 laboratory workflows
- 管理 deck layouts 和 laboratory resources（plates、tips、containers、troughs）
- 集成多个 lab devices（liquid handlers、plate readers、heater shakers、pumps）
- 创建带 state management 的 reproducible laboratory protocols
- 在 physical hardware 上运行前模拟 protocols
- 使用 BMG CLARIOstar 或其他 supported plate readers 读取 plates
- 控制 temperature、shaking、centrifugation 或其他 material handling operations
- 在 Python 中进行 laboratory automation

## 核心能力

PyLabRobot 通过六个主要能力领域提供全面 laboratory automation，每个领域都在 references/ directory 中详细说明：

### 1. Liquid Handling (`references/liquid-handling.md`)

控制 liquid handling robots 进行 aspirating、dispensing 和 transferring liquids。关键 operations 包括：
- **Basic Operations**：在 wells 之间 aspirate、dispense、transfer liquids
- **Tip Management**：自动 pick up、drop 和 track pipette tips
- **Advanced Techniques**：Multi-channel pipetting、serial dilutions、plate replication
- **Volume Tracking**：自动跟踪 wells 中的 liquid volumes
- **Hardware Support**：Hamilton STAR/STARlet、Opentrons OT-2、Tecan EVO 等

### 2. Resource Management (`references/resources.md`)

在 hierarchical system 中管理 laboratory resources：
- **Resource Types**：Plates、tip racks、troughs、tubes、carriers 和 custom labware
- **Deck Layout**：用 coordinate systems 将 resources 分配到 deck positions
- **State Management**：跟踪 tip presence、liquid volumes 和 resource states
- **Serialization**：从 JSON files 保存和加载 deck layouts 与 states
- **Resource Discovery**：通过直观 APIs 访问 wells、tips 和 containers

### 3. Hardware Backends (`references/hardware-backends.md`)

通过 backend abstraction 连接多种 laboratory equipment：
- **Liquid Handlers**：Hamilton STAR（full support）、Opentrons OT-2、Tecan EVO
- **Simulation**：ChatterboxBackend 用于无 hardware 的 protocol testing
- **Platform Support**：适用于 Windows、macOS、Linux 和 Raspberry Pi
- **Backend Switching**：通过替换 backend 更换 robots，无需重写 protocols

### 4. Analytical Equipment (`references/analytical-equipment.md`)

集成 plate readers 和 analytical instruments：
- **Plate Readers**：BMG CLARIOstar，用于 absorbance、luminescence、fluorescence
- **Scales**：Mettler Toledo integration，用于 mass measurements
- **Integration Patterns**：将 liquid handlers 与 analytical equipment 结合
- **Automated Workflows**：在 devices 之间自动移动 plates

### 5. Material Handling (`references/material-handling.md`)

控制 environmental 和 material handling equipment：
- **Heater Shakers**：Hamilton HeaterShaker、Inheco ThermoShake
- **Incubators**：带 temperature control 的 Inheco 和 Thermo Fisher incubators
- **Centrifuges**：带 bucket positioning 和 spin control 的 Agilent VSpin
- **Pumps**：用于 fluid pumping operations 的 Cole Parmer Masterflex
- **Temperature Control**：在 protocols 中设置和监控 temperatures

### 6. Visualization 与 Simulation (`references/visualization.md`)

可视化并模拟 laboratory protocols：
- **Browser Visualizer**：deck state 的 real-time 3D visualization
- **Simulation Mode**：无 physical hardware 测试 protocols
- **State Tracking**：可视化监控 tip presence 和 liquid volumes
- **Deck Editor**：用于设计 deck layouts 的 graphical tool
- **Protocol Validation**：在 hardware 上运行前验证 protocols

## 快速开始

要开始使用 PyLabRobot，请安装 package 并初始化 liquid handler：

```python
# Install PyLabRobot
# uv pip install pylabrobot

# Basic liquid handling setup
from pylabrobot.liquid_handling import LiquidHandler
from pylabrobot.liquid_handling.backends import STAR
from pylabrobot.resources import STARLetDeck

# Initialize liquid handler
lh = LiquidHandler(backend=STAR(), deck=STARLetDeck())
await lh.setup()

# Basic operations
await lh.pick_up_tips(tip_rack["A1:H1"])
await lh.aspirate(plate["A1"], vols=100)
await lh.dispense(plate["A2"], vols=100)
await lh.drop_tips()
```

## 使用 References

此 skill 将详细信息组织在多个 reference files 中。在以下情况下加载相关 reference：
- **Liquid Handling**：编写 pipetting protocols、tip management、transfers
- **Resources**：定义 deck layouts、管理 plates/tips、custom labware
- **Hardware Backends**：连接特定 robots、切换 platforms
- **Analytical Equipment**：集成 plate readers、scales 或 analytical devices
- **Material Handling**：使用 heater shakers、incubators、centrifuges、pumps
- **Visualization**：模拟 protocols、可视化 deck states

所有 reference files 位于 `references/` directory，包含 comprehensive examples、API usage patterns 和 best practices。

## Best Practices

使用 PyLabRobot 创建 laboratory automation protocols 时：

1. **Start with Simulation**：在 hardware 上运行前，用 ChatterboxBackend 和 visualizer 测试 protocols
2. **Enable Tracking**：启用 tip tracking 和 volume tracking，以获得准确 state management
3. **Resource Naming**：为所有 resources（plates、tip racks、containers）使用清晰、描述性名称
4. **State Serialization**：将 deck layouts 和 states 保存为 JSON，便于 reproducibility
5. **Error Handling**：为 hardware operations 实现适当 async error handling
6. **Temperature Control**：尽早设置 temperatures，因为 heating/cooling 需要时间
7. **Modular Protocols**：将 complex workflows 拆分为 reusable functions
8. **Documentation**：参考官方文档 https://docs.pylabrobot.org 获取最新 features

## 常见 Workflows

### Liquid Transfer Protocol

```python
# Setup
lh = LiquidHandler(backend=STAR(), deck=STARLetDeck())
await lh.setup()

# Define resources
tip_rack = TIP_CAR_480_A00(name="tip_rack")
source_plate = Cos_96_DW_1mL(name="source")
dest_plate = Cos_96_DW_1mL(name="dest")

lh.deck.assign_child_resource(tip_rack, rails=1)
lh.deck.assign_child_resource(source_plate, rails=10)
lh.deck.assign_child_resource(dest_plate, rails=15)

# Transfer protocol
await lh.pick_up_tips(tip_rack["A1:H1"])
await lh.transfer(source_plate["A1:H12"], dest_plate["A1:H12"], vols=100)
await lh.drop_tips()
```

### Plate Reading Workflow

```python
# Setup plate reader
from pylabrobot.plate_reading import PlateReader
from pylabrobot.plate_reading.clario_star_backend import CLARIOstarBackend

pr = PlateReader(name="CLARIOstar", backend=CLARIOstarBackend())
await pr.setup()

# Set temperature and read
await pr.set_temperature(37)
await pr.open()
# (manually or robotically load plate)
await pr.close()
data = await pr.read_absorbance(wavelength=450)
```

## 其他资源

- **Official Documentation**：https://docs.pylabrobot.org
- **GitHub Repository**：https://github.com/PyLabRobot/pylabrobot
- **Community Forum**：https://discuss.pylabrobot.org
- **PyPI Package**：https://pypi.org/project/PyLabRobot/

如需特定 capabilities 的详细用法，请参考 `references/` directory 中对应的 reference file。
