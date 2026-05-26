---
name: invoice-organizer
description: 通过读取混乱文件、提取关键信息、统一重命名并整理到逻辑 folders，自动整理 invoices 和 receipts 以便报税准备。将数小时手动记账工作压缩为几分钟自动整理。
---

# 发票整理器

此 skill 将混乱的 invoices、receipts 和 financial documents 文件夹转换为清晰、tax-ready 的归档系统，无需手动操作。

## 何时使用此 Skill

- 为 tax season 做准备，需要有序记录
- 管理来自多个 vendors 的 business expenses
- 整理混乱 folder 或 email downloads 中的 receipts
- 为持续 bookkeeping 建立自动 invoice filing
- 按年份或 category 归档 financial records
- 为 reimbursement 对账 expenses
- 为 accountants 准备 documentation

## 此 Skill 做什么

1. **读取 Invoice 内容**：从 PDFs、images 和 documents 中提取信息：
   - Vendor/company name
   - Invoice number
   - Date
   - Amount
   - Product or service description
   - Payment method

2. **统一重命名 Files**：创建标准化 filenames：
   - 格式：`YYYY-MM-DD Vendor - Invoice - ProductOrService.pdf`
   - 示例：`2024-03-15 Adobe - Invoice - Creative Cloud.pdf`

3. **按 Category 整理**：整理到逻辑 folders：
   - 按 vendor
   - 按 expense category（software、office、travel 等）
   - 按 time period（year、quarter、month）
   - 按 tax category（deductible、personal 等）

4. **处理多种格式**：适用于：
   - PDF invoices
   - 扫描 receipts（JPG、PNG）
   - Email attachments
   - Screenshots
   - Bank statements

5. **保留原件**：在整理 copies 的同时保留 original files

## 如何使用

### 基础用法

导航到混乱的 invoice folder：
```
cd ~/Desktop/receipts-to-sort
```

然后询问 Codex：
```
Organize these invoices for taxes
```

或者更具体地说：
```
Read all invoices in this folder, rename them to 
"YYYY-MM-DD Vendor - Invoice - Product.pdf" format, 
and organize them by vendor
```

### 高级整理

```
Organize these invoices:
1. Extract date, vendor, and description from each file
2. Rename to standard format
3. Sort into folders by expense category (Software, Office, Travel, etc.)
4. Create a CSV spreadsheet with all invoice details for my accountant
```

## 指令

当用户请求 invoice organization 时：

1. **扫描 Folder**
   
   识别所有 invoice files：
   ```bash
   # Find all invoice-related files
   find . -type f \( -name "*.pdf" -o -name "*.jpg" -o -name "*.png" \) -print
   ```
   
   报告发现：
   - 文件总数
   - File types
   - Date range（如果可从名称判断）
   - 当前 organization（或缺乏组织）

2. **从每个 File 提取信息**
   
   对每张 invoice，提取：
   
   **从 PDF invoices**：
   - 使用 text extraction 读取 invoice content
   - 查找常见 patterns：
     - "Invoice Date:", "Date:", "Issued:"
     - "Invoice #:", "Invoice Number:"
     - Company name（通常在顶部）
     - "Amount Due:", "Total:", "Amount:"
     - "Description:", "Service:", "Product:"
   
   **从 image receipts**：
   - 读取图片中可见文字
   - 识别 vendor name（通常在顶部）
   - 查找 date（常见格式）
   - 找到 total amount
   
   **不清晰文件的 fallback**：
   - 使用 filename clues
   - 检查 file creation/modification date
   - 如果 critical info 缺失，标记为 manual review

3. **确定整理策略**
   
   如果未指定，询问用户偏好：
   
   ```markdown
   I found [X] invoices from [date range].
   
   How would you like them organized?
   
   1. **By Vendor** (Adobe/, Amazon/, Stripe/, etc.)
   2. **By Category** (Software/, Office Supplies/, Travel/, etc.)
   3. **By Date** (2024/Q1/, 2024/Q2/, etc.)
   4. **By Tax Category** (Deductible/, Personal/, etc.)
   5. **Custom** (describe your structure)
   
   Or I can use a default structure: Year/Category/Vendor
   ```

4. **创建标准化 Filename**
   
   对每张 invoice，按以下 pattern 创建 filename：
   
   ```
   YYYY-MM-DD Vendor - Invoice - Description.ext
   ```
   
   示例：
   - `2024-03-15 Adobe - Invoice - Creative Cloud.pdf`
   - `2024-01-10 Amazon - Receipt - Office Supplies.pdf`
   - `2023-12-01 Stripe - Invoice - Monthly Payment Processing.pdf`
   
   **Filename 最佳实践**：
   - 移除特殊字符，hyphens 除外
   - 正确大写 vendor names
   - 描述保持简洁但有意义
   - 使用一致的 date format（YYYY-MM-DD）便于排序
   - 保留原始 file extension

5. **执行整理**
   
   移动 files 前先展示计划：
   
   ```markdown
   # Organization Plan
   
   ## Proposed Structure
   ```
   Invoices/
   ├── 2023/
   │   ├── Software/
   │   │   ├── Adobe/
   │   │   └── Microsoft/
   │   ├── Services/
   │   └── Office/
   └── 2024/
       ├── Software/
       ├── Services/
       └── Office/
   ```
   
   ## Sample Changes
   
   Before: `invoice_adobe_march.pdf`
   After: `2024-03-15 Adobe - Invoice - Creative Cloud.pdf`
   Location: `Invoices/2024/Software/Adobe/`
   
   Before: `IMG_2847.jpg`
   After: `2024-02-10 Staples - Receipt - Office Supplies.jpg`
   Location: `Invoices/2024/Office/Staples/`
   
   Process [X] files? (yes/no)
   ```
   
   批准后：
   ```bash
   # Create folder structure
   mkdir -p "Invoices/2024/Software/Adobe"
   
   # Copy (don't move) to preserve originals
   cp "original.pdf" "Invoices/2024/Software/Adobe/2024-03-15 Adobe - Invoice - Creative Cloud.pdf"
   
   # Or move if user prefers
   mv "original.pdf" "new/path/standardized-name.pdf"
   ```

6. **生成摘要报告**
   
   创建包含所有 invoice details 的 CSV file：
   
   ```csv
   Date,Vendor,Invoice Number,Description,Amount,Category,File Path
   2024-03-15,Adobe,INV-12345,Creative Cloud,52.99,Software,Invoices/2024/Software/Adobe/2024-03-15 Adobe - Invoice - Creative Cloud.pdf
   2024-03-10,Amazon,123-4567890-1234567,Office Supplies,127.45,Office,Invoices/2024/Office/Amazon/2024-03-10 Amazon - Receipt - Office Supplies.pdf
   ...
   ```
   
   此 CSV 适用于：
   - 导入 accounting software
   - 与 accountants 分享
   - Expense tracking and reporting
   - Tax preparation

7. **提供完成摘要**
   
   ```markdown
   # Organization Complete! 📊
   
   ## Summary
   - **Processed**: [X] invoices
   - **Date range**: [earliest] to [latest]
   - **Total amount**: $[sum] (if amounts extracted)
   - **Vendors**: [Y] unique vendors
   
   ## New Structure
   ```
   Invoices/
   ├── 2024/ (45 files)
   │   ├── Software/ (23 files)
   │   ├── Services/ (12 files)
   │   └── Office/ (10 files)
   └── 2023/ (12 files)
   ```
   
   ## Files Created
   - `/Invoices/` - Organized invoices
   - `/Invoices/invoice-summary.csv` - Spreadsheet for accounting
   - `/Invoices/originals/` - Original files (if copied)
   
   ## Files Needing Review
   [List any files where information couldn't be extracted completely]
   
   ## Next Steps
   1. Review the `invoice-summary.csv` file
   2. Check files in "Needs Review" folder
   3. Import CSV into your accounting software
   4. Set up auto-organization for future invoices
   
   Ready for tax season! 🎉
   ```

## 示例

### 示例 1：Tax Preparation（来自 Martin Merschroth）

**User**: "I have a messy folder of invoices for taxes. Sort them and rename properly."

**Process**:
1. 扫描 folder：找到 147 个 PDFs 和 images
2. 读取每张 invoice 来提取：
   - Date
   - Vendor name
   - Invoice number
   - Product/service description
3. 将所有 files 重命名为：`YYYY-MM-DD Vendor - Invoice - Product.pdf`
4. 整理到：`2024/Software/`、`2024/Travel/` 等
5. 为 accountant 创建 `invoice-summary.csv`
6. 结果：几分钟内得到 tax-ready 的有序 invoices

### 示例 2：Monthly Expense Reconciliation

**User**: "Organize my business receipts from last month by category."

**Output**:
```markdown
# March 2024 Receipts Organized

## By Category
- Software & Tools: $847.32 (12 invoices)
- Office Supplies: $234.18 (8 receipts)
- Travel & Meals: $1,456.90 (15 receipts)
- Professional Services: $2,500.00 (3 invoices)

Total: $5,038.40

All receipts renamed and filed in:
`Business-Receipts/2024/03-March/[Category]/`

CSV export: `march-2024-expenses.csv`
```

### 示例 3：Multi-Year Archive

**User**: "I have 3 years of random invoices. Organize them by year, then by vendor."

**Output**：创建结构：
```
Invoices/
├── 2022/
│   ├── Adobe/
│   ├── Amazon/
│   └── ...
├── 2023/
│   ├── Adobe/
│   ├── Amazon/
│   └── ...
└── 2024/
    ├── Adobe/
    ├── Amazon/
    └── ...
```

每个 file 都按日期和描述正确重命名。

### 示例 4：Email Downloads Cleanup

**User**: "I download invoices from Gmail. They're all named 'invoice.pdf', 'invoice(1).pdf', etc. Fix this mess."

**Output**:
```markdown
Found 89 files all named "invoice*.pdf"

Reading each file to extract real information...

Renamed examples:
- invoice.pdf → 2024-03-15 Shopify - Invoice - Monthly Subscription.pdf
- invoice(1).pdf → 2024-03-14 Google - Invoice - Workspace.pdf
- invoice(2).pdf → 2024-03-10 Netlify - Invoice - Pro Plan.pdf

All files renamed and organized by vendor.
```

## 常见整理模式

### 按 Vendor（简单）
```
Invoices/
├── Adobe/
├── Amazon/
├── Google/
└── Microsoft/
```

### 按 Year 和 Category（Tax-Friendly）
```
Invoices/
├── 2023/
│   ├── Software/
│   ├── Hardware/
│   ├── Services/
│   └── Travel/
└── 2024/
    └── ...
```

### 按 Quarter（详细跟踪）
```
Invoices/
├── 2024/
│   ├── Q1/
│   │   ├── Software/
│   │   ├── Office/
│   │   └── Travel/
│   └── Q2/
│       └── ...
```

### 按 Tax Category（Accountant-Ready）
```
Invoices/
├── Deductible/
│   ├── Software/
│   ├── Office/
│   └── Professional-Services/
├── Partially-Deductible/
│   └── Meals-Travel/
└── Personal/
```

## 自动化设置

用于持续整理：

```
Create a script that watches my ~/Downloads/invoices folder 
and auto-organizes any new invoice files using our standard 
naming and folder structure.
```

这会创建一个持久方案，在 invoices 到达时自动整理。

## Pro Tips

1. **将 emails 扫描为 PDF**：先用 Preview 或类似工具将 email invoices 保存为 PDFs
2. **一致下载位置**：将所有 invoices 保存到一个 folder，便于 batch processing
3. **月度例行流程**：按月整理 invoices，而不是按年
4. **备份原件**：重组前保留 original files
5. **在 CSV 中包含 amounts**：便于 budget tracking
6. **按 deductibility 打标签**：标注哪些 expenses 是 tax-deductible
7. **保留 receipts 7 年**：标准 audit period

## 处理特殊情况

### 缺失信息
如果无法提取 date/vendor：
- 标记 file 供 manual review
- 使用 file modification date 作为 fallback
- 创建 "Needs-Review/" folder

### Duplicate Invoices
如果同一 invoice 出现多次：
- 比较 file hashes
- 保留最高质量版本
- 在 summary 中注明 duplicates

### Multi-Page Invoices
对于拆分到多个 files 的 invoices：
- 必要时 merge PDFs
- 对各部分使用一致命名
- 如果 invoice 被拆分，在 CSV 中注明

### Non-Standard Formats
对于不常见的 receipt formats：
- 尽可能提取信息
- 标准化可标准化的部分
- 如果 critical info 缺失，标记为 review

## 相关用例

- 创建 reimbursement 用 expense reports
- 整理 bank statements
- 管理 vendor contracts
- 归档 old financial records
- 为 audits 做准备
- 长期跟踪 subscription costs
