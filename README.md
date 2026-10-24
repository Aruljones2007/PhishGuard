# PhishGuard — Phishing URL Detection Web Application

## Project description
PhishGuard is a Python web application that analyzes the structure of a submitted URL for common phishing warning signs. It displays an illustrative risk score and explains the signals detected. The current version uses rule-based checks; it does not train a machine-learning model or visit submitted URLs.

## Technologies used
- Python 3.9+
- Flask
- HTML and CSS
- Python standard-library modules: `urllib.parse`, `ipaddress`, and `re`

## Dataset
The current application does not train on a dataset. For a future machine-learning extension, you may use:
- UCI Phishing Websites dataset: https://archive.ics.uci.edu/dataset/327/phishing
- UCI PhiUSIIL Phishing URL (Website) dataset: https://archive.ics.uci.edu/dataset/967/phiusil-phishing-url-dataset

If you use a dataset, follow its license and cite the dataset source in your report.

## Files
- `ArulJones_PhishGuard.ipynb` — complete code and web interface.
- `requirements.txt` — Python dependency list.
- `ArulJones_ProjectReport.docx` — project documentation.

## Setup and run
1. Install Python 3.9 or later.
2. Open a terminal in the project folder.
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Open `ArulJones_PhishGuard.ipynb` in Jupyter Notebook or JupyterLab.
5. Run the notebook cells in order.
6. Open `http://127.0.0.1:5000` in a browser on the same computer.
7. To stop the app, interrupt the notebook kernel.

## How detection works
The app checks for indicators such as unusual URL length, `@` characters, non-HTTPS URLs, IP-based hostnames, many subdomain levels, punycode, URL shorteners, and selected keywords. It maps the combined score to Low, Medium, or High risk-indicator bands. The scores are illustrative and are not calibrated probabilities.

## Limitations and safe use
- A low score does not guarantee that a URL is safe.
- Legitimate URLs can trigger warnings, and phishing URLs may evade these rules.
- The app does not follow redirects, inspect web page content, or query live reputation services.
- Use this as an educational awareness tool, not a replacement for a security service.
- Do not expose Flask's development server directly to the public internet.
