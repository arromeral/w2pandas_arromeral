# 🦈🩸Data cleaning & wrangling project - Sharks🩸🦈
![Alt text](https://static1.colliderimages.com/wordpress/wp-content/uploads/2023/06/jaws-movies-ranked-worst-to-best.jpg?q=50&fit=contain&w=1140&h=&dpr=1.5)
## Description
The project consists of cleaning and wrangling a database imported from the following csv document [Sharks](https://www.kaggle.com/datasets/teajay/global-shark-attacks) which contains records of shark attacks from 1703 to 2018.

Each record includes a large number of attributes, in many cases with very little consistency and without a clear pattern. Also, a large number of records and some columns from the original set are practically useless due to the large number of null values ​​they contain.

During this project i will try to clean and establish homogenization criteria until obtaining a DataFrame that can be used to carry out different analyzes based on the relevant data of the document.

Likewise, I will perform some analyzes with the DataFrame once cleaned.
## Contents
The contents of the project are as follows:
- [src folder](https://github.com/arromeral/w2pandas_arromeral/tree/main/src):
  - [jaws.ipynb](https://github.com/arromeral/w2pandas_arromeral/blob/main/src/jaws.ipynb): Jupyter notebook with the main code used to clean and obtain results.
  - [funclean.ipynb](https://github.com/arromeral/w2pandas_arromeral/blob/main/src/funclean.ipynb): Jupyter notebook with some custom functions to clean and categorize columns used in jaws.ipynb.
- [images](https://github.com/arromeral/w2pandas_arromeral/tree/main/images): Folders with some pictures of charts obtained during the analysis.
- [attacks.csv](https://github.com/arromeral/w2pandas_arromeral/blob/main/attacks.csv): original csv document with raw data.
- [attacks_clean.csv](https://github.com/arromeral/w2pandas_arromeral/blob/main/attacks_clean.csv): final csv document exported with clean data.
- [paises.csv](https://github.com/arromeral/w2pandas_arromeral/blob/main/paises.csv): csv document containing the ISO2 and ISO3 codes of most countries and their name in several languages.
## Methodology
### Cleaning stage:

For the cleaning phase, different methodologies based on the Pandas library have been used with the aim of examining, understanding, improving the syntax and accessibility to data, and eliminating useless information.
#### Examining & undestanding
First, the document has been examined using the *.shape()* and *.info()* methods to find out the size of the DataFrame, the data types and the columns with null values.
I have also used a custom **checknan** function to see the distribution of null values ​​in rows and columns.
#### Improving syntax
For better use of the data, some column names have been modified, removing spaces and unnecessary characters, making it more understandable. The datatype of some columns has also been changed and the data of almost identical columns has been homogenized. For this, the *.rename()* method has been used largely.
#### Eliminating useless information
Once the distribution of null values ​​has been studied, those records where the majority of the columns had null values ​​have been eliminated, considerably reducing the size of the DataFrame.

One of the conditions at the beginning of the project was not to reduce the number of columns, so columns with a large number of nulls have been reused to store more useful data, such as the number of nulls per row(*num_nan column*).
#### Improving accessibility to data
In this phase, first of all the null values ​​of records of interest have been replaced by the word "unknown" so that they can be used more easily in future analyzes.
Next, I have focused on trying to clean the data in the columns of greatest interest for future studies, such as Country, Sex, Activity, Species, Time or Fatal, trying to categorize each column as much as possible, reducing the number of unique values ​​in those columns. Also, the Date column has been converted into the Month column based on the original information in said column.

To do this, different methods and tools have been used, including a series of custom functions to edit the records to a homogeneous syntax and to search them for keywords that can be used to categorize each column.

The Country column has been considered of special interest, so work has been done to clean it in greater depth. To do this, a dictionary has been created from a csv file that relates the name of the country with its ISO3 code, which is the data that has finally been used to categorize the column.

### Analysis stage:
Once the dataframe has been cleaned, the efficiency of the work has been verified by carrying out a series of analyzes and studies based on the clean dataframe. Some of the most relevant outputs can be seen in the Wrangling & Analysis outputs section of this document.

To carry out these analyzes I have made extensive use of the Pandas methods, groupby, get_dummies and corr(), in addition to other numpy functions.

I have also used the pyplot and seaborn libraries to represent some of the findings.
## Cleaning outputs
## Wrangling & Analysis outputs
