# data-512-a2: Investigating Bias in Data

Name: Tejas Hosangadi

Date: October 25th, 2018

## Goal of Project

The goal of this project is understanding and enriching our knowledge about data bias through an investigative research of Wikipedia articles, in particular, articles on political figures. We conduct two main analyses here, one looking at the percentage of articles as a proportion of a countries population and the other looking at the proportion of high quality articles as a proportion of the total number of articles. 

## Data sources that I used

There are two main data sources that are used here. Let's talk about both of them briefly.

### Wikipedia Dataset

This dataset contains data on most Wikipedia articles with the category "Politicians by nationality" It has three columns,  "page" contains the raw page title, "country" contains the cleaned country name and "last_edit" contains the edit ID of the last page edit.  The data can be found at figshare at this location: https://figshare.com/articles/Untitled_Item/5513449. The folder contains the data along with the code that was used to generate this data. The code and the data is licensed under the CC-BY-SA 4.0 license. The download contains the code and the dataset in a zipped format. For convenience, the data is available in this repo under the raw sub-directory of the data directory and is called page_data.csv. Please attribute whenver you share the data.

| Column  | Description                          |
| ------- | ------------------------------------ |
| page    | The title of the page                |
| country | The country associated with the page |
| rev_id  | The revision ID of the given page    |

### Population Dataset

This dataset contains 207 countries and their population as of mid-2018. This data can be found at this location, and it's hosted on Dropbox: https://www.dropbox.com/s/5u7sy1xt7g0oi2c/WPDS_2018_data.csv?dl=0. The data is copyrighted by the Population Reference Bureau (PRB) and is not included in this repository.  

| Column     | Description                                 |
| ---------- | ------------------------------------------- |
| Geography  | The name of the country or entity           |
| Population | Its population as of mid 2018 (in millions) |

### Final Dataset

The final dataset that is used for the analysis has a format as shown in the table below:

| Column          | Description                                     |
| --------------- | ----------------------------------------------- |
| country         | The name of the country                         |
| article_name    | The title or name of the article                |
| revision_id     | The revision ID of the article                  |
| article_quality | The quality that is obtained using the ORES API |
| population      | The population of the country.                  |
|                 |                                                 |

## Programming and API Resources Used

This analysis was performed in an environment running Python 3.6. and was performed in a Jupyter notebook. There were a number of Python packages used, including Pandas, CSV, Requests, Json, Numpy, and Copy. 

For your convenience and understanding, I am including documentation for all the software and packages that I am using for this analysis. 

Python: https://docs.python.org/3.6/

Jupyter Notebook: https://jupyter-notebook.readthedocs.io/en/stable/

Pandas: https://pandas.pydata.org/pandas-docs/stable/

CSV: https://docs.python.org/3/library/csv.html

Requests: http://docs.python-requests.org/en/master/

Json: https://docs.python.org/3/library/json.html

Numpy: https://docs.scipy.org/doc/

Copy: https://docs.python.org/3/library/copy.html

Additionally, to generate the article scores, the Objective Revision Evaluation Service (ORES) API was used. This API classified Wikipedia articles into one of six different categories. Documentation for this API can be found at this link: https://www.mediawiki.org/wiki/ORES. This API returns one of the six following ratings for each article:

- **FA:** Featured article
- **GA:** Good article
- **B:** B-class article
- **C:** C-class article
- **Start:** Start-class article
- **Stub:** Stub-class article

FA is the highest rating, while Stub is the lowest. 

## Data Files That Were Created

The Jupyter notebook creates a single file. This file, contained in the data directory and called final_data.csv, contains the joined results of the population and article datasets. Additionally, it includes a column that scores the article using the ORES API described above.

## Results

### Countries with highest proportion of articles-per-population

| Country                        | Population | Number of Articles | Proportions (%) |
| ------------------------------ | ---------- | ------------------ | --------------- |
| Tuvalu                         | 10000      | 55                 | 0.5500          |
| Nauru                          | 10000      | 53                 | 0.5300          |
| San Marino                     | 30000      | 82                 | 0.2733          |
| Monaco                         | 40000      | 40                 | 0.1000          |
| Liechtenstein                  | 40000      | 29                 | 0.0725          |
| Tonga                          | 100000     | 63                 | 0.06390         |
| Marshall Islands               | 60000      | 37                 | 0.06166         |
| Iceland                        | 400000     | 206                | 0.05150         |
| Andorra                        | 80000      | 34                 | 0.04250         |
| Federated States of Micronesia | 100000     | 38                 | 0.03800         |

### Countries with lowest proportion of articles-per-population

| Country     | Population | Number of Articles | Proportions (%) |
| ----------- | ---------- | ------------------ | --------------- |
| India       | 1371300000 | 966                | 0.000072        |
| Indonesia   | 265200000  | 214                | 0.000081        |
| China       | 1393800000 | 1135               | 0.000081        |
| Uzbekistan  | 32900000   | 29                 | 0.000088        |
| Ethiopia    | 107500000  | 105                | 0.000098        |
| Zambia      | 17700000   | 25                 | 0.000141        |
| North Korea | 25600000   | 39                 | 0.000152        |
| Thailand    | 66200000   | 112                | 0.000169        |
| Bangladesh  | 166400000  | 323                | 0.000194        |
| Mozambique  | 30500000   | 60                 | 0.000197        |

### Countries with highest proportion of high quality articles

| Country                  | Total Articles | High Quality Articles | Proportion (%) |
| ------------------------ | -------------- | --------------------- | -------------- |
| North Korea              | 39             | 7                     | 17.948718      |
| Saudi Arabia             | 119            | 16                    | 13.445378      |
| Central African Republic | 68             | 8                     | 11.764706      |
| Romania                  | 348            | 40                    | 11.494253      |
| Mauritania               | 52             | 5                     | 9.615385       |
| Tuvalu                   | 55             | 5                     | 9.090909       |
| Bhutan                   | 33             | 3                     | 9.090909       |
| Dominica                 | 12             | 1                     | 8.33333        |
| United States            | 1092           | 82                    | 7.509158       |
| Benin                    | 94             | 7                     | 7.446809       |

### Countries with lowest proportion of high quality articles

| Country               | Total Articles | High Quality Articles | Proportion (%) |
| --------------------- | -------------- | --------------------- | -------------- |
| Comoros               | 51             | 0                     | 0.0            |
| Soloman Islands       | 98             | 0                     | 0.0            |
| Nepal                 | 361            | 0                     | 0.0            |
| Djibouti              | 39             | 0                     | 0.0            |
| Tunisia               | 140            | 0                     | 0.0            |
| Kazakhstan            | 79             | 0                     | 0.0            |
| Slovakia              | 119            | 0                     | 0.0            |
| Moldova               | 426            | 0                     | 0.0            |
| Sao Tome and Principe | 22             | 0                     | 0.0            |
| Cameroon              | 105            | 0                     | 0.0            |

There were 37 countries in total with no high ranked articles. These were 10 of them. 

## Licensing Information

The assignment code is licensed under the MIT license. The license is located at the top of the directory for reference. 

The Wikipedia data is licensed under CC-BY-SA 4.0. Remember to attribute whenever you use this data.

The population data is copyrighted by the Population Reference Bureau (PRB). Please visit https://www.prb.org to find more information about data usage. 

Content that is produced by the ORES API is subject to the copyright agreement CC-BY-SA 3.0 license. Use of the API means you agree to all terms and conditions of this license. 

