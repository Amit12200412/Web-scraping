Google Maps Business Scraper

Overview:
Google Maps Business Scraper is a GUI application built using Python that assists in automating the extraction of business details from Google Maps for a city and country. The issue of manually searching and gathering business details in various categories is addressed. The application extracts major details like Business Name, Website, Phone Number, Address, and tries to gather the first available email from the website of the business. It has support for several categories per execution and tracks entries per category.

Features:

1. GUI Input for Easy Use – Simple-to-use interface with input fields.
2. Multiple Categories Support – Input several business categories separated by commas.
3. Email Extraction – Fetches emails automatically from business websites.
4. Dynamic Excel Output – Exports data to Excel with a "Category Count" column.
5. Logging – Everything logged in serpapi_scraper.log.
6. Error Handling – Retries failed website requests and logs issues.

Prerequisites:

* Python 3.8 or later
* Packages: requests, pandas, ipywidgets, openpyxl
* A SerpApi API Key

Install required packages:
pip install requests pandas ipywidgets openpyxl

Setup Instructions:

1. Clone or download the project repository.
2. Open the scraper.py file in Jupyter Notebook or any Python IDE with widget support.
3. Insert your SerpApi API key:
   SERPAPI_KEY = "YOUR_SERPAPI_KEY"
4. Run the script to show the GUI.

Usage Steps:

1. Input Country (e.g., USA).
2. Input City/State (e.g., Kansas City).
3. Input Categories space-separated:
   Clothing & Apparel, Electronics & Gadgets, Beauty & Personal Care, Jewelry & Accessories, Furniture & Décor, Legal Services, Accounting & Tax, Consulting, Real Estate Agency, Financial Planning, Hospitals & Clinics, Fitness Centers, Restaurants, Cafes, Catering Services, Coaching Institutes
4. Input an Output File name (optional). Blank if not specified, a timestamped name is automatically generated.
5. Press Run Scraper to initiate the process.
6. Wait for scraping to finish. Observe progress in the output area.
7. Verify that the resulting Excel file contains business records and category counts.

Output:
The Excel file has the following columns:

* Business Name
* Email
* Phone
* Website
* Address
* Category
* Category Count (number of records in that category)

Filename format: <Country>*<City>*<Categories>_<YYYYMMDD_HHMM>.xlsx

Quick Start GUI Screenshot:

* Country: Text input for country.
* City/State: Text input for city.
* Categories: Category input for categories (comma-separated).
* Output File: Optional file name.
* Run Scraper: Button to run scraping.
* Output Area: Live progress and logs are displayed.

Logging:
Every activity, warning, and error is logged in serpapi_scraper.log for troubleshooting purposes.

Notes:

* Email extraction relies on website structure; some websites don't list emails.
* Be considerate of SerpApi rate limits according to your subscription.
* Active internet connection is needed during scraping.

Example:
Scraping Kansas City, USA for multiple categories produces an Excel file like:
USA_KansasCity_Clothing & Apparel-Electronics & Gadgets-Beauty & Personal Care_20250928_1530.xlsx

Challenges Faced:A

1. Some websites blocked automated requests, making email extraction inconsistent.
2. Businesses without websites or emails had to be skipped.
3. Handling multiple categories and ensuring correct Category Count for each record required careful tracking.
4. Rate limits of SerpApi needed attention to avoid request failures.
5. Making the GUI refresh dynamically and show real-time progress during extended scraping sessions.

License:
MIT License – free to use, modify, and distribute for both private and commercial use.
