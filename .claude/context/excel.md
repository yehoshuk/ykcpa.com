# Excel Context for Blog Posts

Reference material for writing Excel-related blog posts.

## Target Audience

- Accountants and bookkeepers
- Small business owners managing their own books
- Finance professionals automating workflows
- Excel beginners to intermediate users

## Writing Style

- Practical, solution-focused
- Include screenshots when helpful (save to `src/assets/`)
- Show before/after examples
- Explain the "why" not just the "how"
- Include keyboard shortcuts where applicable

## Common Excel Topics

### Formulas & Functions
- Lookup: VLOOKUP, XLOOKUP, INDEX/MATCH, HLOOKUP
- Aggregation: SUMIF, SUMIFS, COUNTIF, AVERAGEIF
- Text: LEFT, RIGHT, MID, TRIM, CLEAN, TEXT, CONCAT
- Date: EOMONTH, NETWORKDAYS, DATEDIF, TODAY, NOW
- Logic: IF, IFS, SWITCH, AND, OR, NOT
- Error handling: IFERROR, IFNA, ERROR.TYPE

### Data Tools
- Tables (Ctrl+T)
- Power Query
- Pivot Tables
- Data Validation
- Conditional Formatting
- Named Ranges

### Productivity
- Keyboard shortcuts
- Quick Access Toolbar customization
- Custom number formats
- AutoFill and Flash Fill

## Version Notes

- Default to Microsoft 365 / Excel 2021+ features
- Note when features are 365-only (like XLOOKUP, dynamic arrays)
- Mention Excel for Mac differences when relevant

## Common Tags

```yaml
tags:
  - Excel
  - formulas
  - productivity
  - accounting
```

## Formula Formatting

Use code blocks for formulas:
```excel
=XLOOKUP(A2, data[ID], data[Name], "Not Found")
```

## Resources

- [Microsoft Excel Help](https://support.microsoft.com/excel)
- [ExcelJet](https://exceljet.net/)
- [Chandoo](https://chandoo.org/)
