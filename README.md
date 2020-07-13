#   0.1 | TradeRepublic - PDF Converter for Portfolio Performance
# a) Description
Python script to extract TradeRepublic transaction statements (PDF) and generate .csv overview sheets (Portfolio Performance).For testing purposes the import and export is currently only possible with G-Drive. Alternatives are on the todo list. 

## Output A: Master Sheet
The master sheet lists all previous transactions from the PDFs. 

## Output B: Delta Sheet (dated)
The delta sheet contains all new transactions that have been added since the script was last executed. These are intended to be imported into Portfolio Performance. 

# b) Setup
*   Optimized for Google Colab (https://colab.research.google.com/)
*   TradeRepublic statements will be imported via GoogleDrive. All PDF files shoule be in a single folder. You need to configure the path to your G-Drive before usage (see: gdrive_path) 
*   Export .csv optimized for "Portfolio Performance" (https://www.portfolio-performance.info/)

# c) Options to customize
- for different data sources, see: https://colab.research.google.com/notebooks/io.ipynb
- in order to create different data structures, take a look at "Examples for extracted fields". 

# d) Further Information
## Handling of costs statements
*   "Kosten des Wertpapierkaufs/verkaufs" are be considered.
*   "Kosten während der Haltedauer (pro Jahr)" are not extracted and therefore do not appear the sheets. 

## Deposits & Withdrawls
* Deposits and withdrawals to the depot are not recorded in PDF format. Therefore they are not taken into account and must be entered by hand if necessary.

## "Order" ID PDF documents
* Each TradeRepublic document has got a "order" number. This is extracted and stored in the field "Notiz". It serves to prevent duplicate entries.  

# e) Todos
## Done
* Extract G-Drive folder of TradeRepublic PDFs
* Create data structure (for Portfolio Performance or other purposes)
* Generate master sheet of all transactions
* Generate delta sheet for new transactions (basis for Trade Republic Import)

## Open
* Create sheets for portfolio performance in .csv format
* Offer alternatives to G-Drive import/export

## To be fixed
- calculate_stock_value() => conversion of german/international number system
- table labelling for delta sheet => not added unless master sheet is new
- name function => str length error
