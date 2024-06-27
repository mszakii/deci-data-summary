# DECI LEVEL 3 DATA TRACK SUMMARY 2024 2

By <span style="color: #009688; font-weight: bold">Mohamed Elsayed</span> © 2024

<h2 style="color: #3f51b5">1️⃣ Intro to Gathering Data</h2>

- The Data wrangling process

  - Gathering
  - Assess
  - Clean

- `TSV (Tab Separated Files)` A file format for representing tabular data that uses tabs as delimiters

- `Flat File` A plain text data file with one data record per line and fields **separated by delimiters**

To read TSV Files

```python
df = pd.read_csv("bestofrt.tsv", sep="\t")
```

### Beautiful Soup 🧼

- Method 1 Save The HTML file

```python
import requests
url = 'https://www.rottentomatoes.com/m/et_the_extraterrestrial'
response = requests.get(url)

# Save HTML to file
with open("et_the_extraterrestrial.html", mode='wb') as file:
    file.write(response.content)
```

- Method 2 Work Directly

```python
# Work with HTML in memory
from bs4 import BeautifulSoup
soup = BeautifulSoup(response.content, 'lxml')
```

- `Parser` is a tool used to pull information from markup languages (lxml)

- You can use `find` to find a specific tag in HTML

```python
soup.find('title')
```

```html
<title>E.T. The Extra-Terrestrial (1982) - Rotten Tomatoes</title>
```

- You can use `.contents` to find the contents in a specific tag
  - It returns a list of the tags of childrens.

```python
soup.find('div', class_ = "container").find("span").contents[0]
```

### How to write files programmatically

```python
folder_name = "my_scrapes"
url = "https://google.com/file.txt"

with open(os.path.join(folder_name, url.split('/')[-1]), mode = 'wb') as file:
    file.write(response.content)
```

- `Character sets` are the collections of characters that are available for use in a system.
- `Encoding` is the scheme for converting the character sets bits to letters and numbers.

- `glob Patterns` is a pattern used to match pathnames using wildcard characters
- `Wildcard Characters` is a placeholders used in searches to represent one or more characters

<h2 style="color: #3f51b5">2️⃣ Gathering Data Applications</h2>

- `JSON` stands for Javascript Object Notation
- `XML` stands for Extensible Markup Language.

To share dataset

```python
df.to_csv('dataset.csv', index=False)
```

### Glossary

| Key                                     | Definetion                                                                                                                                                                |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Application programming interface (API) | An interface that allows applications to communicate and each other and pass data                                                                                         |
| BeautifulSoup                           | An HTML parser written in the Python programming language.                                                                                                                |
| Character Set                           | A collection of characters that is available for use                                                                                                                      |
| Encoding                                | The scheme for converting the character set bits into letters and numbers                                                                                                 |
| Exploratory Data Analysis (EDA)         | A data analysis approach that focuses on identifying general patterns in the data, and identifying outliers and features of the data that might not have been anticipated |
| Extract Transform Load (ETL)            | A process to copy data from one or more sources and integrate it into a single dataset                                                                                    |
| Flat File                               | A plain text data file with one data record per line and fields separated by delimiters                                                                                   |
| glob Patterns                           | A pattern used to match pathnames using wildcard characters                                                                                                               |
| Tag Soup                                | A reference to the HTML found on many websites that is unstructured and difficult to parse                                                                                |
| Text File                               | A file that uses specific character set where lines of text are separated by newline characters and contains no formatting or media                                       |
| Web Scraping                            | Extracting data from websites using code                                                                                                                                  |
| Wildcard Characters                     | Placeholders used in searches to represent one or more characters                                                                                                         |

<h2 style="color: #3f51b5">3️⃣ Assessing vs Exploring</h2>

- `Dirty Data` Data that has issues with data content including missing data, invalid data, inaccurate date or inconsistent data

- `Messy Data` Data that has issues with its structure (columns, rows or table)

### Visual Assessment

- `Directed Visual Assessment` Systematically looking through each table of data in a Jupyter notebook or spreadsheet

- `Non-directed Visual Assessment` Scrolling through the data looking for interesting and relevant issues

### Exploratory Data Analysis (EDA) is about:

- `Exploring` the data with simple visualizations that summarize the data's main characteristics
- `Augmenting` the data, for example, removing outliers and feature engineering