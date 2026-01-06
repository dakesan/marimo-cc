---
name: marimo-inspect
description: |
  This skill should be used when inspecting marimo notebook execution results.

  Triggers include:
  - Checking notebook output
  - Viewing execution results
  - Reading __marimo__ HTML snapshots
  - Debugging notebook errors
  - Verifying cell outputs
---

# Marimo Notebook Inspector

Inspect marimo notebook execution results by reading HTML snapshots stored in the `__marimo__` directory.

## Purpose

Marimo automatically saves HTML snapshots during editing sessions. This skill reads those snapshots to verify:

- Cell execution outputs
- Error messages and tracebacks
- Visualization renders
- UI element states

## Snapshot Location

HTML snapshots are stored in:

- `__marimo__/` directory (relative to notebook)
- `.marimo/` directory (alternative location)

## Workflow

1. Locate the `__marimo__` or `.marimo/` directory using Glob
2. List available HTML snapshots
3. Read the HTML file with the Read tool
4. Parse and analyze:
   - Cell outputs (text, tables, plots)
   - Error states and messages
   - Console output
5. Report findings to user

## Usage Pattern

```
# Find snapshots
Glob: **/__marimo__/*.html

# Read snapshot
Read: __marimo__/notebook_name.html
```

## Analysis Focus

When inspecting HTML snapshots:

- Look for `<div class="output">` sections for cell outputs
- Check for error indicators and stack traces
- Identify visualization elements (plots, charts)
- Note any warning or info messages
