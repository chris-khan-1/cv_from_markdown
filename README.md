# How To Use

## User Information

Update the [`USER_PROFILE`](USER_PROFILE) file with your details.

## Pre Commit

The use of pre-commit is optional.

If you have Python `3.7` or newer, you can run the following commands:

```bash
pip install --requirement requirements.txt
pre-commit install
pre-commit run --all-files
```

## Windows

1. Download `pandoc` from the [pandoc release page](https://github.com/jgm/pandoc/releases).
1. Install [`miktex`](https://miktex.org/download) and required packages.
1. Run conversion script by entering `./to_pdf` in your bash terminal.

## WSL2 / Ubuntu

### Install Pandoc

1. Download Release Package - `wget https://github.com/jgm/pandoc/releases/download/3.6.4/pandoc-3.6.4.1-amd64.deb`
2. Install Package - `sudo dpkg -i pandoc-3.6.4-1-amd64.deb`
3. Verify Installation: `pandoc -v`

### Install Miktex

1. Register GPG Key - `curl -fsSL https://miktex.org/download/key | sudo gpg --dearmor -o /usr/share/keyrings/miktex.gpg`
2. Register Installation Source (using Ubunut Jammy) - `echo "deb [signed-by=/usr/share/keyrings/miktex.gpg] https://miktex.org/download/ubuntu jammy universe" | sudo tee /etc/apt/sources.list.d/miktex.list`
3. Update and install - `sudo apt-get update`, `sudo apt-get install miktex`
4. Finish setup - `miktexsetup finish`

Full instructions at [miktex.org](https://miktex.org/download)

### Install xelatex

1. Install `sudo apt install texlive-xetex`
2. Verify installation `xelatex -v`

### Install font package

1. Install `sudo apt-get install "fonts-crosextra-carlito"`

### Run conversion script

Must be administrator: `sudo bash ./to_pdf`
