---
name: json-formatter
description: Format, validate, and work with JSON files. Use when working with JSON data that needs formatting, validation, or structure analysis. Handles malformed JSON, provides clear error messages, and supports common JSON operations like pretty-printing and schema validation.
---

# JSON Formatter

Format and validate JSON files with consistent styling and error detection.

## Quick Start

Use the bundled `format_json.py` script for reliable JSON formatting:

```bash
python scripts/format_json.py <input_file> [output_file] [indent]
```

**Parameters:**
- `input_file`: Path to JSON file to format (required)
- `output_file`: Output path (optional, overwrites input if omitted)
- `indent`: Number of spaces for indentation (optional, default: 2)

**Examples:**
```bash
# Format in place
python scripts/format_json.py data.json

# Format to new file
python scripts/format_json.py data.json formatted.json

# Format with 4-space indentation
python scripts/format_json.py data.json data_formatted.json 4
```

## Common Tasks

### Validate JSON Syntax
Run the format script - it will exit with error if JSON is invalid and display the specific error location.

### Fix Malformed JSON
Common issues and fixes:
- **Trailing commas**: Remove last comma in arrays/objects
- **Single quotes**: Replace with double quotes
- **Unquoted keys**: Add quotes around object keys
- **Missing commas**: Add between array/object elements

### Work with Large Files
For files >10MB, consider streaming approaches or the `jq` command-line tool.

## Schema Validation

For JSON schema validation patterns, see [references/common-schemas.md](references/common-schemas.md) which contains:
- Common validation patterns (email, URL, UUID, dates)
- Configuration file structures (package.json, tsconfig.json)
- Schema definition examples

## Error Handling

The script provides clear error messages:
- `Invalid JSON`: Shows line and column of syntax error
- `File not found`: Verifies file path exists
- Returns exit code 1 on any error for CI/CD integration
