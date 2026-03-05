# Hebrew RTL Skill

A Claude Code skill for generating correctly formatted Hebrew (RTL) documents across multiple output formats.

## What It Does

This skill ensures proper right-to-left layout, Hebrew-compatible fonts, correct punctuation, and proper formatting whenever Claude Code produces Hebrew content. It covers:

- **Word (.docx)** - XML injection into Hebrew Word templates with correct `<w:bidi/>` and `<w:rtl/>` patterns
- **PowerPoint (.pptx)** - RTL text boxes, bullet fixes, and post-processing for correct column/timeline ordering
- **HTML / PDF** - Proper `dir="rtl"` markup with Heebo font and RTL table/list styling

## Key Features

- Automatic RTL direction and right-alignment for all Hebrew text
- Correct BiDi handling for mixed Hebrew-English content
- Tables, grids, and timelines ordered right-to-left (first item on the right)
- Hebrew-compatible fonts (Arial for Office formats, Heebo for web)
- Proper punctuation rules (hyphens only, no em/en dashes)
- Date formatting in Israeli conventions (`DD.MM.YYYY`)

## Installation

Copy `SKILL.md` into your Claude Code skills directory, or add this repository as a skill source.

## Usage

The skill activates automatically when:
- The user writes a request in Hebrew
- The user asks for content "בעברית" (in Hebrew)
- The user requests a Hebrew document, report, presentation, summary, or letter

No manual activation is needed - Claude Code will apply the correct RTL formatting rules for the target output format.

## Formats Reference

| Format | Font | RTL Method |
|--------|------|------------|
| .docx | Arial | XML `<w:bidi/>` + `<w:rtl/>` via template injection |
| .pptx | Arial | `rtlMode: true` + Python post-processing |
| HTML/PDF | Heebo | `dir="rtl"` + CSS `direction: rtl` |

## License

MIT
