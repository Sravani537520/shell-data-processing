# Shell Data Processing

## Retrieve Text with curl
1. [Data url](https://hadoop.apache.org/docs/r1.2.1/hdfs_design.html)
2. This curl command is used to retrieve the page text
``` curl "https://hadoop.apache.org/docs/r1.2.1/hdfs_design.html" ```
3. This curl command is used to return the page text and output to a file
``` curl "https://hadoop.apache.org/docs/r1.2.1/hdfs_design.html" -O data.txt```

## Process Text Data

1. ```tr ' ' '\12' < data.txt``` This command converts each line to individual words

2. Pipe the output to sort (send the results of one command as input into another command). SORT command sorts the contents of a text file, line by line. It supports sorting alphabetically, in reverse order, by number, by month and can also remove duplicates.
```tr ' ' '\12' < data.txt | sort ```
3. ``` tr ' ' '\12' < data.txt | sort | Uniq -c ``` The sorted output to uniq -c to count. It gives the output how many times it has found each entry.

4. Reduced output to sort with -nr flag most duplicates to bubble up to the top
``` tr ' ' '\12' < data.txt | sort | uniq -c | sort -nr ```
5. Redirect the output to result.txt. After executing this command the result will send to the new file result.txt
``` tr ' ' '\12' < data.txt | sort | uniq -c | sort -nr > result.txt ```
6. When we hit the up arrow in bash it will get the previous command we have used.
7. -n means numeric-value (it compares according to string numeric value)
8. -r means reverse (it reverse the result of comparisons sort according to WORD:)
9. Only one dash used for single letter flag 
10. Two dashes are used for long flags which are used for descriptive options.


## Understand Important Bash commands (>, >>, |, cat)
1. ```ls > filelist.txt``` to redirect the contents of your directory into a file. list of contents in the directory is saved to the filelist.txt
2. ```ls >> filelist.txt``` it appends lists of contents to the file rather than overwriting the data.
3. ```ls > temp.txt``` it sends the results to a new file temp.txt.
4. cat temp.txt it displays the content of the temp.txt.

