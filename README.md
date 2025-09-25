# bughunter

**bughunter** is an all-in-one domain bug finder tool designed to perform comprehensive security assessments on web domains. It automates the discovery of subdomains, enumeration of admin/login/registration panels, clickjacking checks, SPF evaluation, security headers analysis, Java library version scanning, and CVE lookups. The tool generates detailed reports in JSON, Markdown, and HTML formats for easy analysis.

## Features

- **Subdomain Discovery**: Uses Certificate Transparency (CT) logs and DNS brute-forcing to find subdomains.
- **Admin/Login/Registration Panel Enumeration**: Scans for common authentication pages and crawls for additional links.
- **Clickjacking Checks**: Identifies potential clickjacking vulnerabilities by checking for missing X-Frame-Options and CSP headers.
- **SPF (Sender Policy Framework) Evaluation**: Analyzes SPF records for email security.
- **Security Headers Evaluation**: Checks for essential security headers like Content-Security-Policy, X-Frame-Options, etc.
- **Java Library Version Scanning**: Discovers publicly accessible .jar files and extracts manifest information.
- **CVE Lookup**: Performs best-effort CVE searches for detected components using public APIs.
- **Detailed Reporting**: Outputs results in JSON, Markdown, and HTML formats for comprehensive analysis.

## Prerequisites

- Python 3.10 or higher
- Internet connection for external API calls (e.g., CVE lookup)
- Permissions to test the target domain (see Disclaimer)

## Installation

### Windows

1. **Install Python**:
   - Download and install Python 3.10+ from the [official website](https://www.python.org/downloads/).
   - Ensure "Add Python to PATH" is checked during installation.

2. **Install Dependencies**:
   - Open Command Prompt or PowerShell as Administrator.
   - Navigate to the project directory:
     ```
     cd d:/edunet/bugsolver
     ```
   - Install required packages:
     ```
     pip install -r requirements.txt
     ```

3. **Verify Installation**:
   - Run the tool:
     ```
     python bughunter.py --help
     ```

### Linux

1. **Install Python**:
   - Update your package manager and install Python 3.10+:
     ```
     sudo apt update
     sudo apt install python3 python3-pip  # For Ubuntu/Debian
     # or
     sudo yum install python3 python3-pip  # For CentOS/RHEL
     ```

2. **Install Dependencies**:
   - Navigate to the project directory:
     ```
     cd /path/to/bugsolver
     ```
   - Install required packages:
     ```
     pip3 install -r requirements.txt
     ```

3. **Verify Installation**:
   - Run the tool:
     ```
     python3 bughunter.py --help
     ```

### macOS

1. **Install Python**:
   - Download and install Python 3.10+ from the [official website](https://www.python.org/downloads/) or use Homebrew:
     ```
     brew install python
     ```

2. **Install Dependencies**:
   - Navigate to the project directory:
     ```
     cd /path/to/bugsolver
     ```
   - Install required packages:
     ```
     pip3 install -r requirements.txt
     ```

3. **Verify Installation**:
   - Run the tool:
     ```
     python3 bughunter.py --help
     ```

## Usage

Run the tool with the following command:

```
python bughunter.py -d example.com -o out --max-pages 150 --threads 20
```

- `-d, --domain`: Target domain (required, e.g., example.com)
- `-o, --output`: Output directory (default: out)
- `--threads`: Number of threads (default: 12, reserved for future use)
- `--max-pages`: Maximum pages to crawl (default: 150)
- `--timeout`: HTTP timeout in seconds (default: 10)

**Example**:
```
python bughunter.py -d example.com -o reports --max-pages 200 --threads 15
```

After execution, check the console for a summary and review the generated files in the output directory.

## Output

The tool generates three types of reports in the specified output directory:

- **JSON Report**: `{domain}_bughunter.json` - Machine-readable data.
- **Markdown Report**: `{domain}_bughunter.md` - Human-readable summary.
- **HTML Report**: `{domain}_bughunter.html` - Interactive web-based report.

Example output files:
- `example.com_bughunter.json`
- `example.com_bughunter.md`
- `example.com_bughunter.html`

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a feature branch: `git checkout -b feature/new-feature`.
3. Commit your changes: `git commit -am 'Add new feature'`.
4. Push to the branch: `git push origin feature/new-feature`.
5. Submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Disclaimer

**Legal & Ethics**: Run this tool only on domains you own or have explicit written permission to test. You are responsible for complying with all applicable laws and policies. Unauthorized scanning may violate terms of service or legal regulations.

For educational and authorized use only.
