# Quick Start Guide for gallery-dl-modi

This guide will help you quickly verify that gallery-dl is functional and get started using it.

## Installation

### Option 1: Install from source (recommended for development)

```bash
# Clone the repository
git clone https://github.com/77degrees/gallery-dl-modi.git
cd gallery-dl-modi

# Install in development mode
python3 -m pip install -e .
```

### Option 2: Install directly via pip

```bash
python3 -m pip install git+https://github.com/77degrees/gallery-dl-modi.git
```

## Verify Installation

Run these commands to verify everything is working:

```bash
# Check version
gallery-dl --version

# View help
gallery-dl --help

# List available extractors
gallery-dl --list-extractors | head -20
```

Expected output:
```
1.31.3-dev
```

## Quick Functionality Test

Test the tool without downloading anything:

```bash
# Simulate download (no actual download)
gallery-dl --simulate --get-urls "https://example.com/image.jpg"
```

## Basic Usage Examples

### 1. Download images from a URL

```bash
gallery-dl "https://example.com/gallery"
```

### 2. Get URLs without downloading

```bash
gallery-dl --get-urls "https://example.com/gallery"
```

### 3. Download with custom directory

```bash
gallery-dl -d ~/Downloads "https://example.com/gallery"
```

### 4. Use authentication

```bash
gallery-dl -u "username" -p "password" "https://example.com/gallery"
```

### 5. View available options for a specific site

```bash
gallery-dl --list-extractors | grep -i "sitename"
```

## Running Tests

### Run all unit tests

```bash
python3 -m unittest discover -s test
```

### Run specific test module

```bash
python3 -m unittest test.test_util
```

## Configuration

### Create config file

```bash
# Initialize configuration
gallery-dl --config init
```

Default config locations:
- Linux/macOS: `~/.config/gallery-dl/config.json`
- Windows: `%APPDATA%\gallery-dl\config.json`

### Example configuration

Create a file at `~/.config/gallery-dl/config.json`:

```json
{
    "extractor": {
        "base-directory": "~/Downloads/gallery-dl/",
        "archive": "~/Downloads/gallery-dl/archive.sqlite3"
    }
}
```

## Common Commands

| Command | Description |
|---------|-------------|
| `gallery-dl --version` | Show version |
| `gallery-dl --help` | Show help |
| `gallery-dl --list-extractors` | List all supported sites |
| `gallery-dl -g URL` | Get URLs only |
| `gallery-dl -s URL` | Simulate (no download) |
| `gallery-dl -d PATH URL` | Download to specific directory |
| `gallery-dl -u USER -p PASS URL` | Use authentication |
| `gallery-dl --cookies FILE URL` | Use cookies file |

## Supported Features

- ✅ 914+ extractors for various websites
- ✅ Authentication (OAuth, cookies, username/password)
- ✅ Resume interrupted downloads
- ✅ Custom filename formats
- ✅ Post-processing
- ✅ Archive database (avoid re-downloads)
- ✅ Metadata extraction
- ✅ Filter expressions
- ✅ Rate limiting
- ✅ Proxy support

## Troubleshooting

### Issue: Command not found

```bash
# Make sure pip bin directory is in PATH
python3 -m gallery_dl --version
```

### Issue: Import errors

```bash
# Reinstall dependencies
pip3 install -r requirements.txt
```

### Issue: SSL errors

```bash
# Update certificates
pip3 install --upgrade certifi
```

## Getting Help

1. **Documentation:** See `README.rst` for detailed documentation
2. **Configuration:** Check `docs/configuration.rst` for all options
3. **Supported Sites:** See `docs/supportedsites.md`
4. **Issues:** Report bugs on GitHub Issues
5. **Status Report:** See `FUNCTIONALITY_STATUS.md` for detailed test results

## Next Steps

1. Read the full `README.rst` for comprehensive documentation
2. Explore `docs/` directory for advanced configuration
3. Check `docs/supportedsites.md` for list of supported websites
4. Review `CHANGELOG.md` for recent updates and features

---

**Note:** This is a fork of the original gallery-dl project. For the original project, visit: https://github.com/mikf/gallery-dl
