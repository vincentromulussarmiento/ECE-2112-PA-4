# ECE-2112-PA-4
Made by: Vincent Romulus S. Sarmiento | 2ECE-D A.Y.2026-2027

This repository contains the jupyter notebook file for our Programming Assignment 4 in ECE2112, as well as the README file that explains the code more thoroughly.

In this programming assignment, we were provided with a CSV file that contains a table of students and their data such as their name, hometown, and their scores in the different exams of the boards. The assignment focuses on the utilization of the matplot library to visualize the data of the CSV in numerous ways. The assignment also incorporated some pandas functions to ensure mastery.  

## Importation of the Pandas Library
The Pandas library contains various functions that allows the creation and manipulation of Data Series and Frames. By running the code below, the library is automatically imported into the code.
``` Python
import pandas as pd
```

## Reading CSV files 
One of the functions of the Pandas library is the reading of CSV files. This type of file contains data encoded in a particular table (either a series or a frame) for easier distribution of data samples instead of people providing themselves their own tabular data. The function is written as:
``` Python
_____ = pd.read_excel('_____')
```
Wherein the first blank refers to the variable name that you want to assign your data to, and the second blank is the exact filename of your csv file.

An example is shown below:
``` Python
eceboardexam2 = pd.read_excel('board2.xlsx')
```

## Importation of the MATPLOT Library
The matplot library contains functions that allows the production and manipulation of different graphical visualizations. This is primarily used when you want to visualize your data in a way that can be easily understood by almost everyone. To import this library in a code, run the code below:
``` Python
import matplotlib.pyplot as plt
```

## A. Visayas Communication Data Frame
Create a Data Frame assigned under the variable VisComm. This particular Data Frame should contain the students that meets the following: resides in Visayas and took Communications as their track. After finding those students, only display their name, gender, exam scores in math and electronics, and the average of their exam scores.

Functions(s), Method(s), and/or Operation(s) used:

- .mean(axis=1) - 
- .loc() - This function is used to locate certain elements of a Data Series or Frame. It has 2 parts, the rows and the columns. .loc means that it accepts row inputs not just by their index number, but also their exact value. Therefore, it is more versatile than the other locating function which is .iloc
- == - This is the equality operator. It is used when you want to check if a variable is equal to something. When used in a condition, if the two aren't equal, it would result to false, which might lead to a particular condition to not be met.
- & - This is the AND operator. This operator requires at least 2 propositions so that there is something to compare. These propositions have to be true so that it would be accepted by the operator. When applied as a condition, if there is even 1 false, the operator wouldn't store that data to a given variable.

Below is the completed code: 
``` Python
eceboardexam2['Average'] = eceboardexam2[['Math', 'GEAS', 'Electronics', 'Communication']].mean(axis=1)
VisComm = eceboardexam2.loc[(eceboardexam2['Hometown'] == 'Visayas') & (eceboardexam2['Track'] == 'Communication')]
VisComm[['Name', 'Gender', 'Math', 'Electronics', 'Average']]
```

## B. Visayas Female Data Frame
Create a Data Frame under the variable VisFemale. This Data Frame should contain the students that meets the following: resides in Visayas, a Female, and an average exam score of atleast 60. After finding said students, only display their name, track, exam scores in GEAS and electronics, and the average of their exam scores.

Functions(s), Method(s), and/or Operation(s) used:

- .loc() - This function is used to locate particular elements of a table. It is different from .iloc because .loc also accepts row and column inputs by their value instead of just their index number.
- == - This is the equality operator. When used in a condition, if a variable isn't equal to something, it would result to false.
- & - This is the AND operator, this accepts at least 2 propositions. In a condition, both propositions have to be true so that the data would be stored to a variable.

Below is the completed code: 
``` Python
VisFemale = eceboardexam2.loc[(eceboardexam2['Hometown'] == 'Visayas')
                            & (eceboardexam2['Gender'] == 'Female') 
                            & (eceboardexam2['Average'] >= 60)]
VisFemale[['Name', 'Track', 'GEAS', 'Electronics', 'Average']]          
```

## C. Category-Average Visualization
task

Functions(s), Method(s), and/or Operation(s) used:

- dawdasd

Below is the completed code: 
``` Python

```

Repository Updates: 
September 17 - Created Repository

September 17 - Finished the README, and uploaded the necessary files
