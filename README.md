# 🦈🩸Data cleaning & wrangling project - Sharks🩸🦈
![Alt text](https://static1.colliderimages.com/wordpress/wp-content/uploads/2023/06/jaws-movies-ranked-worst-to-best.jpg?q=50&fit=contain&w=1140&h=&dpr=1.5)
## Description
This project focuses on cleaning and wrangling a database sourced from the [Sharks dataset](https://www.kaggle.com/datasets/teajay/global-shark-attacks), containing records of shark attacks spanning from 1703 to 2018. The dataset's complexity arises from inconsistent attributes and a substantial number of null values.

The cleaning process involves establishing homogenization criteria, resulting in a DataFrame suitable for various analyses based on relevant data from the document. Additionally, post-cleaning analyses have been conducted using the refined DataFrame.

## Contents
The contents of the project are as follows:
- [src folder](https://github.com/arromeral/w2pandas_arromeral/tree/main/src):
  - [jaws.ipynb](https://github.com/arromeral/w2pandas_arromeral/blob/main/src/jaws.ipynb): Jupyter notebook containing the main code for cleaning and obtaining results.
  - [funclean.ipynb](https://github.com/arromeral/w2pandas_arromeral/blob/main/src/funclean.ipynb): Jupyter notebook with custom functions for cleaning and categorizing columns used in jaws.ipynb.
- [images](https://github.com/arromeral/w2pandas_arromeral/tree/main/images): Folder containing charts obtained during the analysis.
- [attacks.csv](https://github.com/arromeral/w2pandas_arromeral/blob/main/attacks.csv): Original CSV document with raw data.
- [attacks_clean.csv](https://github.com/arromeral/w2pandas_arromeral/blob/main/attacks_clean.csv): Final CSV document exported with clean data.
- [paises.csv](https://github.com/arromeral/w2pandas_arromeral/blob/main/paises.csv): CSV document containing ISO2 and ISO3 codes of most countries and their names in several languages.
- 
## Methodology
### Cleaning stage:

#### Examining & undestanding
The initial phase involved using Pandas methods like .shape() and .info() to determine DataFrame size, data types, and columns with null values. Additionally, a custom checknan function was utilized to visualize the distribution of null values in rows and columns.
![check_nan](https://github.com/arromeral/w2pandas_arromeral/assets/138980560/f6faaff1-99a4-49b3-bd97-aa67dd17315c)

#### Improving syntax
To enhance data usability, certain column names were modified by removing spaces and unnecessary characters, making them more understandable. The datatype of some columns was also adjusted, and data in similar columns was homogenized using the .rename() method.
#### Eliminating useless information
Records with a majority of null values across columns were removed, significantly reducing the DataFrame size. Columns with a substantial number of nulls were repurposed to store more meaningful data, such as the number of nulls per row (*num_nan column*).
#### Improving accessibility to data
Null values in relevant records were replaced with "unknown" to facilitate future analyses. The focus was on cleaning columns crucial for studies, such as **Country, Sex, Activity, Species, Time, or Fatal,** by categorizing each column and reducing the number of unique values.

The **Country** column underwent special attention, utilizing a dictionary created from a CSV file correlating country names with their ISO3 codes for better categorization.

### Analysis stage:
Post-cleaning, a series of analyses and studies were conducted using Pandas methods, including groupby, get_dummies, and corr(), along with other numpy functions. Visualization was achieved using pyplot and seaborn libraries.
## Cleaning outputs
- DataFrame size reduced **from 25723 rows to 5572.**
- Null values reduced to **0.**
### Categorization improvements
Reduction in the number of unique values/categories:
- **Country**: from 212 to 113.
- **Year:** from 249 to 216.
- **Sex:** from 6 to 3 (Male, Female & unknown).
- **Age:** from 157 to 82.
- **Fatal:** from 8 to 3 (Yes, No & unknown).
- **Time:** from 366 to 4 (morning, afternoon, night & unknown)
- **Species:** from 1549 to 342. (retaining and concentrating a significant number of records in the main species)
- **Activity:** from 1532 to 37.(retaining and concentrating a significant number of records in the main activities)
- **Month:** New column with 12 unique values(one for each month of the year)
  ## **IMPORTANT**
  During this homogenization process, 730 records containing relevant information about real attacks have been lost/deleted.
## Wrangling & Analysis outputs
The main studies carried out with the clean database and some of the relevant outputs are detailed below.
### **Annual distribution of attacks in countries with more than 30 records**
![Australia](https://github.com/arromeral/w2pandas_arromeral/assets/138980560/b90eb180-05ef-4886-b76e-f021e7ad181e)
![Sudáfrica](https://github.com/arromeral/w2pandas_arromeral/assets/138980560/94be5107-3194-42b8-a49c-a6acf5b9dbcb)
![USA](https://github.com/arromeral/w2pandas_arromeral/assets/138980560/3d44f15b-95b2-4e76-a0c0-9a4baf6b4703)
![Brasil](https://github.com/arromeral/w2pandas_arromeral/assets/138980560/bd7268eb-1540-416f-9378-7acda02f5554)
### **Percentages of attacks by sex in countries with more than 100 records**
![](https://github.com/arromeral/w2pandas_arromeral/assets/138980560/251b2786-80f4-4dda-858d-276a286f82b8)

### **Countries with the highest and lowest average age of victims (for countries with more than 40 records)**
- *UK maximum with **36.54** years*
- *Papua New Guinea the minimum with **21.18** years*
### **Search for correlations between sex and activity during the attack**
- MALES: **Surfing**
- FEMALES: **Swimming**
### **Search for correlations between sex and time of day**
- MALES: **Night (00-06 h)**
- FEMALES: **Afternoon (12-24 h)**
### **Representation of the percentage of FATALITY for some of the main shark species**
![White shark](https://github.com/arromeral/w2pandas_arromeral/assets/138980560/3aef3495-852d-4609-8de2-8214a2da7211)
![Tiger shark](https://github.com/arromeral/w2pandas_arromeral/assets/138980560/e9c1098c-e41c-4e30-ab99-325777d5c7ba)
![Bull shark](https://github.com/arromeral/w2pandas_arromeral/assets/138980560/8cc02205-af68-4d1f-943a-7920d977137d)
![Blue shark](https://github.com/arromeral/w2pandas_arromeral/assets/138980560/cb30f0db-2635-42ee-9ddd-818ada6e2ed9)
![Hammer shark](https://github.com/arromeral/w2pandas_arromeral/assets/138980560/0e2d6314-6892-4ad2-b97e-11641f2601d5)
### **Evolution of fatality rate since 1950**
![Fatality vs Year (1950-2018)](https://github.com/arromeral/w2pandas_arromeral/assets/138980560/76c2ba3f-05b1-4e81-8f32-d392bacefe96)



 
