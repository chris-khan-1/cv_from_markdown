# Generate a Professional CV from Markdown

[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit)](https://github.com/pre-commit/pre-commit)
[![pre-commit.ci status](https://results.pre-commit.ci/badge/github/pre-commit/pre-commit/main.svg)](https://results.pre-commit.ci/latest/github/pre-commit/pre-commit/main)

Generate a professional CV from Markdown using Pandoc and LaTeX.

## Getting Started

1. **Update your profile:**
   Edit [`USER_PROFILE`](USER_PROFILE) with your personal details.

2. **Install dependencies:**
   See platform-specific instructions below.

## Pre-commit Hooks (Optional)

If you have Python 3.7+, you can enable pre-commit hooks for code quality:

```bash
pip install --requirement requirements.txt
pre-commit install
pre-commit run --all-files
```

## Windows Setup

1. [Download Pandoc](https://github.com/jgm/pandoc/releases).
2. [Install MikTeX](https://miktex.org/download) and required packages.
3. Run the conversion script:

   ```bash
   ./to_pdf
   ```

   (Use a Bash terminal such as Git Bash.)

## WSL2 / Ubuntu Setup

Follow these steps to set up the required tools for generating your CV on WSL2 or Ubuntu.

### 1. Install Pandoc

Download and install Pandoc:

```bash
wget https://github.com/jgm/pandoc/releases/download/3.6.4/pandoc-3.6.4-1-amd64.deb
sudo dpkg -i pandoc-3.6.4-1-amd64.deb
pandoc -v
```

### 2. Install MikTeX

Add the MikTeX repository and install MikTeX:

```bash
curl -fsSL https://miktex.org/download/key | sudo gpg --dearmor -o /usr/share/keyrings/miktex.gpg
echo "deb [signed-by=/usr/share/keyrings/miktex.gpg] https://miktex.org/download/ubuntu jammy universe" | sudo tee /etc/apt/sources.list.d/miktex.list
sudo apt-get update
sudo apt-get install miktex
miktexsetup finish
```

Refer to the [official MikTeX instructions](https://miktex.org/download) for more details.

### 3. Install XeLaTeX

Install XeLaTeX for PDF generation:

```bash
sudo apt install texlive-xetex
xelatex -v
```

### 4. Install Font Package

Install the recommended font package:

```bash
sudo apt-get install fonts-crosextra-carlito
```

**Note:** Calibri is not available on Ubuntu. The recommended alternative is the `Carlito` font.
Update the `mainfont` setting in the [`to_pdf`](./scripts/to_pdf) script to use `Carlito`.

### Run Conversion Script

```bash
sudo bash ./to_pdf
```

(Must be run as administrator.)

## Troubleshooting

- If you encounter missing LaTeX packages, install them via MikTeX or TeX Live.
- For font issues, ensure the required fonts are installed.
