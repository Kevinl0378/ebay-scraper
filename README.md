# Scraping from eBay

In this project, I created a Python program that scrapes information from eBay and saves it into either a JSON file or a CSV file. Here is a link to the project instructions: [Project_03](https://github.com/mikeizbicki/cmc-csci040/tree/2022fall/project_03)

<br/>

The `ebay-dl.py` file contains this program. It utilizes the `argparse`, `requests`, and `bs4` libraries to extract the name, price, ownership status, shipping cost, return cost, and units already sold for items that appear on eBay based on a specific search term, which is entered into the command line. The program then stores all of this information as a list of dictionaries, where each dictionary is for a different item. This list is saved as a JSON file by default when the program is executed.

<br/>

In order to run the file, you should enter your search term into the command line. For example, the following command line was used to generate the `ipad.json` file:  
```
$ python3 ebay-dl.py ipad
```

If your search term contains a space, you must put quotation marks around it. For example, the following command lines were used to generate the `playstation 5.json` file:
```
$ python3 ebay-dl.py 'playstation 5'
```
and the `coffee maker.json` file:
```
$ python3 ebay-dl.py 'coffee maker'
```
<br/>
<br/>

In order to save the output file as a CSV file instead of a JSON file, you would enter the `--csv` flag into the command line. For example, the following command lines were used to generate the `lego.csv` file:
```
$ python3 ebay-dl.py lego --csv
```
and the `celsius energy drink.csv` file:
```
$ python3 ebay-dl.py 'celsius energy drink' --csv
```

<br/>
<br/>

By default, the program scrapes information from the first 10 webpage results for your search term. This number can be adjusted in the command line. For example, if you wanted to scrape information from the first webpage only, you would enter:
```
$ python3 ebay-dl.py 'playstation 5' --num_pages=1
