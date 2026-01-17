# macOS Development Environment Setup

This guide will help you set up your macOS system with essential development tools.

## Quick Setup (Recommended)

Run the automated setup script:

```bash
./setup-macos.sh
```

**Note:** This script will:
- Install Xcode Command Line Tools (you'll need to click "Install" in the popup)
- Install Homebrew (you'll need to enter your password)
- Install Node.js, Python 3, and other useful tools
- Optionally configure git

## Manual Setup

If you prefer to set up manually, follow these steps:

### 1. Install Xcode Command Line Tools (includes Git)

```bash
xcode-select --install
```

A popup will appear - click "Install" and wait for it to complete.

### 2. Install Homebrew

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

After installation, you may need to add Homebrew to your PATH:

**For Apple Silicon Macs (M1/M2/M3):**
```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

**For Intel Macs:**
```bash
echo 'eval "$(/usr/local/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/usr/local/bin/brew shellenv)"
```

### 3. Install Development Tools

```bash
# Update Homebrew
brew update

# Install Node.js (for web development)
brew install node

# Install Python 3
brew install python@3.12

# Install GitHub CLI (optional but useful)
brew install gh

# Upgrade git to latest version
brew install git
```

### 4. Configure Git

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

## Verify Installation

Check that everything is installed:

```bash
git --version
brew --version
node --version
npm --version
python3 --version
```

## Additional Tools (Optional)

You might also want to install:

- **VS Code**: `brew install --cask visual-studio-code`
- **Docker**: `brew install --cask docker`
- **Postman**: `brew install --cask postman`
- **iTerm2**: `brew install --cask iterm2`

## Troubleshooting

### Homebrew not found after installation
Make sure you've added Homebrew to your PATH (see step 2 above) and restart your terminal.

### Permission issues
Some installations require administrator access. You'll be prompted for your password when needed.

### Xcode Command Line Tools stuck
If the installation seems stuck, you can check the status:
```bash
xcode-select -p
```

If it returns a path, the tools are installed. If not, try running the installation command again.
