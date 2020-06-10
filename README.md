# To Do


## Section 1
- Each dataset is for each section and for question 1 part 1 we are to investigate for any data quality problems and propose generalisable, scalable methods to manage identified issues

### Question 1 part 1
- s1 transactions data has 6 columns
    - most columns are similar to the schema provided by the question however
    there is an additional column which is sales_date_id

#### Issues and solutions
1. There are 158 duplicated rows, this could be due to double entry of records
    - Rectified by clearing duplicated rows. As we specify only the duplicated rows, it means that the original rows are still kept
    - to see if there are even more than a double entry, we ran the method `.drop_duplicates` on the duplicated rows and we can see that there are indeed more than double entries as some records have more than 2 duplicates
    - In order to solve this issue, we create another dataframe with the duplicated rows removed

2. Investigate the dtypes of the data frame. sales_pieces is in <b>float</b> instead of <b>int</b>, sales date id is in <b>int</b> instead of <b>datetime</b>
    - converted to appropriate datatypes

3. Double entry purchase. There are duplicated receipt and sales_date records for the same type of ciggarete (show example)
    - Create a new column indicating that the sales receipt has a duplicate entry 

4. need to also filter out single packs that have partial sales as it makes no sense, only multipacks should have partial sales


##### Overall solution is to introduce a new function that can help with the entire process 

