# CNStockAssistant #
CN Stock Assistant is a set of utility python scripts.
These scripts provide to anaylze the historical data and make the trade decision in China Stock Market.


## data source ##
* the stock data from yahoo
**Note: the month is from 0**
 + CCBC in China
 http://ichart.yahoo.com/table.csv?s=601939.ss&d=08&e=26&f=2015&g=d
 + CCBC in HongKong:
 http://ichart.yahoo.com/table.csv?s=0939.hk&d=08&e=26&f=2015&g=d
 + SCLQ in China
 http://ichart.yahoo.com/table.csv?s=600039.ss&d=07&e=28&f=2015&g=d
* currency
 + historical data
 http://www.federalreserve.gov/datadownload/Output.aspx?rel=H10&series=a6a0113179fdeb9c6fbcdc18575ec09c&lastObs=&from=10/27/2005&to=08/28/2015&filetype=csv&label=include&layout=seriescolumn
 + now
http://download.finance.yahoo.com/d/quotes.csv?e=.csv&f=sl1d1t1&s=CNYHKD=X

## some usuful sql commands for sqlite3 ##
* delete the table and import the data from csv file to sqlite database
<pre>
DROP TABLE database_name.table_name;
select * from sqlite_master;
CREATE TABLE ss601939(date date, open float, high float, low float, close float,volume int, adj float);
.separator ','
.import 601939ss.csv ss601939
delete from ss601939 where date='Date'
</pre>

