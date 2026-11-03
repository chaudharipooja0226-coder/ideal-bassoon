# Automated Web Scanner

## Project description
A small Python educational tool that checks one user-supplied website for six commonly used HTTP security headers and reviews the returned CORS headers. It prints a readable summary and saves the result as `scan_report.json`.

**Authorized-use only:** Use only on a website you own or have explicit permission to assess. The tool sends one GET request, follows normal redirects, and does not crawl, fuzz, exploit, bypass authentication, or test credentials. Do not use it against `ibm.bob.com` or any other third-party domain unless you have written authorization.

## Technologies
- Python 3
- Requests library
- Jupyter Notebook

## Files
- `YourName_AutomatedWebScanner.ipynb` — notebook source code and usage notes
- `automated_web_scanner.py` — same code in standalone Python form
- `requirements.txt` — dependency list
- `YourName_ProjectReport.docx` — project documentation

## Dataset
No external dataset is required. The scanner evaluates live HTTP response headers supplied by the authorized target. For repeatable classroom demonstrations, use a local test web server or a deliberately configured training application.

## Setup
1. Install Python 3.9 or newer.
2. Download/extract this project folder.
3. Open a terminal in the project folder.
4. Install dependencies:

   ```bash
   python -m pip install -r requirements.txt
   ```

## Run in Jupyter
1. Start Jupyter Notebook: `jupyter notebook`
2. Open `YourName_AutomatedWebScanner.ipynb`.
3. Run the code cell.
4. In a new cell, call:

   ```python
   result = scan_url("https://your-authorized-domain.example")
   print_report(result)
   ```

## Run as a Python script
```bash
python automated_web_scanner.py
```
Enter a single authorized URL and type `AUTHORIZED` when prompted. The output is saved to `scan_report.json`.

## Checks performed
- Strict-Transport-Security
- Content-Security-Policy
- X-Content-Type-Options
- X-Frame-Options
- Referrer-Policy
- Permissions-Policy
- Access-Control-Allow-Origin and Access-Control-Allow-Credentials

## Important limitations
This is a basic header review, not a penetration test or a complete security audit. Header requirements depend on the application and deployment. CORS conclusions require context; a reflected test Origin is a signal to review, not proof of exploitability. HTTPS certificate validation remains enabled.
