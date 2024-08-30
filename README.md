# AI Web Scraper

## Overview

The **AI Web Scraper** is a powerful and user-friendly web scraping tool built using Python and Streamlit. It allows users to scrape content from websites, clean and process the content, and then parse specific information using AI models. The scraper is designed to handle complex web pages, including those protected by CAPTCHAs, and uses a robust backend powered by Selenium and Ollama's language models.

## Features

- **Website Scraping:** Scrape content from any website using Selenium with remote browser capabilities.
- **Content Cleaning:** Clean and extract meaningful text content from the scraped HTML.
- **AI-Powered Parsing:** Parse and extract specific information from the content using the Ollama language model.
- **User-Friendly Interface:** Streamlit-based UI for easy input and interaction.

## Technologies Used

- **Python 3.8+**
- **Streamlit:** For building the user interface.
- **Selenium:** For web scraping and handling CAPTCHAs.
- **BeautifulSoup:** For HTML parsing and content extraction.
- **Ollama LLM:** For AI-powered parsing of content.
- **Langchain:** For managing prompt templates and chaining operations.
- **dotenv:** For managing environment variables.

## Installation

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/Atomic-man007/AI-Web-Scraper.git
   cd AI-Web-Scraper
   ```

2. **Install the Required Packages:**

   It's recommended to use a virtual environment:

   ```bash
   python3 -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   ```

3. **Set Up Environment Variables:**

   Create a `.env` file in the project root with the following content:

   ```plaintext
   SBR_WEBDRIVER="http://your_selenium_browser_remote_address:port"
   ```

   Replace `"http://your_selenium_browser_remote_address:port"` with the actual URL of your Selenium WebDriver.

## Usage

1. **Run the Application:**

   Start the Streamlit app by running:

   ```bash
   streamlit run app.py
   ```

2. **Input Website URL:**

   - Enter the URL of the website you want to scrape in the input box.
   - Click the "Scrape Website" button to start the scraping process.
   - View the extracted DOM content in the expandable text box.

3. **Parse Content:**

   - Describe what you want to extract from the DOM content in the text area.
   - Click "Parse Content" to parse the information using the Ollama language model.
   - The parsed results will be displayed below.

## Code Overview

### `app.py`

This is the main application file that handles user interaction, scraping, and parsing. It consists of the following key steps:

- **Website Scraping:** 
  - Uses Selenium to scrape the website content.
  - Extracts and cleans the body content using BeautifulSoup.

- **AI-Powered Parsing:** 
  - Splits the DOM content into manageable chunks.
  - Uses Ollama LLM to parse and extract the desired information based on user input.

### `scrape.py`

This module contains the functions related to web scraping:

- `scrape_website(website)`: Connects to a remote Selenium browser and scrapes the HTML content of the specified website.
- `extract_body_content(html_content)`: Extracts the `<body>` content from the HTML.
- `clean_body_content(body_content)`: Cleans the extracted content by removing scripts, styles, and unnecessary whitespace.
- `split_dom_content(dom_content, max_length=6000)`: Splits the cleaned content into chunks for easier processing by the AI model.

### `parse.py`

This module handles the AI-powered parsing:

- `parse_with_ollama(dom_chunks, parse_description)`: Uses the Ollama language model to parse the DOM content based on the user's description.

### Environment Setup

- **Selenium Browser Remote (SBR):** Ensure that you have a running Selenium server or cloud-based service with the correct WebDriver setup.

## Contributing

Contributions are welcome! Please submit a pull request or open an issue to discuss any changes or improvements.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
