xl_strip_null_rows is designed to solve a specific problem - Excel sheets with
a huge number of blank rows after the real data, often up to the maximum
allowable number of rows, 1,048,576. Stripping out these empty rows in Excel
is often difficult or impossible because of the massive size in memory such an
Excel file takes, slowing manipulations to a crawl. This program aims to do
that, stripping out blank rows in a much more efficient fashion, approximately
100x as fast as in Excel.

The algorthim used is limited. It iterates over all the Worksheets in the
Workbook. In each Worksheet, it reads each cell in the first column
sequentially from top to bottom. When it finds the FIRST blank/null cell, it
then copies the all the rows above that blank/null cell, and puts them in a
brand-new Workbook and identically named Worksheet. Note that all formatting,
formulas, charts, etc. are not preserved in the copy; only the values. Note
also that a stray blank row will cause the program to ignore all the rows
(even if non-blank) below it. It also makes no attempt to strip away or detect
empty columns. In the future, we may add additional options for these use
cases.
