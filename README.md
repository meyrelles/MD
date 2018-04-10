---
title: Veda Treasury Web Application
---

<br>
<br>
<br>
<p align="center">
  <img src="http://ultroneous.org/assets/veda.png"/>
</center>
<br>
<br>
<br>

# Veda Treasury
  
# Web Application

## Specifications and requirements book

----------

| | |
| --- | --- |
| **Work / project** | Veda treasury – web app – SRB |
| **Date** | 29/03/2018 |
| **Web developer team** | Spencer Campbell, Scott Campbell and Nuno de Meyrelles |
| **Software tester** | Shirley Norwood and Veda members |
| **Version** | 1.0 |

<div class="pagebreak"></div>

----------

# Index

 - [1 Introduction](#1-introduction)
 - [2 Technical Resume](#2-technical-resume)
 - [2.1 The current process](#21-the-current-process)
 - [2.2 The proposal](#22-the-proposal)
 - [2.3 Draft layout / user interface](#23-draft-layout-/-user-interface)
 - [3 Development](#3-development)
 - [3.1 1st main function](#311st-main-function)
 - [3.1.1 Insert sub-function](#311-insert-sub-function)
 - [3.1.2 Modify sub-function](#312-modify-sub-function)
 - [3.1.3 Delete sub-function](#313-delete-sub-function)
 - [3.2 2nd main function](#322nd-main-function)
 - [3.3 Database structure](#33-database-structure)
 - [3.3.1 Treasury records data table structure](#331-treasury-records-data-table-structure)
 - [3.3.2 Main data tables structure](#332-main-data-tables-structure)
 - [3.3.3 Database flow chart](#333-database-flow-chart)
 - [4 Timeline](#4-timeline)
 - [5 Risk management](#5-risk-management)
 - [6 Ruby on Rails](#6-Ruby-on-Rails)
 - [7 Conclusion](#7-conclusion)

<div class="pagebreak"></div>



----------
 
# 1 Introduction
This book of specifications and requirements (SRB) is part of the Veda Treasury web application technical development.

Any part of this document may be changed to approach the real necessities of user friendly utilization -- for example, corrections to flow charts, chronograms, risk table and functionalities.

Any changes should be recorded in a specific document and in development journal and the developer team should be analyze the risk of change and update the necessary spreadsheets/documents.

----------

<div class="pagebreak"></div>

# 2 Technical Resume
The development process involves linking the current treasury system to the new implementation, keeping everything working as usual during the change to prevent any big surprises. Perhaps, in the near future it’s advisable to centralize all information in a database to simplify the development, backup and restore process.

Ruby will still be the main programming language to develop the Veda website and web applications, while keeping an open mind to change when necessary to improve the development experience.

## 2.1 The current process
Each Veda element has a google spreadsheet and keep it updated all time and the information is synchronized to web site, the users can change any entry any time and the information is replicated again to website.

At begin the process works properly. The Veda structure starts to increase and the processes must be changed and adapted to new reality, bring easy concepts to correct use of tools, keeping the work methods intact.

## 2.2 The proposal
Developer a simple web interface to mobile device to provide the follow operations:

- Register payments;
- Register receipts;
- Register exchange;
- List own movements;
- List global movements;
- Filter lists by user, description, word in description, data, type of operation;
- Chart expenses per month.

The list of operation can be updated by users inputs during the developer process.

## 2.3 Draft layout / user interface

| | | |
| --- | --- | --- |
| <p align="center"><img src="http://drive.google.com/uc?id=1EEbejvsNYOVf59BS4rN4Stx6lcDpgcUW"/></center> | <p align="center"><img src="http://drive.google.com/uc?id=1Z-O3k0Dl9Xj8D2pahLq7TvD-f-qU-JT8"/></center> | <p align="center"><img src="http://drive.google.com/uc?id=1Z-O3k0Dl9Xj8D2pahLq7TvD-f-qU-JT8"/></center> |
| Fig 1 - Web app payment layout | Fig 2 - Web app receipt layout | Fig 3 - Web app exchange layout |

----------

<div class="pagebreak"></div>

# 3 Development
The app will be divided in 2 main functions: 1st treasury data operations (input, update or delete); 2nd reporting/list movements per filters.

## 3.1 1st main function
This is the part of software to maintain treasury individual data. The user will be able to input, update and delete records from google spreadsheet to keep the information clear and readable.

It will appear in the web app menu option to update the data:

<br/>
<br/>

| | 
| --- | 
| <p align="center"><img src="http://drive.google.com/uc?id=1Io2_vi8vlRYg_SDVc8-UDH42oC0111Ko"/></center> | 
| Fig 4 - Web app Menu process |

### 3.1.1 Insert sub-function
The insert function is the option to the user input new records to google spreadsheet, selecting the option, listed in figure 5.

| | 
| --- | 
| <p align="center"><img src="http://drive.google.com/uc?id=13k7yieBJ1Q6stcRWuAyFzc7nDqkC4w8A"/></center> | 
| Fig 5 - Web app update data menu |

#### 3.1.1.1	Payment sub function
To insert a new payment the user just need to use the option “Payment”, insert the payment details and press the button SEND.

##### 3.1.1.1.1	 The process flow chart:

| | 
| --- | 
| <p align="center"><img src="http://drive.google.com/uc?id=1FCpxd132yuFW8m3_WOdasm8EYLfiX6QV"/></center> | 
| Fig 6 - Insert payment flow chart |

#### 3.1.1.2	Receipt sub function
To insert a new receipt the user just need to use the option “Receipt”, insert the receipt details and press the button SEND.

##### 3.1.1.2.1	 The process flow chart:

| | 
| --- | 
| <p align="center"><img src="http://drive.google.com/uc?id=1301_eTxlFzkc4OnKcj_UR1nR5ggNOTue"/></center> | 
| Fig 7 - Insert Receipt  flow chart |

#### 3.1.1.3 Exchange  sub function
To insert a new exchange the user just need to use the option “Exchange”, insert the exchange details and press the button SEND. In this option, the system will input two records in Spreadsheet, the first will subtract the amount from the source coinlog and the second line will add the amount to the new coinlog. 

##### 3.1.1.3.1 The process flow chart:

| | 
| --- | 
| <p align="center"><img src="http://drive.google.com/uc?id=1dzZfFHx5o_Dd7C5lps1kbboqg2m7td2f"/></center> | 
| Fig 8 - Insert Exchange flow chart |

### 3.1.2 Modify sub-function 
To change records, the user must go to reporting function, filter the data and select the movement to change.

After select the record, the web app opens the linked operation (payment, receipt, exchange) and the user just need to update the operation.
 
### 3.1.3 Delete sub-function 
To delete records, the user must go to reporting function, filter the data and select the movement to delete.

The web app will ask to user if he/she really wants delete the record X, after confirmation the system will delete the record in spreadsheet.

----------

<div class="pagebreak"></div>


## 3.2 2nd main function
This is the part of software to maintain treasury individual data. The user will be able to see the completed or filtered list of movements.

**It will be extremely important all user give inputs about the reports they want to see in Veda treasury.**


SPENCER INPUTS:

- How much money do we have, in total?
- How much money is available, and how much is already assigned to projects?
- When she has a request for money, who should she ask? (Who has it?)
- She also wants to be able to search, for example, how much money has a particular user spent on groceries?
- She would like a monthly report, like a bank statement.
- She would like to see a report of all the funds she has received.
- She wants it to be easy to check if the amount shown in the treasury is - the same as the amount in her physical wallet plus bank account.

## 3.3 Database structure

### 3.3.1 Treasury records data table structure

| Fields | Description | Data type |
| --- | --- | --- |
| UniqueID | User ID + auto increment sequential number | String |
| Date | User date | Date |
| Time | User time | Time |
| Timezone | Automatic by cell phone time zone | int |
| Description | Operation description | String |
| Reason | Operation reason | String |
| Coinbag | “The same like currency!!!!” | String |
| From | User select or fixed in pay option | String |
| To | User selecto or fixed in recieve option | String |
| Currency | User select | String |
| Amount | Amount value | Float |
| Celebrate | To celebrate | String |
| SystemDT | Auto datetime | Datetime |

<br>
<br>

### 3.3.2 Main data tables structure

#### 3.3.2.1 Veda users table structure

| Fields | Description | Data type |
| --- | --- | --- |
| Username | User name | String |
| Password | User Password | password |
| Surname | User surname | String |
| Givenname | User given name | String |
| Nickname | User nick name | String |
| Birthdate | User birthdate | Date |
| Birthtime | User birth time | Time |
| SpreadsheetLink | User Google spreadsheet link code | String |

<br>

#### 3.3.2.2 Veda reasons table structure

| Fields | Description | Data type |
| --- | --- | --- |
| ReasonID | Reason unique ID | String |
| Description | Description | String |

<br>

#### 3.3.2.3 Veda coinbag table structure

| Fields | Description | Data type |
| --- | --- | --- |
| CoinbagID | Coinbag unique ID | String |
| Description | Description | String |

<br>

#### 3.3.2.4 Veda currencies table structure

| Fields | Description | Data type |
| --- | --- | --- |
| CurrencyID | Currency unique ID | String |
| Description | Description | String |

<br>
<br>

### 3.3.3 Database flow chart


| | 
| --- | 
| <p align="center"><img src="http://drive.google.com/uc?id=1Sgu7wh3RbSUycB2NSkHe8KfOMzz8jUiV"/></center> | 
| Fig 9 - Database flow chart |

----------

<div class="pagebreak"></div>

# 4 Timeline

| Description | Time |
| --- | --- |
| Learn Ruby | 4 days |
| Develop database | 1 day |
| Develop 1st process | 3 days |
| Develop 2nd process | 4 days |
| Web app test | 2 days |
| Tuning | 2 days |
| Online | 1 day |
|  |  |
| Total | 17 days |

----------

<div class="pagebreak"></div>

# 5 Risk management

| Risk | Probability | Impact |
| --- | --- | --- |
| Web server without database agreement | Active | high |
| Veda users feedback / inputs | Active | middle |
| VWeb app device layout compatibility | Active | middle |


----------

<div class="pagebreak"></div>

# 6 Ruby on Rails

**Ruby on Rails**, or **Rails**, is a server-side web application framework written in Ruby under the MIT License. Rails is a model–view–controller (MVC) framework, providing default structures for a database, a web service, and web pages. It encourages and facilitates the use of web standards such as JSON or XML for data transfer, and HTML, CSS and JavaScript for display and user interfacing. In addition to MVC, Rails emphasizes the use of other well-known software engineering patterns and paradigms, including convention over configuration (CoC), don't repeat yourself (DRY), and the active record pattern.

Ruby on Rails' emergence in the 2000s greatly influenced web app development, through innovative features such as seamless database table creations, migrations, and scaffolding of views to enable rapid application development. Ruby on Rails' influence on other web frameworks remains apparent today, with many frameworks in other languages borrowing its ideas, including Django in Python, Laravel in PHP, Phoenix in Elixir, and Sails.js in Node.js.

----------

<div class="pagebreak"></div>

# 7 Conclusion
This development must care about the development itself in terms of delays in timeline, because everything will be produced by root level.

All work did during the project, must be kept well documented to prevent future interpreted problems.

This a open document, free to be update and commented by all members of Veda Coop. The SRB will be shared in google docs with comment and follow-up options.
