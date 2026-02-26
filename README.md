DATE: 2026/02/23
# Retail Inventory Analytics & API Data Pipeline
Automated API inventory pipeline for Webhallen.com GPU stock. Identifies trapped capital in uncompetitive 8GB units and maps retail price-to-performance gaps. Analyzes inventory bulges in the RTX 50-series to pinpoint structural risk.

## Project
This project evaluates the inventory health, pricing efficiency, and market positioning of Webhallen, a major Swedish electronics retailer. By building an automated, API-first data extraction pipeline, I gathered a complete snapshot of their GPU inventory (as of 2026/02/22). 

The analysis identifies structural market shifts, calculates "trapped capital" due to brand premiums, and contextualizes the inventory against aggressive competitor pricing (e.g., Inet).

## This project is split into two Jupyter Notebooks:
### 1. Data Extraction ('Webhallen GPU Inventory Scraper.ipynb')
A Python web scraper built to bypass fragile HTML parsing by intercepting the retailer's backend API directly.
* **API-First Extraction:** Captures raw JSON payloads for maximum stability.
* **Defensive Parsing:** Utilizes '.get()' dictionary methods to handle missing or malformed database entries without pipeline failure.
* **Feature Engineering:** Heavy utilization of Regular Expressions (Regex) to extract hardware specifications (VRAM, Clock Speed, Base GPU) from unstructured text strings.
* **Categorical Engineering:** Custom Python logic mapping sub-brands into strategic market tiers (Halo, Performance, Value).

[!IMPORTANT]
This script is highly customizable for other retailers. However, users must consult the /robots.txt file of any target domain to ensure compliance with their policies.

### 2. Analysis ('Analysis of Webhallens GPU inventory')
A comprehensive business intelligence report translating raw inventory data into actionable retail strategy.
* **The 8GB "Dead Zone":** Analysis indicates a 4,000 SEK hard ceiling for the viability of 8GB GPUs. One competitor is saturating the market with >250 units of 16GB alternatives (RX 9060 XT) priced between 4,599 and 5,700 SEK.
* **Trapped Capital Detection:** Formulated a custom risk metric isolating working capital tied strictly to manufacturer "brand premiums" over baseline equivalents.
* **Inventory Dominance:** Identified areas where the retailer holds a pricing advantage (e.g., cheap INNO3D RTX 5080 stock) that many competitors cannot currently match.

# Tech Stack
* **Language:** Python
* **Data Extraction:** requests, json, time, random
* **Data Processing:** pandas, re (Regex)
* **Data Visualization:** matplotlib, seaborn

## How to run
1. Clone repository to your machine.
2. Install required libraries installed (pip install pandas matplotlib seaborn requests).
3. Run 'Webhallen GPU Inventory Scraper.ipynb' to generate a fresh CSV snapshot of the current inventory.
4. Run 'Analysis of Webhallens GPU inventory.ipynb' to generate the visual dashboards & more.
