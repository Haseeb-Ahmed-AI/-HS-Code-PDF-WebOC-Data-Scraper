# HS Code PDF & WebOC Data Scraper
## Table of Contents

-   Overview
-   Features
-   Architecture
-   Project Structure
-   Installation
-   Usage
-   Sample Outputs
-   Contributing
-   License

## Overview

This project provides an end-to-end automation pipeline that: - Reads
government-issued tariff PDFs - Extracts HS Codes with descriptions -
Searches each HS Code on the WebOC valuation portal - Captures
valuation, unit prices, country data, and timestamps - Stores all
records into structured Excel files

It is built for reliability, high-volume extraction, and minimal
supervision.

## Features

### PDF Extraction

-   Extracts HS Codes from complex table layouts
-   Auto-cleaning and formatting
-   Saves output to Excel for easy reuse

### WebOC Scraping

-   Fully automated browser workflow using Playwright
-   Handles pagination and multi-page datasets
-   Resumes automatically after unexpected stops
-   Retry mechanism with up to 100 attempts

### Excel Output

-   Clean, structured, and validated Excel files
-   Automatic file-splitting for large datasets
-   Removes emojis and unsupported characters

## Architecture

    PDF → HS Code Extractor → HS Code List → Web Scraper → Clean Excel Output

## Project Structure

    /Documents
        /PDF-Files
        /Excel-Files
        file_name_counter.txt

    src/
        PdfExtractor.py
        WebScraping.py
        __init__.py

## Installation

    pip install -r requirements.txt
    playwright install

## Usage

### Extract HS Codes

``` python
from PdfExtractor import pdf_extractor
hs_codes = pdf_extractor(newExtraction=True)
```

### Run Web Scraper

``` python
from WebScraping import run
run(hs_codes, isAllPages=True)
```

### Output

Stored in:

    /Documents/Excel-Files/

## Sample Output

(Insert screenshots here)

## Contributing

1.  Fork the repository\
2.  Create a feature branch\
3.  Commit changes\
4.  Open a pull request

## License

MIT License

## Disclaimer

Ensure compliance with website terms and national regulations before
scraping.
