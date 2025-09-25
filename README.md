# Bughunter - Low Hanging Bug Finder

A comprehensive Python tool for discovering low-hanging security issues on a target domain. This tool performs various scans including subdomain enumeration, authentication panel discovery, clickjacking checks, SPF validation, security header analysis, Java library detection, and CVE lookups.

## Features

- **Subdomain Discovery**: Uses Certificate Transparency logs and DNS brute force to find subdomains.
- **Authentication Panels**: Identifies potential admin, login, and registration pages.
- **Clickjacking Protection**: Checks for missing X-Frame-Options and CSP headers.
- **SPF Records**: Detects and lints SPF records for email security.
- **Security Headers**: Scans for key security headers like CSP, HSTS, etc.
- **Java Libraries**: Extracts and analyzes publicly accessible JAR files.
- **CVE Lookup**: Searches for known vulnerabilities in detected components.
- **Multiple Output Formats**: Generates reports in JSON, Markdown, and HTML formats.
- **HTTP Server**: Automatically starts a local server to view HTML reports.

## Installation

### Prerequisites

- Python 3.10 or higher
- pip (Python package manager)

### Dependencies

Install the required Python packages using pip:

```bash
pip install requests beautifulsoup4 dnspython tldextract
```

### Cross-Platform Compatibility

This tool is compatible with Linux, Windows, and macOS. Ensure Python is installed on your system:

- **Linux**: Python is usually pre-installed. If not, install via your package manager (e.g., `sudo apt install python3` on Ubuntu).
- **Windows**: Download and install Python from [python.org](https://www.python.org/downloads/). Make sure to check "Add Python to PATH" during installation.
- **macOS**: Python is pre-installed. For the latest version, install via Homebrew: `brew install python`.

## Usage

### Basic Command

Run the tool with the following command:

```bash
python bughunter.py -d example.com -o out --max-pages 150 --threads 20
```

### Command-Line Arguments

- `-d, --domain`: Target domain (required, e.g., example.com)
- `-o, --output`: Output directory (default: "out")
- `--threads`: Number of threads (default: 12, reserved for future use)
- `--max-pages`: Maximum pages to crawl (default: 150)
- `--timeout`: HTTP timeout in seconds (default: 10)

### Running on Different Operating Systems

#### Linux

1. Open a terminal.
2. Navigate to the directory containing `bughunter.py`.
3. Run the command as shown above.

Example:
```bash
cd /path/to/bughunter
python3 bughunter.py -d example.com -o reports
```

#### Windows

1. Open Command Prompt or PowerShell.
2. Navigate to the directory containing `bughunter.py` using `cd`.
3. Run the command.

Example:
```cmd
cd C:\path\to\bughunter
python bughunter.py -d example.com -o reports
```

#### macOS

1. Open Terminal.
2. Navigate to the directory containing `bughunter.py`.
3. Run the command.

Example:
```bash
cd /path/to/bughunter
python3 bughunter.py -d example.com -o reports
```

### Output

The tool generates three types of reports in the specified output directory:

- **JSON Report**: `{domain}_bughunter.json` - Machine-readable data.
- **Markdown Report**: `{domain}_bughunter.md` - Human-readable summary.
- **HTML Report**: `{domain}_bughunter.html` - Interactive web report.

After scanning, the tool automatically starts an HTTP server on port 8000 (or the next available port) to serve the HTML report. Open your browser and navigate to `http://localhost:8000/{domain}_bughunter.html` to view the results.

## Examples

### Basic Scan
```bash
python bughunter.py -d example.com
```

### Custom Output and Settings
```bash
python bughunter.py -d example.com -o ./scans/example -o --max-pages 200 --threads 15 --timeout 15
```

### Quick Scan with Minimal Crawling
```bash
python bughunter.py -d example.com --max-pages 50
```

## Legal and Ethics

**Important**: Run this tool only on domains you own or have explicit written permission to test. You are responsible for complying with all applicable laws and policies. Unauthorized scanning may violate terms of service or local laws.

## Troubleshooting

- **Module Not Found Errors**: Ensure all dependencies are installed using the pip command above.
- **DNS Resolution Issues**: The tool requires internet access for DNS lookups and external API calls.
- **Port Already in Use**: If port 8000 is occupied, the tool will try the next available port.
- **Python Version**: Verify you're using Python 3.10+ by running `python --version` or `python3 --version`.

## Contributing
- manas1020:- https://github.com/manas1020
- SanikaG31:-  https://github.com/SanikaG31
- diptibangde10:- https://github.com/diptibangde10

## License

This project is open-source. Please check the license file for details.

---

For more information, refer to the inline comments in `bughunter.py`.
