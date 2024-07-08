# web-enum
# Web Reconnaissance Automation Script

This Bash script automates the reconnaissance process for a specified URL, including subdomain enumeration, port scanning, subdomain takeover checks, and scraping wayback data.

## Prerequisites

Ensure you have the following tools installed:
- [assetfinder](https://github.com/tomnomnom/assetfinder)
- [httprobe](https://github.com/tomnomnom/httprobe)
- [subjack](https://github.com/haccer/subjack)
- [nmap](https://nmap.org/)
- [waybackurls](https://github.com/tomnomnom/waybackurls)

## Usage

```bash
./recon.sh <URL>
```

Replace `<URL>` with the target domain.

## Directory Structure

The script creates the following directory structure if they don't exist:

- `<URL>`
  - `recon/`
    - `scans/`
    - `httprobe/`
      - `alive.txt`
    - `potential_takeovers/`
      - `potential_takeovers.txt`
    - `wayback/`
      - `wayback_output.txt`
      - `params/`
        - `wayback_params.txt`
      - `extensions/`
        - `js.txt`
        - `jsp.txt`
        - `json.txt`
        - `php.txt`
        - `aspx.txt`
  - `final.txt`
  - `assets.txt`

## Functionality

- **Subdomain Enumeration**: Uses assetfinder to harvest subdomains.
- **Subdomain Probing**: Uses httprobe to check for alive subdomains.
- **Subdomain Takeover Check**: Uses subjack to identify potential subdomain takeover vulnerabilities.
- **Port Scanning**: Uses nmap to scan open ports on discovered alive subdomains.
- **Wayback Data Scraping**: Uses waybackurls to gather historical data from the target domain.
- **Parameter and File Extraction**: Extracts parameters and specific file types (js, jsp, json, php, aspx) from wayback data.

## Notes

- Ensure you have necessary permissions and dependencies installed before running the script.
- Some operations may take time depending on the target domain and network conditions.
