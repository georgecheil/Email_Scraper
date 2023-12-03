# Email_Scraper

Simple web scraper that extracts email addresses from a target website.

### Web Scraper for Email Addresses

This Python script uses the BeautifulSoup library and requests module to scrape email addresses from a given target URL.

#### Prerequisites
Make sure you have the following dependencies installed:
```bash
pip install beautifulsoup4 requests
```

#### Usage
1. Run the script in a Python environment.
2. Enter the target URL when prompted.
3. The script will crawl the website, extract email addresses, and display them.

#### Code Explanation

1. **Importing Libraries:**
   - `BeautifulSoup`: Used for pulling data out of HTML and XML files.
   - `requests`: Used for making HTTP requests.
   - `urllib.parse`: Used for parsing URLs.
   - `deque`: A double-ended queue for efficiently adding and removing elements.
   - `re`: Regular expression library for pattern matching.

2. **User Input:**
   - The script prompts the user to enter the target URL.

3. **Initialization:**
   - Initializes a deque (`urls`) to store URLs for crawling.
   - Sets up sets (`scraped_urls` and `emails`) to store unique URLs and email addresses, respectively.
   - Initializes a counter (`count`) to limit the number of processed URLs.

4. **Crawling Loop:**
   - The script enters a loop where it dequeues URLs from `urls` and processes them until the count reaches 100 or the queue is empty.
   - The script handles exceptions such as missing schema or connection errors.

5. **Processing URLs:**
   - Extracts the base URL and path from the current URL.
   - Makes an HTTP request to the URL and extracts email addresses using a regular expression.
   - Parses the HTML content using BeautifulSoup.

6. **Finding Links:**
   - Iterates over `<a>` tags in the HTML and extracts the `href` attribute.
   - Forms absolute URLs from relative URLs and adds them to the deque for further processing.

7. **Interrupt Handling:**
   - The script handles KeyboardInterrupt, allowing the user to stop the script without losing progress.

8. **Displaying Email Addresses:**
   - After crawling, the script prints the extracted email addresses.

#### Limitations
- This script has a simple email regex and may not capture all email formats.
- The crawling is limited to 100 URLs to prevent excessive requests.

Feel free to customize the script based on your needs, and ensure compliance with the website's terms of service.
