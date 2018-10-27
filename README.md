# data-512-a2: Investigating Bias in Data

Name: Tejas Hosangadi

Date: October 25th, 2018

## Goal of Project

The goal of this project is understanding and enriching our knowledge about data bias through an investigative research of Wikipedia articles, in particular, articles on political figures. We conduct two main analyses here, one looking at the percentage of articles as a proportion of a countries population and the other looking at the proportion of high quality articles as a proportion of the total number of articles. 

## Data sources that I used

There are two main data sources that are used here. Let's talk about both of them briefly.

### Wikipedia Dataset

This dataset contains data on most Wikipedia articles with the category "Politicians by nationality" It has three columns,  "page" contains the raw page title, "country" contains the cleaned country name and "last_edit" contains the edit ID of the last page edit.  The data can be found at figshare at this location: https://figshare.com/articles/Untitled_Item/5513449. The folder contains the data along with the code that was used to generate this data. The code and the data is licensed under the CC-BY-SA 4.0 license. The download contains the code and the dataset in a zipped format. For convenience, the data is available in this repo under the raw sub-directory of the data directory and is called page_data.csv. Please attribute whenver you share the data.

### Population Dataset

This dataset contains 207 countries and their population as of mid-2018. This data can be found at this location, and it's hosted on Dropbox: https://www.dropbox.com/s/5u7sy1xt7g0oi2c/WPDS_2018_data.csv?dl=0. There is no license listed on the Dropbox page for this given dataset. Since there is no license, I do not include it in this repository as it may be copyrighted. You must download the data and place it in the raw data folder to reproduce this analysis. 

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

Additionally, to generate the article scores, the Objective Revision Evaluation Service (ORES) API was used. This API classified Wikipedia articles into one of six different categories. Documentation for this API can be found at this link: https://www.mediawiki.org/wiki/ORES

## Data Files That Were Created

The Jupyter notebook creates a single file. This file, contained in the data directory and called final_data.csv, contains the joined results of the population and article datasets. Additionally, it includes a column that scores the article using the ORES API described above.

## Licensing Information

The assignment code is licensed under the MIT license. The license is located at the top of the directory for reference.

Licensing information of the data sources has been included above. 