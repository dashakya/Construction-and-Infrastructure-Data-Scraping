# Web Scraping and Named Entity Recognition (NER) with Python

This project demonstrates how to scrape content from a webpage and perform Named Entity Recognition (NER)
using Python libraries such as `requests`, `BeautifulSoup`, and `spaCy`. 
The script specifically targets a webpage containing major projects listed by the city of Richmond, CA, extracts content from linked pages,
and identifies named entities within that content.

## Prerequisites

Before running the script, ensure you have Python3.11 installed on your system along with the following packages:

- `requests`
- `beautifulsoup4`
- `spacy`

# Setup

This project uses the `en_core_web_sm` language model for SpaCy.

Run the following command to download and install the en_core_web_sm model:

- !python -m spacy download en_core_web_sm


##  To install the dependencies listed in requirements.txt, run the following command:

pip install -r requirements.txt

## Description:

requests - For making HTTP requests to fetch web pages.
beautifulsoup4 - For parsing HTML and extracting information from web pages.
spacy - en_core_web_sm` (a spaCy language model)  en_core_web_sm a pre-trained NLP language model, which is used for NER.  

## Remember

As soon as data scraped a csv file named 'scraped.csv' will form that contains 'title' and 'details' column(details column contains data of entire page of particular project link) details column is then leveraged for generating NER(named entity recognition)

After it ,apply en_core_web_sm model to each row of details column to fetch NER

Make connection with MySql database using sqlalchemy

At last, data will get stored in database :

Table columns :
original_id	aug_id	country_name	country_code	region_name	region_code	latitude	longitude	url	title	description	status	timestamp	timestamp_label	budget	budget_label	currency	sector	subsector	document_urls



### Input:
https://www.ci.richmond.ca.us/1404/Major-Projects


### Output:

| original_id | aug_id | country_name   | country_code | region_name   | region_code | latitude | longitude | url                                                      | title                                      | ... | timestamp | timestamp_label | budget | budget_label | currency | sector | subsector | document_urls                                               | org | date |
|-------------|--------|----------------|--------------|---------------|-------------|----------|-----------|----------------------------------------------------------|--------------------------------------------|-----|-----------|-----------------|--------|--------------|----------|--------|-----------|-------------------------------------------------------------|-----|------|
| na          | na     | United States  | US           | Richmond      | na          | na       | na        | [Link](http://www.ci.richmond.ca.us/viaverdiproject)     | Via Verdi Slope Stabilization Project       | ... | na        | na              | na     | na           | na       | na     | na        | [Document](http://www.ci.richmond.ca.us/DocumentCenter/Vi...) | na  | na   |
| na          | na     | United States  | US           | na            | na          | na       | na        | [Link](https://www.ci.richmond.ca.us/4486/Travel-Safe)  | Travel Safe Richmond                       | ... | na        | na              | na     | na           | na       | na     | na        | [Document](https://www.ci.richmond.ca.us/DocumentCenter/V...) | na  | na   |
| na          | na     | United States  | US           | na            | na          | na       | na        | [Link](http://www.ci.richmond.ca.us/3001/Atlas-Road-I)  | Atlas Road Industrial Building Project      | ... | na        | na              | na     | na           | na       | na     | na        | [Document](http://www.ci.richmond.ca.us/3001/Atlas-Road-I...) | na  | na   |
| na          | na     | United States  | US           | Baxter Creek  | na          | na       | na        | [Link](http://www.ci.richmond.ca.us/index.aspx?NID=2443) | Richmond Greenway Gap Closure Project      | ... | na        | na              | na     | na           | na       | na     | na        | [Email](mailto:lina_velasco@ci.richmond.ca.us) [Link](http://...) | na  | na   |
| na          | na     | United States  | US           | Project Area  | na          | na       | na        | [Link](http://www.ci.richmond.ca.us/2595/Mathieu-Cour) | Mathieu Court Alley Play Street            | ... | na        | na              | na     | na           | na       | na     | na        | [Document](https://kaboom.org/playability/play_everywhere...) | na  | na   |


22 columns

