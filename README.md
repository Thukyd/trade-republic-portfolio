# 0.2 | TradeRepublic - PDF Converter for Portfolio Performance
# a) Description
This tool should help to keep the overview of the transactions within TradeRepublic. In TR there is the possibility to export all orders as PDF. For testing purposes the import and export is currently only possible with G-Drive. Alternatives are on the todo list. 

## Output A: Master Sheet
The master sheet lists all previous transactions from the PDFs. 

## Output B: Delta Sheet (dated)
The delta sheet contains all new transactions that have been added since the script was last executed. These are intended to be imported into Portfolio Performance. 

# b) Setup
*   optimized for Google Colab (https://colab.research.google.com/)
*   TradeRepublic statements will be imported via GoogleDrive. All PDF files shoule be in a single folder. You need to configure the path to your G-Drive before usage (see: gdrive_path) 
*   export .csv optimized for "Portfolio Performance" (https://www.portfolio-performance.info/)

# c) Options to customize
- for different data sources, see: https://colab.research.google.com/notebooks/io.ipynb
- in order to create different data structures, take a look at "Examples for extracted fields". 

# d) Further Information
## Handling of costs statements
*   "Kosten des Wertpapierkaufs/verkaufs" are be considered.
*   "Kosten während der Haltedauer (pro Jahr)" are not extracted and therefore do not appear the sheets. 

## Deposits & Withdrawls
* deposits and withdrawals to the depot are not recorded in PDF format. Therefore they are not taken into account and must be entered by hand if necessary.

## "Order" ID PDF documents
* each TradeRepublic document has got a "order" number. This is extracted and stored in the field "Notiz". It serves to prevent duplicate entries.  

# e) Backlog
## Open
* create sheets for portfolio performance in .csv format
* offer alternatives to G-Drive import/export

## To be fixed
- define "add to delta" by order number - not by row alone
- examples: calculate_stock_value() => conversion of german/international number system
- limit reading operations for google sheets https://github.com/burnash/gspread/issues/583
- examples: name 
- examples: transaction type & order volume

# f) Changelog 
## 0.1
* extract G-Drive folder of TradeRepublic PDFs
* create data structure (for Portfolio Performance or other purposes)
* generate master sheet of all transactions
* generate delta sheet for new transactions (base for TradeRepublic import)

## 0.2
- fixed | sort extracted transactions by date
- fixed | double entries of table lables in delta sheet
