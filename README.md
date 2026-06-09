# Web Scraping Quotes Website using Python

## Project Overview

This project demonstrates how to perform web scraping using Python, Requests, and BeautifulSoup.

The scraper extracts quotes, authors, and tags from the Quotes to Scrape website and stores the collected data for further analysis.

The project automatically navigates through multiple pages, downloads HTML content, extracts useful information, and saves the results into a structured format.

---

## Features

* Scrapes data from multiple webpages automatically
* Uses Python Requests to fetch webpage content
* Uses BeautifulSoup for HTML parsing
* Extracts:

  * Quote Text
  * Author Name
  * Tags
* Stores downloaded HTML pages locally
* Saves extracted data into a Pandas DataFrame
* Exports data to CSV format
* Implements automatic stopping when no more pages are available

---

## Technologies Used

* Python
* Requests
* BeautifulSoup4
* Pandas
* HTML Parsing

---

## Project Structure

```
Web-Scraping-Project/
├── quotes_data.csv
├── scraping_activity.ipynb
└── README.md
```

---

## Installation

Install the required libraries:

```bash
pip install requests
pip install beautifulsoup4
pip install pandas
pip install lxml
```

---

## How It Works

### Step 1: Send HTTP Requests

The program sends requests to the target website using the Requests library.

```python
response = requests.get(url)
```

### Step 2: Download Web Pages

Each webpage is downloaded and stored as an HTML file.

```python
with open("quotes1.html", "w") as f:
    f.write(response.text)
```

### Step 3: Parse HTML

BeautifulSoup is used to parse the HTML structure.

python
soup = BeautifulSoup(html_content, "lxml")

### Step 4: Extract Data

The scraper extracts:

* Quote Text
* Author Name
* Tags

using CSS selectors.

```python
quotes = soup.select("div.quote")

### Step 5: Store Data

The extracted information is stored in a Python list and converted into a Pandas DataFrame.

```python
df = pd.DataFrame(all_quotes)

### Step 6: Export Data

The final dataset is exported as a CSV file.

python
df.to_csv("quotes_data.csv", index=False)


## Sample Output

| Quote                              | Author          | Tags                  |
| ---------------------------------- | --------------- | --------------------- |
| The world as we have created it... | Albert Einstein | change, deep-thoughts |
| It is our choices...               | J.K. Rowling    | abilities, choices    |

---

## Learning Outcomes

Through this project, I learned:

* Web Scraping Fundamentals
* HTTP Requests and Responses
* HTML Structure Analysis
* Data Extraction using BeautifulSoup
* Working with Loops for Multi-page Scraping
* Data Cleaning and Storage
* CSV File Generation using Pandas


## Future Improvements

* Store data in a database
* Add error handling and logging
* Scrape multiple websites
* Schedule automated scraping tasks
* Perform data visualization and analysis

## Author

Bhumika Rai

