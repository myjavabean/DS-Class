### Lesson 04 Homework: Command Line Chipotle
1. Look at the head and the tail of **chipotle.tsv** in the **data** subdirectory of this repo. Think for a minute about how the data is structured. What do you think each column means? What do you think each row means? Tell me! (If you're unsure, look at more of the file contents.)  *Answer*:
  - Use command **`head -5 chipotle.tsv`** to look the first 5 lines, and use **`tail chipotle.tsv`** to look the last 10 lines of the file
  - The column names describe an order: _order id, quantity, item name, choice description_ and _item price_
  - Each row represents the item(s) ordered in a particular order (associated with an unique order id); 

2. How many orders do there appear to be?  *Answer*:
  - The first column is the order id, cound the uniqe order id with command: **`cut -f1 chipotle.tsv | sort | uniq | wc -l`** which gives 1835, then **minus 1** for column header, so the total unique orders id is **1834**.
  
3. How many lines are in this file?  *Answer*:
  - Use command: **`cat chipotle.tsv | wc -l`**, gives **4623**, which includes column header line

4. Which burrito is more popular, steak or chicken?  *Answer*: **Chicken Burrit** is popular!
  - command `cut -f2,3 chipotle.txt|grep 'Steak Burrito'|sort|uniq -c` outputs:
    * 352, 1,	Steak Burrito
    * 14, 2, Steak Burrito
    * 2, 3,	Steak Burrito

    351 order each has 1 Steak Burrito, 14 orders each has 2 Steak Burritos, 2 orders each has 3 Steak Burritos, so total is         **352*1+14*2+2*3=386**

  - command `cut -f2,3 chipotle.txt|grep 'Chicken Burrito'|sort|uniq -c` outputs:
    * 521, 1,	Chicken Burrit
    * 28, 2, Chicken Burrito
    * 2, 3,	Chicken Burrito
    * 2, 4,	Chicken Burrito
      
    521 orders each has 1 Chicken Burrit, 28 orders each has 2 Chicken Burritos, 2 orders each has 3 Chicken Buritos, and 2 orders each has 
  4 Chicken Burritos, so total is **521*1+28*2+2*3+2*4=591**

5. Do chicken burritos more often have black beans or pinto beans?  *Answer*: more often have **Black Beans**
  - command `cat chipotle.txt|grep 'Chicken Burrito'|grep 'Black Beans'|cut -f2,3|sort|uniq -c` output:
    * 261, 1,	Chicken Burrito
    * 19, 2,	Chicken Burrito
    * 2, 4,	Chicken Burrito
    
    Total of Black Beans Chicken Burrito is **261*1+19*2+2*4=307**
  
  -  command `cat chipotle.txt|grep 'Chicken Burrito'|grep 'Pinto Beans'|cut -f2,3|sort|uniq -c` output:
    * 102, 1,	Chicken Burrito
    * 3, 2,	Chicken Burrito
    
    Total of Pinto Beans Chicken Burrito is **102*1+3*2=108**
  
6. Make a list of all of the CSV or TSV files in the [our class repo] (https://github.com/ga-students/DS-SEA-3). repo (using a single command). You will be working on your local repo on your laptop. Think about how wildcard characters can help you with this task.
  - pwd -> /Users/myusername/desktop/GA-School-DS/DS-Class/DS-Class
  - `ls -lr ../DS-SEA-06/data/*.tsv ../DS-SEA-06/data/*.csv` -> all the CSV or TSV files

7. Optional: Use the the command line to discover something "interesting" about the Chipotle data. Try using the commands from the "advanced" section!


