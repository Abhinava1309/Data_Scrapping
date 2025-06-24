# 🕸️ Web Scraping Project (Requests, BeautifulSoup, Selenium, Web Scraper Extension)

This project is a comprehensive showcase of different web scraping techniques using:

- 🐍 **Requests + BeautifulSoup** — for fast scraping of static websites  
- 🧪 **Selenium WebDriver** — for scraping dynamic, JavaScript-rendered content  
- 🌐 **Web Scraper Browser Extension** — a no-code/low-code scraping solution for structured data

---

## 📦 What's Inside (`Data_Scrapping.zip`)

Once you extract the ZIP file, you’ll find:

```
Data_Scrapping/
├── bs4_scraper.ipynb               # Requests + BeautifulSoup example
├── selenium_scraper.ipynb         # Selenium notebook
├── web scrapper(website).ipynb    # Selenium + extension usage
├── output_data.csv                # Optional sample output
├── README.md                      # You're reading it!
└── LICENSE                        # MIT license
```

---

## 🧪 Method 1: Scraping with `requests` + `BeautifulSoup`

**Best for:** Static websites with HTML-rendered content only.

### 🔧 Requirements

```bash
pip install requests beautifulsoup4 pandas
```

### 🔍 Example Code Flow

```python
import requests
from bs4 import BeautifulSoup

url = 'https://example.com/products'
response = requests.get(url)
soup = BeautifulSoup(response.content, 'html.parser')
titles = [tag.text.strip() for tag in soup.select('div.product-title')]
print(titles)
```

**✅ Advantages**
- Simple, fast, and lightweight
- Great for HTML-rendered pages
- Easy CSV export with pandas

**⚠️ Limitations**
- Doesn’t work with JavaScript content
- Less flexible for complex interactions

---

## 🧪 Method 2: Scraping with Selenium

**Best for:** Dynamic websites with interactive content (e.g., Flipkart, Amazon)

### 🔧 Requirements

- Google Chrome + ChromeDriver

```bash
pip install selenium pandas
```

### 🚀 Example Code Flow

```python
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys

driver = webdriver.Chrome()
driver.get("https://www.flipkart.com")

search_box = driver.find_element(By.NAME, "q")
search_box.send_keys("tripod")
search_box.send_keys(Keys.ENTER)

titles = driver.find_elements(By.CLASS_NAME, "s1Q9rs")
for title in titles:
    print(title.text)
```

**✅ Features**
- Simulates real user actions
- Works great with JavaScript-heavy pages

**⚠️ Limitations**
- Slower compared to static scraping
- Requires WebDriver setup
- May be blocked by anti-bot tools

---

## 🌐 Method 3: Web Scraper Browser Extension

**Best for:** Beginners or no-code users scraping structured content

### 🧩 Installation

- Chrome: [Web Scraper Extension](https://chrome.google.com/webstore/detail/web-scraper/)
- Firefox: Search for it in the Add-ons store

### 🪜 Steps to Use

1. Open target website
2. Click the Web Scraper icon → Open Sitemap Editor
3. Create sitemap & define selectors
4. Start scraping & export to CSV/JSON

**✅ Features**
- No programming needed
- Works within browser
- Ideal for structured lists & tables

**⚠️ Limitations**
- May struggle with large datasets
- Limited by what the browser can load

---

## 📌 Tool Comparison

| Tool              | Best For                             | Handles JavaScript? |
|-------------------|--------------------------------------|---------------------|
| `requests + bs4`  | Fast, simple static scraping         | ❌ No               |
| `Selenium`        | Dynamic content & user interaction   | ✅ Yes              |
| `Web Scraper Ext` | Visual scraping for structured data  | ✅ Yes              |

---

## ✅ License

This project is licensed under the MIT License – see the `LICENSE` file for details.

---

## ✍️ Author

**Abhinava Ghosh**  
📧 Email: `susmitasurcoc600@gmail.com`

---

## 🤝 Contributions

Feel free to fork this repo or open issues/PRs to improve it.

---

## ⭐ Star This Project

If you found this helpful, don't forget to ⭐ it on GitHub!
```
