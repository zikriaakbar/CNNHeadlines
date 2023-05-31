# CNNHeadlines
Pythonscript for fetching the data of CNN Headlines
import requests
from bs4 import BeautifulSoup

# URL of the CNN website
url = "https://www.cnn.com/"

# Send a GET request to the URL
response = requests.get(url)

# Create a BeautifulSoup object to parse the HTML content
soup = BeautifulSoup(response.content, "html.parser")

# Find all the headline elements on the page
headline_elements = soup.find_all("h3", class_="cd__headline")

# Extract the text from the headline elements
headlines = [headline.text.strip() for headline in headline_elements]

# Print the headlines
for headline in headlines:
    print(headline)
