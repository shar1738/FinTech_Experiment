# Getting Started with a Financial Tech Experimentation

This repository is designed to help anyone get started with analyzing the financial world through programming. Whether you're interested in stock trading, portfolio management, or quantitative analysis, this repo provides tools and templates to explore financial data programmatically.

## Basic Resources

### Python Libraries
- [pandas Documentation](https://pandas.pydata.org/docs/)
- [numpy Documentation](https://numpy.org/doc/)
- [yfinance Documentation](https://pypi.org/project/yfinance/)
- [Matplotlib Documentation](https://matplotlib.org/stable/)

### Help Guides
For help on basic tools, refer to the `Help/` folder:

- `finance_pyton_explanation.md` - Basic overview of how the two can be used together 
- `git_explanation.md` — Git version control
- `bash_explanation.md` — Bash terminal commands 
- `AI_explanation.md` — AI prompting guide

## Prerequisites

### Python

This project requires **Python 3.13 or higher**.

#### Installing Python on Linux (Ubuntu/Debian)

```bash
sudo apt update
sudo apt install python3.13 python3.13-venv python3.13-dev
```

#### Installing Python on macOS

Using Homebrew:
```bash
brew install python@3.13
```

#### Installing Python on Windows

Download from [python.org](https://www.python.org/downloads/) or use winget:
```bash
winget install Python.Python.3.13
```

#### Verify Python Installation

```bash
python3.13 --version
```

### UV (Fast Python Package Manager)

UV is a fast, modern Python package manager written in Rust. Just use it — it's awesome!

#### Installing UV on Linux/macOS

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

Or using pip:
```bash
pip install uv
```

#### Installing UV on Windows

```powershell
powershell -ExecutionPolicy Bypass -Command "irm https://astral.sh/uv/install.ps1 | iex"
```

Or using winget:
```bash
winget install astral-sh.uv
```

#### Verify UV Installation

```bash
uv --version
```

## Setup Instructions

### 1. Clone the Repository

```bash
git clone <repository-url>
cd Quant_Experiment
```

### 2. Set Up Virtual Environment

This project includes a pre-configured `.venv` directory. Follow step 3 for instructions.

### 3. Install Dependencies with UV

This project already has a `.venv` directory with dependencies installed. You can use it directly:

```bash
# Activate the existing virtual environment
source .venv/bin/activate  # Linux/macOS
.venv\Scripts\activate     # Windows
```

If you need to create a new virtual environment:

```bash
# Create a new virtual environment
uv venv

# Activate it
source .venv/bin/activate  # Linux/macOS
.venv\Scripts\activate     # Windows

# Install dependencies
uv sync
```

### 4. Verify Installation

```bash
# Check installed packages
uv pip list

# Or run the main script
python main.py
```

## Running Jupyter Notebooks

This project includes JupyterLab for exploratory analysis:

```bash
# Launch JupyterLab
jupyter lab
```

Then open your browser to `http://localhost:8888`

## Project Structure

```
Quant_Experiment/
├── Data/           # Data files and storage
├── Help/           # Documentation and guides
├── Notebooks/      # Jupyter notebooks for analysis
├── Portfolios/     # Portfolio tracking templates
├── Reports/        # Generated reports
├── main.py         # Main entry point
├── pyproject.toml  # Project dependencies
└── uv.lock        # Locked dependencies
```

## Common Tasks

### Adding New Dependencies

```bash
uv add <package-name>
```

### Updating Dependencies

```bash
uv sync --upgrade
```

### Running Tests (if configured)

```bash
uv run pytest
```

### End Note

All pixels, code and hereby software. At some point, was made by people just like you and me.
