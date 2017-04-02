## lesson 04 Homework: Command Line Chipotle
1. Look at the head and the tail of **chipotle.tsv** in the **data** subdirectory of this repo. Think for a minute about how the data is structured. What do you think each column means? What do you think each row means? Tell me! (If you're unsure, look at more of the file contents.) *Answer*:
  - Use command **`head -5 chipotle.tsv`** to look the first 5 lines, and use **`tail chipotle.tsv`** to look the last 10 lines of the file
  - The column names describe an order: _order id, quantity, item name, choice description_ and _item price_
  - Each row represents the item(s) ordered in a particular order (associated with an unique order id); 

2. How many orders do there appear to be? *Answer*:
  - The first column is the order id, cound the uniqe order id with command: **`cut -f1 chipotle.tsv | sort | uniq | wc -l`** which gives 1835, then **minus 1** for column header, so the total unique orders id is **1834**.
  
3. How many lines are in this file? *Answer*:
  - Use command: **`cat chipotle.tsv | wc -l`**, gives **4623**, which includes column header line

4. Which burrito is more popular, steak or chicken? *Answer*:
  - command `cut -f2,3 chipotle.txt|grep 'Steak Burrito'|sort|uniq -c` outputs:
    * 352 1	Steak Burrito
    * 14 2	Steak Burrito
    * 2 3	Steak Burrito
351 order each has 1 Steak Burrito, 14 orders each has 2 Steak Burritos, 2 orders each has 3 Steak Burritos, so total is       352*1+14*2+2*3=386

  - `cut -f2,3 chipotle.txt|grep 'Chicken Burrito'|sort|uniq -c` command outputs:
      521 1	Chicken Burrit
      28 2	Chicken Burrito
      2 3	Chicken Burrito
      2 4	Chicken Burrito
      521 orders each has 1 Chicken Burrit, 28 orders each has 2 Chicken Burritos, 2 orders each has 3 Chicken Buritos, and 2 orders each has 4 Chicken Burritos, so total is 521*1+28*2+2*3+2*4=591

 
 
 




Do chicken burritos more often have black beans or pinto beans?

Make a list of all of the CSV or TSV files in the [our class repo] (https://github.com/ga-students/DS-SEA-3). repo (using a single command). You will be working on your local repo on your laptop. Think about how wildcard characters can help you with this task.

Count the approximate number of occurrences of the word "dictionary" (regardless of case) across all files of [our class repo] (https://github.com/ga-students/DS-SEA-3).

Optional: Use the the command line to discover something "interesting" about the Chipotle data. Try using the commands from the "advanced" section!

See the following useful **_GitHub Flavor Markdown_** syntax:
- This is **inline code** like pip command: `sort file.txt| uniq | wc -l` which asked alot during the interview
- This is *inline code block*:
    ```
       ls -a
       grep -ni 'pandas*' *.*
       find . -name 'seattle' -print
    ```
- This is *** python function code block ***
    ``` 
    def function(x):
        return x**2    
    ```
- ~~WDI class not for me~~ __WDS is good__ for me!

**To do _list_**
* [x] study DS 04
* [ ] do homework
* [ ] movie time

__*Show me how the sorted list works:*__
1. Make code changes
   i. fix bugs ?????????????
  ii. add comments
 iii. format the code blocks
    * make indent consistency
    * make header bigger
2. Push my commits to gitHub
3. Open a pull request
  * Describe the changes ????????????
  * Mention all the members on the team
    * Ask feedback
    * Take neccessry action to the feedback

This is a link [Link to gitHub](http://gitbub.com)
