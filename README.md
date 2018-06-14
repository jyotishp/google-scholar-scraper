# Google Scholar Scraper

## Installation

### Clone the repository
```
git clone https://github.com/jyotishp/google-scholar-scraper
```

### Setup a virtual environment (optional)
First, install virtualenv using pip or your OS package manager. Then run the following in the directory where the repository was cloned,
```
virtualenv --no-site-packages -p python3 scholar
source scholar/bin/activate
```

### Install necessary packages
Go to the directory where the repository was cloned and run the following,
```
pip install -r requirements.txt
```

## Usage

### Example
```python
#!/usr/bin/env python


from google_scholar import GoogleScholarUser

if __name__ == '__main__':
	user_id =  # The Google Scholar ID of the user you want to scrape
	# To retrieve this user_id, visit the profile of the user.
	# The user=xxxxxxxx part in the URL is the user_id you need.

	scraper = GoogleScholarUser(user_id)
	scraper.get_scholar_articles()

```

As of now, the articles are stored under `scraper.articles` variable. All the articles are instances of BeautifulSoup and hence contain HTML tags. In order to access only the text part, you can do something like,

```python
for article in scraper.articles:
	print(article.text)  # Prints only the text part remove HTML tags
```
