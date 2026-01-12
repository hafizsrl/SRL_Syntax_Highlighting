# SRL Syntax Highlighting

A VS Code extension that provides syntax highlighting for SRL (Standard Report Language) files.

## Disclaimer

**This is an independent, community-maintained VS Code extension. It is not affiliated with, endorsed by, or supported by Tribal Group.**

## Author

**hafiz musa** 

## Citation

This extension can be cited as:

> "Custom IDE tooling for enterprise SRL-based systems"
> 
> Aligns perfectly with AI Readiness / Developer Capability
> 
> "Industry-relevant software artefact developed to support HE enterprise systems"

## Features

- Syntax highlighting for SRL variables (`<<...>>`)
- Syntax highlighting for inner SRL variables (`<...>`)
- Syntax highlighting for conditional text (`{{SEL:...}}`)
- Syntax highlighting for lists (`[[...]]`)
- Syntax highlighting for print styles (`<...>`)
- Support for field references, functions, registers, and SLP codes
- Color-coded operators, strings, and comments

## Supported Syntax Elements

### SRL Variables
- Field references: `<<STU_CODE.STU.SRS>>`
- Functions: `<<$date>>`, `<<$$USR_CODE>>`
- Registers: `<<$$USR_CODE>>`
- SLP codes: `<<@SLPCODE>>`
- Text: `<<"Text">>`
- Temp variables: `<<#VAR = Value>>`
- Prompts: `<<'Prompt'"Value">>`
- Format specifiers: `<<FIELD&L10>>`

### Conditional Text
- New style: `{{SEL:(FIELD="value"):Text}{Alternative}}`
- Supports operators: `=`, `!=`, `<`, `<=`, `>`, `>=`
- Supports logical operators: `&` (AND), `|` (OR)
- Supports functions: `$date()`, `$number()`, `$hits()`

### Lists
- Basic list syntax: `[[ENTITY{.DICTIONARY}: ... ]]`
- **Sort (SRT)**: `[[ENTITY:SRT:FIELD1,FIELD2~: ... ]]`
  - Multiple sort fields separated by commas
  - `~` suffix for descending order
- **Total (TOT)**: `[[ENTITY:TOT:MODE&FORMAT: ... ]]`
  - Total modes: `SUM`, `MIN`, `MAX`, `AVERAGE`, `MEDIAN`, `COUNT`, `UNIQUE`, `EXPRESSION`, `COEFFICIENT`, `STANDARD`, `VARIANCE`
  - Optional format specifier after `&`
- **Selection (SEL)**: `[[ENTITY:SEL:(conditions): ... ]]`
  - Supports both new-style (with parentheses) and old-style conditions
  - Multiple conditions with `&` (AND) operator
  - Field comparisons, value comparisons, and wildcards
- **Combined**: Lists can combine SRT, TOT, and SEL in any order

### Inner SRL Variables
- Inner variables: `<FIELD.Entity.Dictionary>`
- Supports all SRL variable features except temp variables

## Installation

### Method 1: Install from Local Folder (Recommended for Development)

1. **Open VS Code**
2. **Open the Command Palette** (`Ctrl+Shift+P` on Windows/Linux, `Cmd+Shift+P` on Mac)
3. **Type**: `Extensions: Install from VSIX...` or `Extensions: Install from Location...`
4. **Navigate to this folder** (`C:\Works\srl`) and select it
5. **Reload VS Code** when prompted
6. Open any `.srl` file to see syntax highlighting

### Method 2: Copy to Extensions Directory

1. **Find your VS Code extensions directory**:
   - Windows: `%USERPROFILE%\.vscode\extensions\`
   - Mac: `~/.vscode/extensions/`
   - Linux: `~/.vscode/extensions/`

2. **Copy this entire folder** (`srl`) to the extensions directory
   - The folder should be named `srl-syntax-1.0.0` or similar
   - Or keep it as `srl` if you prefer

3. **Reload VS Code** (`Ctrl+R` or `Cmd+R`)

4. **Verify installation**: Open Command Palette → `Extensions: Show Installed Extensions` → Search for "SRL Syntax Highlighting"

### Method 3: Package as VSIX (For Distribution)

1. **Install VS Code Extension Manager** (if not already installed):
   ```bash
   npm install -g @vscode/vsce
   ```

2. **Package the extension**:
   ```bash
   cd C:\Works\srl
   vsce package
   ```

3. **Install the VSIX file**:
   - Open VS Code
   - Command Palette → `Extensions: Install from VSIX...`
   - Select the generated `.vsix` file

### Quick Test

After installation, open `sample.srl` in VS Code to verify syntax highlighting is working correctly.

## File Associations

Files with the `.srl` extension are automatically recognized as SRL files.

## Language Features

- Auto-closing pairs for `<<>>`, `{{}}`, `[[]]`, `<>`, `{}`, `[]`, `()`
- Bracket matching
- Word pattern matching for field names
- Comment support (`//` and `/* */`)

## Contributing

Contributions are welcome! Please feel free to submit issues or pull requests.

## License

MIT


