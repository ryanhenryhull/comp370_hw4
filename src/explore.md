## Details
Author: Ryan Hull, 261182310
Date: 26 September 2025
Class: COMP370
Purpose: Describe commands used to solve the data exploration part of homework 4

## Task 3

We can see how big the dataset is by using wc -l clean_dialog.csv to count the number of lines (here, 36860)
Similarly wc -w clean_dialog.csv counts words
Also, ls -lh will list the file size of your files in that directory

head clean_dialog.csv will reveal the top rows of the file, allowing us to understand the basic structure

To see how many episodes there are, we can pipe the first column using csvtool into unique and then count the number of lines:
csvtool col 1 clean_dialog.csv | uniq | wc -l
Note this includes the first row which are col titles, so the answer is result -1. Here, 197

Some issues with the data include the fact that the first row is column names - thus the first row must be excluded from
any analysis. Also, the My Little Pony Movie is technically not an episode, so we must confirm it's relevance to the data 
science questions.


## Task 4 (Analyzing speaker frequency)
We can use csvtool col 3 clean_dialog.csv | grep -c "Fluttershy" to count the number of times Fluttershy appears in the speaker column in order to complete this task.
