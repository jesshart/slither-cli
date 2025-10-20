# slither-cli

A Python CLI tool for displaying directory structure as ASCII art trees in your terminal.

## Quick Start

Run instantly without installation using [uvx](https://docs.astral.sh/uv/):

```bash
# Display current directory
uvx --from slither-cli slither

# Display specific directory
uvx --from slither-cli slither /path/to/dir

# Show help
uvx --from slither-cli slither --help
```

## Features

- Display directory trees with beautiful ASCII art formatting
- Customizable depth limiting
- Pattern-based file filtering (include/exclude)
- Show/hide hidden files
- Display file sizes in bytes or human-readable format
- Reverse sort order
- Directories-only mode

## Installation

### Run without installing (recommended)

Use [uvx](https://docs.astral.sh/uv/) to run slither-cli without installation:

```bash
uvx --from slither-cli slither
```

### Install with pip

```bash
pip install slither-cli
slither
```

### Install with uv

```bash
uv pip install slither-cli
slither
```

### Install from source

```bash
git clone https://github.com/jesshart/slither-cli.git
cd slither-cli
uv sync
uv run slither
```

## Usage Examples

### Using uvx (no installation required)

```bash
# Display current directory
uvx --from slither-cli slither

# Display specific directory
uvx --from slither-cli slither /path/to/dir

# Limit depth to 2 levels
uvx --from slither-cli slither -L 2

# Show hidden files
uvx --from slither-cli slither -a

# Show directories only
uvx --from slither-cli slither -d

# Show only Python files
uvx --from slither-cli slither -P "*.py"

# Ignore compiled Python files
uvx --from slither-cli slither -I "*.pyc"

# Show file sizes in human-readable format
uvx --from slither-cli slither -s -h

# Reverse sort order
uvx --from slither-cli slither -r

# Combine multiple options
uvx --from slither-cli slither -L 3 -a -P "*.py" -s -h
```

### Using installed command

If you installed with pip or uv, simply use `slither`:

```bash
slither
slither /path/to/dir
slither -L 2 -a -s -h
```

## All Available Options

| Option | Long form | Description |
|--------|-----------|-------------|
| `-L` | `--level` | Max display depth of the directory tree |
| `-a` | `--all` | Print all files, including hidden files |
| `-d` | `--dirs-only` | List directories only |
| `-P` | `--pattern` | List only files that match the pattern (wildcard) |
| `-I` | `--ignore` | Do not list files that match the pattern |
| `-s` | `--size` | Print file sizes in bytes |
| `-h` | `--human` | Print file sizes in human-readable format |
| `-r` | `--reverse` | Sort output in reverse order |

## Example Output

```
/Users/jesse/Repos/personal/slither-cli
├── slither
│   ├── __init__.py
│   ├── cli.py
│   └── tree.py
├── main.py
├── pyproject.toml
├── README.md
└── uv.lock

1 directory, 6 files
```

## Development

### Project structure

```
slither-cli/
├── slither/           # Main package
│   ├── __init__.py   # Package initialization
│   ├── cli.py        # Typer-based CLI interface
│   └── tree.py       # Core tree building and rendering logic
├── main.py           # Alternative entry point
├── pyproject.toml    # Project configuration
└── uv.lock           # Dependency lock file
```

### Built with

- [Typer](https://typer.tiangolo.com/) - CLI framework
- [Rich](https://rich.readthedocs.io/) - Terminal formatting

## License

This project is open source and available under the MIT License.

## Author

Created by Jesse Hart
