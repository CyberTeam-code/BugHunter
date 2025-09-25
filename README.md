# Bughunter

**Bughunter v1.1** – A Python-only low-hanging bug finder for security research, penetration testing, and bug bounty hunting.

Bughunter is designed to uncover **low-hanging vulnerabilities** in a target domain using pure Python, making it lightweight, portable, and easy to run across multiple operating systems without external dependencies like heavy scanners or binaries.

---

## What the Tool Does

Bughunter helps you identify **common weaknesses** in domains and web applications by performing a series of automated checks and reconnaissance tasks.  
It generates professional reports in **JSON**, **Markdown**, and **HTML**, complete with a built-in HTTP server for quick result viewing.

### Key Features

- **Subdomain Discovery**  
  Uses Certificate Transparency logs and DNS brute force to enumerate subdomains.

- **Authentication Panel Detection**  
  Automatically scans for **admin**, **login**, and **registration** pages.

- **Clickjacking Vulnerability Check**  
  Detects missing `X-Frame-Options` and CSP headers.

- **SPF Record Analysis**  
  Identifies issues with SPF records to prevent email spoofing.

- **Security Header Analysis**  
  Scans for missing headers like **CSP**, **HSTS**, etc.

- **Java Library Analysis**  
  Finds publicly accessible JAR files and checks their `MANIFEST` versions.

- **CVE Lookup**  
  Searches for known vulnerabilities related to discovered libraries or versions.

- **Export Capabilities**  
  Outputs results in **JSON**, **Markdown**, and **HTML** formats.

- **Built-in HTTP Server**  
  Automatically launches a local server to view interactive HTML reports.

---

## Use Cases

- Security Assessments and VAPT
- Bug Bounty Hunting
- Web Application Reconnaissance
- Domain and Subdomain Intelligence Gathering
- Vulnerability Research

---

## Installation Instructions

### Prerequisites
- Python **3.10 or higher**
- Internet connection for API lookups and scanning

---

### Step 1: Clone the Repository
```bash
git clone https://github.com/your-username/bughunter.git
cd bughunter
````

---

### Step 2: Install Dependencies

#### Install using pip:

```bash
pip install requests beautifulsoup4 dnspython tldextract
```

#### OR install via requirements.txt:

```bash
pip install -r requirements.txt
```

---

## OS-Specific Installation

### **Windows**

1. Download and install Python from [python.org](https://www.python.org/downloads/).
2. During installation, **check "Add Python to PATH"**.
3. Open **Command Prompt** or **PowerShell**:

   ```cmd
   cd C:\path\to\bughunter
   pip install -r requirements.txt
   python bughunter.py -d example.com
   ```

---

### **Linux**

```bash
sudo apt update
sudo apt install python3 python3-pip
git clone https://github.com/your-username/bughunter.git
cd bughunter
pip3 install -r requirements.txt
python3 bughunter.py -d example.com
```

---

### **macOS**

```bash
brew install python
git clone https://github.com/your-username/bughunter.git
cd bughunter
pip3 install -r requirements.txt
python3 bughunter.py -d example.com
```

---

## How to Use

### Basic Command

```bash
python bughunter.py -d example.com -o output_folder
```

---

### Command-Line Arguments

| Argument       | Description                    | Default Value |
| -------------- | ------------------------------ | ------------- |
| `-d, --domain` | Target domain to scan          | Required      |
| `-o, --output` | Output directory for reports   | `./out`       |
| `--threads`    | Number of threads for scanning | 12            |
| `--max-pages`  | Maximum pages to crawl         | 150           |
| `--timeout`    | HTTP request timeout (seconds) | 10            |

---

### Example Usage

#### 1. Basic Scan

```bash
python bughunter.py -d example.com
```

#### 2. Custom Output Directory

```bash
python bughunter.py -d example.com -o ./reports
```

#### 3. Fast Scan with More Threads

```bash
python bughunter.py -d example.com --threads 20 --timeout 8
```

---

## Output and Reports

After scanning, Bughunter generates **3 different report formats** in the output folder:

| Report Type | Example File Name        | Description            |
| ----------- | ------------------------ | ---------------------- |
| JSON        | `example_bughunter.json` | Machine-readable data  |
| Markdown    | `example_bughunter.md`   | Easy-to-read summary   |
| HTML        | `example_bughunter.html` | Interactive web report |

> **Tip:**
> Once the scan finishes, the tool starts a local HTTP server (default port **8000**).
> View your report in a browser:
> `http://localhost:8000/example_bughunter.html`

---

## System Requirements

| Resource   | Minimum Requirement   |
| ---------- | --------------------- |
| OS         | Windows, Linux, macOS |
| RAM        | 512MB                 |
| Disk Space | 50MB                  |
| Internet   | Required              |

---

## Troubleshooting

| Issue                    | Solution                                    |
| ------------------------ | ------------------------------------------- |
| `ModuleNotFoundError`    | Run `pip install -r requirements.txt`       |
| DNS errors               | Ensure stable internet connection           |
| Port 8000 already in use | Tool automatically picks the next free port |
| Python version too low   | Use Python 3.10 or higher                   |

---

## Legal Disclaimer

> **Use Responsibly**
> Run Bughunter **only on domains you own or have explicit permission to test**.
> Unauthorized scanning can lead to legal consequences.

---

### Contributors

* **Manas Dabhane** – 
  [https://github.com/manas1020](https://github.com/manas1020)

* **Sanika Gongale** – 
  [https://github.com/SanikaG31](https://github.com/SanikaG31)

* **Dipti Bangde** –
  [https://github.com/diptibangde10](https://github.com/diptibangde10)

---

## License

Open-source under the **MIT License** – see the LICENSE file for details.

---

```
```
