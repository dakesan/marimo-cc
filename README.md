# marimo-cc

Marimo reactive notebook integration for Claude Code

## Overview

This plugin provides a specialized skill for creating and editing marimo reactive notebooks with Claude Code. It helps you build efficient data science and analytics workflows using marimo's reactive programming model.

**Note:** Most of the prompts and instructions used in this skill are transplanted from the original [marimo](https://github.com/marimo-team/marimo) prompts. This project inherits the Apache 2.0 License from marimo.

## Features

- Create new marimo notebooks
- Convert Jupyter notebooks to marimo
- Implement reactive patterns and UI components
- Build interactive data visualizations
- Generate code following marimo best practices

## Installation

### Install from GitHub

```bash
# Install the plugin with Claude Code
claude plugin install https://github.com/dakesan/marimo-cc
```

### Install from local directory

```bash
# Clone the repository
git clone https://github.com/dakesan/marimo-cc.git

# Install as a local plugin
claude plugin install ./marimo-cc
```

## Usage

After installation, the skill will automatically activate when you make requests like:

- "Create a marimo notebook"
- "Convert this Jupyter notebook to marimo"
- "Build an interactive visualization with marimo"
- "Add a slider to make this parameter adjustable with marimo"

## Examples

### Basic Usage

```
User: "Create a marimo notebook to visualize the iris dataset"

Claude: I'll use the marimo-editor skill to create an interactive visualization notebook...
```

### Reactive UI Example

```python
# Cell 1: Import libraries
import marimo as mo
import matplotlib.pyplot as plt
import numpy as np

# Cell 2: Create UI element
n_points = mo.ui.slider(10, 100, value=50, label="Number of points")
n_points

# Cell 3: Reactive visualization
x = np.random.rand(n_points.value)
y = np.random.rand(n_points.value)
plt.scatter(x, y)
plt.gca()
```

## Skill Details

### marimo-editor

Supports creating and editing marimo reactive notebooks.

**Key capabilities:**
- Understanding marimo's reactive programming model
- Proper use of UI elements
- Data handling best practices
- Integration with visualization libraries (matplotlib, plotly, altair)
- SQL (DuckDB) support

## Requirements

- [marimo](https://marimo.io/) must be installed

```bash
pip install marimo
# or
uv pip install marimo
```

## Contributing

Pull requests and issues are welcome!

## License

Apache License 2.0

This project is derived from [marimo](https://github.com/marimo-team/marimo) and inherits its Apache 2.0 License. Most of the prompts and instructions are transplanted from the original marimo project.

See [LICENSE](LICENSE) for details.

## Author

Hiroyuki Odake ([@dakesan](https://github.com/dakesan))

## Links

- [marimo Official Site](https://marimo.io/)
- [marimo Documentation](https://docs.marimo.io/)
- [marimo GitHub](https://github.com/marimo-team/marimo)
- [This Plugin Repository](https://github.com/dakesan/marimo-cc)

## Acknowledgments

Special thanks to the [marimo team](https://github.com/marimo-team) for creating marimo and providing the original prompts and instructions that this skill is based on.
