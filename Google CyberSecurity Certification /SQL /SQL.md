Links for documentation:

PDF: https://drive.google.com/file/d/1631_DEtXBrPFlVSufJefzGI-ZWHwRxFc/view?usp=sharing

DOCX: https://drive.google.com/file/d/1r4CuJdDyPM58DRFwCTwXELe36rA4h7df/view?usp=sharing

# Applying filters to SQL queries

## Descritpion

**SQL** (*Structured Query Language*) is a programming language which allows for fast querying and filtering of data bases. This concept sets in 2 main fundamental commands: 
  
- **Select**; 

- **From**;

To understand the logic of these commands we need to understand that a database is no more than a spreadsheet made of columns and lines. 

When we evoque the select command we will make reference to the columns we want to extract information from. In order to query more than one column, these must be separated by a coma (,) and in case we want to query all the columns in the database an asterisk (*) must be used. 

When we evoque the from command we will make reference to which database we want to extract these columns from. 

There are several commands which will help us refine our search, as an example: 

- **ORDER BY**: 

This command uses a column name to identify which column will be used in order to organize the answer provided. In its natural state the organization happens from lowest to highest number or A to Z. 

This can be applied to more than one column at once, being the second result impacted by the first. 

- **ORDER BY DESC**: 

This command provides the same result as the previous one, yet it changes the order of the organization. 

- **WHERE**: 

This command allows us to specify, from all the results we previously asked for in Select the ones we want to focus on search for. 

For this symbols like (= > < >= <= <>) are used.

- **LIKE**:

This command allows the use of wildcards to avoid inconsistencies. Since a name can be represented in a short form, with the use of % (percentage) the leftover of a string will be automatically pulled out. 

This command accepts the use of wildcard before and after the known string. 

**%** - For strings 

**_** - For single characters (being possible the usage of 2 _ ) 

- **BETWEEN**: 

This command allows you to search for ranges of numerical data, having an inclusive approach. It will include the first result from the specified starting point to the last result of the specified ending point. 

- **AND/OR/NOT**:

These commands are used in addition to *WHERE*. 

  **AND**: Will filter on two conditions, being exclusive, presenting less results. OR: Will filter on two conditions, although being inclusive , presenting more results 

  **NOT**: Will filter on the specific condition we presented, presenting only results which don't have to do with it. 

- **;** : 

Used in the the end of the query to sign it is finished. 

## Exmaples

For the next examples please refer to the following tables: 


**Table 1 ** - *log_in_attempts* 

---------------------------------------------------------------------
| event_id | username | login_name | country | ip_address | success | 
---------------------------------------------------------------------

**Table 2**  - *employees*

------------------------------------------------------------
| employee_id | device_id | username | department | office |
------------------------------------------------------------

**Retrieving after hours** - *Table 1* 

    SELECT * 
    FROM log_in_attempts 
    WHERE login_date > ‘18:00’
    ORDER BY event_id; 

**Retrieving login attempts on specific dates** - *Table 1* 

    SELECT * 
    FROM log_in_attempts 
    ORDER BY login_date, login_time; 

**Retrieve login attempts outside of Mexico** - *Table 1*

    SELECT * 
    FROM log_in_attempts 
    WHERE NOT country LIKE ‘Mex%’; 


**Retrieve employees in Marketing** - *Table 2*

    SELECT * 
    FROM employees 
    WHERE department = ‘marketing’; 

**Retrieve employees in Finance or Sales** - *Table 2*

    SELECT * 
    FROM employees 
    WHERE department = ‘marketing’ OR department = ‘sales’; 

**Retrieve all employees not in IT** - *Table 2*

    SELECT * 
    FROM employees 
    WHERE NOT department = ‘IT’; 

## Summary 

SQL is a very intuitive language. It does not take a great amount of effort to give the first successful steps, unlike other languages. Yet it is also easy to fall into misuse due to lack of practice. 

Online exercises are recommended, try to practice it every week, even if only for 1h in separate days.

## Exercises

- **Wise Owl** - https://www.wiseowl.co.uk/sql/exercises/standard/
- **Learn SQL** - https://www.sql-practice.com/
- **Pracity** - https://practity.com/sql-3/
