# 🛡️ SafeDev — Secure Package Installer for Developers

SafeDev is a security-focused CLI tool that **analyzes packages before installation** to prevent supply chain attacks, typosquatting, and malicious dependencies.

Instead of blindly installing packages using `pip`, SafeDev adds an intelligent security layer:

> 🔍 **Analyze → Score Risk → Ask → Install**

---

# 🚀 Features

## 🔐 1. Pre-install Security Scanning

* Scans downloaded package files before installation
* Uses:

  * AST analysis (detects dangerous code like `eval`, `exec`)
  * Regex rules (custom security patterns)

---

## ⚠️ 2. Typosquatting Detection

Detects common mistakes like:

* `pytorch` → suggests `torch`
* `colourama` → suggests `colorama`

Prevents installing malicious or wrong packages.

---

## 📊 3. Risk Scoring System (0–100)

* Calculates risk based on:

  * Severity of issues
  * Unique vulnerabilities
* Displays:

  * 🟢 Safe
  * 🟡 Low Risk
  * 🟠 Medium Risk
  * 🔴 High Risk

---

## ⚡ 4. Real-time Download Progress

* Shows:

  * Download size
  * Speed (MB/s)
  * Progress bar

---

## 🔍 5. Multi-threaded File Scanning

* Fast scanning using multiple CPU cores
* Handles large packages efficiently

---

## 🎨 6. Clean CLI UI

* Colored output using `colorama`
* Highlighted security findings
* Boxed reports for readability

---

## 🌐 7. Multi-source Support

Supports:

* Python (`pip`)
* Node (`npm`)
* Git repositories

---

# 📦 Installation

## 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/safedev.git
cd safedev
```

## 2. Install locally

```bash
pip install .
```

---

# 🧠 Usage

## 🔹 Basic Command

```bash
safedev install <package>
```

---

## 🔹 Examples

### Install a Python package

```bash
safedev install torch
```

### Install with typo detection

```bash
safedev install colourama
```

### Install npm package

```bash
safedev install express --npm
```

### Clone Git repo

```bash
safedev clone https://github.com/user/repo.git
```

---

# 🔄 How It Works (Step-by-Step)

## 1. Typo Check

* Detects suspicious package names
* Suggests correct alternatives

---

## 2. Trust Check

* Checks if package is known/trusted

---

## 3. Download Package

* Uses `pip download`
* Shows real-time progress

---

## 4. Extract Files

* Extracts `.whl` and `.zip` files

---

## 5. Scan Files

* Runs:

  * AST analysis
  * Regex rules

---

## 6. Generate Risk Score

* Calculates score (0–100)
* Categorizes risk level

---

## 7. Show Findings

Example:

```
⚠ Shell execution (Severity 4)
→ Uses subprocess to run commands
✔ Fix: Validate inputs
```

---

## 8. User Confirmation

```bash
Install anyway? (y/n):
```

---

## 9. Install Package

If approved → installs via pip

---

# 📁 Project Structure

```
safedev/
│
├── cli.py              # CLI entry point
├── pip_handler.py      # Python package handler
├── npm_handler.py      # Node package handler
├── scanner.py          # Security scanning engine
├── risk.py             # Risk calculation
├── typo.py             # Typosquatting detection
├── ui.py               # CLI UI
├── trust.py            # Trust validation
├── rules.json          # Security rules
```

---

# ⚠️ Limitations

* Static analysis only (no runtime detection)
* Does not scan deep dependency trees yet
* Limited rule database
* No CVE integration (yet)

---

# 🚀 Future Improvements

* 🔥 Dependency tree scanning
* 🔥 CVE vulnerability integration
* 🔥 AI-based threat detection
* 🔥 Sandbox execution
* 🔥 Package reputation scoring

---

# 🧠 Why SafeDev?

Modern attacks target developers through packages.

SafeDev helps you:

* Avoid malicious installs
* Detect risky code
* Make informed decisions

---

# 🧑‍💻 Author

Developed by **Rupanshu Sisodia**

---

# ⭐ Support

If you like this project:

* ⭐ Star the repo
* 🛠️ Contribute
* 🧠 Share ideas

---

# 🔥 Demo Idea

Try this:

```bash
safedev install pytorch
```

👉 Watch it detect typo + suggest correct package.

---

# 📜 License

MIT License
