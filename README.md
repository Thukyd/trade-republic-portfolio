# **TradeRepublic Portfolio won't be developed further** 
*   a cli alternative can be found here: https://github.com/marzzzello/pytr

# **0.4 | TradeRepublic Portfolio** 
# *PDF Converter for Portfolio Performance & Investing.com*
# a) Description
This tool should help to keep the overview of the transactions within TradeRepublic. In TR there is the possibility to export all orders as PDF. For testing purposes the import and export is currently only possible with G-Drive. Alternatives are on the todo list. 


## Output A: Master Sheet
The master sheet lists all previous transactions from the PDFs. 

## Output B: Delta Sheet
The delta sheet contains all new transactions that have been added since the script was last executed. These are intended to be imported into Portfolio Performance and Investing.com. Delta sheets are dated.

## Output C: Portfolio Sheet
The portfolio sheet contains an overview of all open positions with basic information as average purchase price. The three fields "Stop Preis", "Limit Preis" and "Strategie" are for notes, which are kept at each execution of the script, if the corresponding position is still in the portfolio. 

## Scope 
*   optimized for Google Colab (https://colab.research.google.com/)
*   export optimized for "Portfolio Performance" (https://www.portfolio-performance.info/) and "Investing.com" (https://de.investing.com/)
*   for further information about the import at "Investing.com", see: https://www.investing-support.com/hc/en-us/articles/360000265217-Import-Portfolio-Holdings 


# b) Configuration
## G-Drive Path
*   TradeRepublic statements will be imported via GoogleDrive. All PDF files shoule be in a single folder. You need to configure the path to your G-Drive before usage (see: "Configurations - to be defined by user")

# c) Options to customize
- for different data sources, see: https://colab.research.google.com/notebooks/io.ipynb
- in order to create different data structures, take a look at "Examples for extracted fields". 

# d) Further Information
## Handling of costs statements
*   "Kosten des Wertpapierkaufs/verkaufs" are be considered.
*   "Kosten während der Haltedauer (pro Jahr)" are not extracted and therefore do not appear the sheets. 

## Deposits & Withdrawls
* deposits and withdrawals to the depot are not recorded in PDF format. Therefore they are not taken into account and must be entered by hand if necessary.

## "Order" in Trade Republic documents
* each TradeRepublic document has got a "order" number. This is extracted and stored in the field "Notiz". It serves to prevent duplicate entries.  

# e) Backlog
## Open
* create sheets for portfolio performance in .csv format
* offer alternatives to G-Drive import/export

## To be fixed
- ...

# f) Changelog 
## 0.1
* extract G-Drive folder of TradeRepublic PDFs
* create data structure (for Portfolio Performance or other purposes)
* generate master sheet of all transactions
* generate delta sheet for new transactions (base for TradeRepublic import)

## 0.2
- fixed | sort extracted transactions by date
- fixed | double entries of table lables in delta sheet

## 0.3
- add ticker symbol via finnhub api (requires your own api key)
- fixed | calculate purchase price
- add values to sheet ("Kaufkurs", "Gebühren")
- data structure for Investing.com import

## 0.4
- full refactoring (new class structure)
- add current portfolio as output option
- allow data enrichment of extracted data
- note already extracted PDFs
