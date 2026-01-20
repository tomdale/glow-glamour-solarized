# Solarized Theme for Glow

Beautiful Solarized Dark and Light themes for [glow](https://github.com/charmbracelet/glow) and [glamour](https://github.com/charmbracelet/glamour), the markdown renderer.

![Screenshot showing Solarized theme in action](screenshot.png)

## Features

- Faithful implementation of the [Solarized](https://ethanschoonover.com/solarized/) color palette
- Syntax highlighting for code blocks using Solarized colors
- Support for tables, lists, and quotes
- Available in both Dark and Light variants
- Works with glow CLI and any glamour-based tool

## Installation

1. Download the theme file:
   - [solarized-dark.json](solarized-dark.json) for Solarized Dark
   - [solarized-light.json](solarized-light.json) for Solarized Light

2. Place it in your preferred location (e.g., `~/.config/glow/`)

3. Use with glow:
   ```bash
   glow -s ./solarized-dark.json README.md
   ```

## Usage

### CLI Usage

Render markdown files with the Solarized theme:

```bash
# Use Solarized Dark theme
glow -s ./solarized-dark.json document.md

# Use Solarized Light theme
glow -s ./solarized-light.json document.md

# Read from stdin
cat README.md | glow -s ./solarized-dark.json -
```

### Programmatic Usage

Use the theme in your Go applications with glamour:

```go
import (
    "fmt"
    "os"

    "github.com/charmbracelet/glamour"
)

func main() {
    // Load the theme file
    themeData, err := os.ReadFile("solarized-dark.json")
    if err != nil {
        panic(err)
    }

    // Create renderer with custom theme
    r, err := glamour.NewTermRenderer(
        glamour.WithStylesFromJSONBytes(themeData),
    )
    if err != nil {
        panic(err)
    }

    // Render markdown
    markdown := "# Hello, Solarized!\n\nThis is **beautiful** markdown."
    out, err := r.Render(markdown)
    if err != nil {
        panic(err)
    }

    fmt.Print(out)
}
```

### JavaScript/TypeScript Usage

For Node.js applications using glamour wrappers:

```javascript
const { ThemeManager } = require('glamour');
const fs = require('fs');

const themeData = fs.readFileSync('./solarized-dark.json', 'utf8');
const theme = JSON.parse(themeData);

const manager = new ThemeManager({
  customThemes: { 'solarized-dark': theme }
});

manager.apply('solarized-dark');
```

## Color Palette

This theme uses the official [Solarized color palette](https://ethanschoonover.com/solarized/) designed by Ethan Schoonover. The palette is designed to reduce eye strain and improve readability in both light and dark environments.

### Solarized Colors

| Color Name | Hex       | Usage                          |
|-----------|-----------|--------------------------------|
| base03    | `#002b36` | Background (dark)              |
| base02    | `#073642` | Background highlights (dark)   |
| base01    | `#586e75` | Comments                       |
| base00    | `#657b83` | Body text (light)              |
| base0     | `#839496` | Body text (dark)               |
| base1     | `#93a1a1` | Optional emphasized content    |
| base2     | `#eee8d5` | Background highlights (light)  |
| base3     | `#fdf6e3` | Background (light)             |
| yellow    | `#b58900` | Emphasis, types                |
| orange    | `#cb4b16` | Strong emphasis, exceptions    |
| red       | `#dc322f` | Errors, deletions              |
| magenta   | `#d33682` | Link text                      |
| violet    | `#6c71c4` | Subheadings                    |
| blue      | `#268bd2` | Headings, functions, names     |
| cyan      | `#2aa198` | Links, literals, constants     |
| green     | `#859900` | Keywords, insertions           |

For more information, visit the [Solarized project homepage](https://ethanschoonover.com/solarized/).

## Compatibility

These themes work with:

- **glow** (CLI markdown reader) - version 1.0.0 and later
- **glamour** (Go markdown rendering library) - version 0.2.0 and later
- Any application that uses glamour for markdown rendering

## Supported Elements

| Element      | Support | Notes                          |
|--------------|---------|--------------------------------|
| Headings     | Yes     | H1-H6 with blue styling        |
| Code blocks  | Yes     | Full syntax highlighting       |
| Inline code  | Yes     | Green color                    |
| Links        | Yes     | Cyan with underline            |
| Lists        | Yes     | Ordered & unordered            |
| Tables       | Yes     | Standard formatting            |
| Quotes       | Yes     | Italic with indent             |
| Tasks        | Yes     | Checkboxes for TODO items      |

## Credits

- **Solarized color palette** by [Ethan Schoonover](https://ethanschoonover.com/solarized/)
- **glow** by [Charmbracelet](https://github.com/charmbracelet/glow)
- **glamour** by [Charmbracelet](https://github.com/charmbracelet/glamour)

## License

MIT License

Copyright (c) 2026

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

---

The Solarized color palette is designed to reduce eye strain and improve readability in both light and dark environments.

For more information, visit the [Solarized project homepage](https://ethanschoonover.com/solarized/).
