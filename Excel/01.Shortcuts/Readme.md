## Excel Shortcuts

## Excel Formulas

 -  Applying table format
   
    - Ctrl+ t  -> for Table adding table use ctrl+A and press ctrl+T
- remove table format

   -  click on any cell -> ctrl+A and press right click -> select table -> convert to range-> now select an empy cell -> in home ribbon select-> format painter brush->now ctrl+a

-   select the entire data using the shortcuts
    
     -  click on the cell (start) press ctrl+shift+right arrow(->) it will select entire row
     
     - If we click Ctrl+Shift+down arrow, it will select all columns
- Moving inside the sheet
   -  Ctrl+up arrow -> click on any cell by pressing Ctrl+uparrow will take you topmost and vice versa
   -    Ctrl+down arrow will take you down 
   -    Ctrl+Left Arrow takes you to the most left side 
   -    Ctrl+right arrow will take you to the right 

- Adding row
   - select the row that we want to add a row above, use Ctrl+Shift + to add a row

- Delete row
   - select the row you want to delete, now press Ctrl - to delete the entire row
   - for multiple rows, select the rows that need to be deleted and press Ctrl+  -
     
- Adding column
   - select the column that we want to add a column next to it and press ctrl+ shift+ + it will add a column

- Delete a column
   -  select the column you want to delete and press Ctrl+ -
   -  We can delete multiple columns at once by selecting multiple columns and pressing Ctrl+ -
 
- Make headers visible while scrolling
  -  select the column -> ctrl+leftarrow -> in the view ribbon ->we have freeze panes -> select freeze top row, now we can scroll any rows, still the header is visible
  -  To make it normal ->ctrl+leftarrow -> in the view ribbon ->we have freeze panes -> select unfreeze rows, it makes it normal.
 

  ### Auto-adjusting rows and columns

The default width of the row cell is 16, and the column cell is 10
- select the row/ column, right click to see the width

- select the data Ctrl+ A
- now for rows we use `Alt + H + O+ A`
- now for columns we use `Alt + H + O + I`



### Data Entry
   - First  type the column names and select the columns  using ctrl+shift+leftarrow or using the mouse.
   -  Now, press Alt+D+O. This will open like a form by using tab we can switch to next,  by pressing enter will make an entry


### Formulas

##### Basic mathematical operations on rows

- for adding entire rows  `Alt =` -> it automatically applies sum formula  on row
- for average `alt+H+U+A` -> it automatically applies average  formula on row
- for maximum  `Alt+h+m` ->it automatically applies maximum  formula on row
- For minimum  `Alt+h+I` -> It aautomatically applies minimum formula in row
-  for count
   - we use `=Count(cell range:cell range) ` count -> it only counts numbers
   -   we use `=CountA(cell range:cell range)` counta -> counts everything except blanks
   -   we use `=countBLANK(cell range:cell range)` countblank -> counts only blank cells


### Text formulas

- Upper letter :- we use `=upper(cell range)`
- lower letter :- we use `=LOWER(cell range)`
- Proper text(ex: Microsoft Excel) : - we use `=PROPER(cell range)`


#### Extracting text (left,mid,right)

- left :- by using this we get left characters `=LEFT(text,char) `
- right :- by using this we get right characters `=RIGHT(text,char)`
- mid :- by using this we can get mid characters `=MID(text,start_num(index),text_char)`

### Date to Text

- we use TEXT function to convert date into text.
- ex: 15-03-2026  -> to find out what day it was
   - we use `=TEXT(cell range,"DDDD")` -> saturday
   - we use `=TEXT(cell range,"MMMM")` -> march
   - we use `=TEXT(cell range,"yyyy")` -> 2026


 - Edate : - edate will give you the exact date in the given range, best for finding due dates
 - `=EDATE(cell range,month)` -> note we will get number so we  have to change -> in number section -> change general -> short date
 
- Day and Days
  -  if it is DAY -> we get single value which is day it self ex: 03-05-2026 -> `=DAY(date)` -> 3
  -  If it is DAYS -> we get the difference between days  :- `=DAYS(end_date,start_date)` -> ex: 01-03-2026 to 10-03-2026 -> 10

- NETWORKDAYS
    in excel
   - working day (Mon-fri)
   -  Weekend(sat,sun)
 
  - By using this networkdays exxcel automatically removes weekends
  - `=NETWORKDAYS(startdate,enddate)`  -> -> ex: 01-03-2026 to 10-03-2026 -> 10 days but we get only 7 cause it removes weekends

 ### logical formulas


 - IF check the condition

   `=IF(logical_test condition,value if true,value if false)` -> it checks the condition and assign the values

- SUMIF  -> if your are using in range better to fix that with F4
   -  if we need to find a person how much sales have done in group of people
      - range -> enitre sales persons name
      - criteria -> sales person name
      - sum range -> amount
  
   - `=SUMIF(range,criteria,sumrange)` ->
 
- AVERAGEIF  -> if your are using in range better to fix that with F4
   -  if we need to find a person how much sales average  have done in group of people
      - range -> enitre sales persons name
      - criteria -> sales person name
      -  rangevalue -> amount
  
   - `=AVERAGEIF(range,criteria,rangevalue)` ->
 
-- COUNTIF  -> if your are using in range better to fix that with F4
   -  if we need to find  how many times does the person    have in group of people
      - range -> enitre sales persons name
      - criteria -> sales person name
      - `=COUNTIF(range,criteria)`
    


  ### Finding the data using lookups

  - VlooKup
    - lookup value -> what to find
    - table array -> complete table   -> try to avoid serial numbers
    - column index -> answer column
    - true/false -> true: proximate, false: absolute value

-`=VLOOKUP(lookupvalue,table array,column index_num, range->true/false)` -> ex: =Vlookup(personname,table array, 3,false)


  - Xlookup
     - lookup value -> criteria/what to find
     - lookup array ->  criteria entire column
     - return array -> answer column

    - `=Xlookup(lookupvalue,lookup array,return array)`  ex: - Xlookup(person name,persons column fix with F4,return column answer)

       
