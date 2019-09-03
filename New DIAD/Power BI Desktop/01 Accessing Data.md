# Power BI Desktop – Accessing Data

In this section, you will import VanArsdel and its competitors USA sales data. Then you will import and merge sales data from other countries.

## Power BI Desktop - Get Dat

Let’s start with looking at the data files. The dataset contains sales data of VanArsdel and other competitors. We have 7 years of transaction data by day, product and zip code for each manufacturer. We are going to analyze data from 7 countries.

USA sales data is in a csv file located in /Data/USSales folder.

Sales of all other countries is in /Data/InternationalSales folder. Each country’s sales data is in a csv file in this folder.

Product, Geography and Manufacturer information is in an excel file in /Data/USSales/bi_dimensions.xlsx.

1. Open /Data/USSales/bi_dimensions.xlsx. Notice the first sheet has Product information. The sheet has a header and product data is in a named table. Also notice Category column has a bunch of empty cells.

Manufacturer sheet has data laid out across the sheet and with no column headers and it has a couple of blank rows and a note in row 7.

Geo sheet has geography information. The first couple of rows has data details. Actual data starts from row 4.

We will start by connecting to data from these different files and perform data cleaning and transformation operations.

2.  If you don’t have the Power BI Desktop open, launch it now.
3.  Select Already have a Power BI Account? Sign in option.
4.  Sign in using your Power BI credentials.
5.  Startup screen opens. Click on X on the top right corner of the dialog to close it.

Let’s set up the locale to US English, to make it convenient to go through the rest of this lab.

6.  From the ribbon, select File -> Options and settings -> Options.
7.  In the left panel of Options dialog, select Regional Settings.
8.  From the Locale drop down select English (United States).
9.  Select OK to close the dialog.

First step is to load data to Power BI Desktop. We will load USA Sales data which is in comma separated value (CSV) files.

10. From the ribbon, select Home -> Get Data.
11. Select Text/CSV.

**Note:** Power BI Desktop has the capability to connect to 70+ data sources. We are using csv and excel data files in this lab for simplicity.

12. Browse to DIAD\Data\USSales folder and select sales.csv.
13. Click Open.

Power BI detects the data type of each column. There are options to detect the data type based on the first 200 rows or based on the entire dataset or not detect it. Since our dataset is large and it will take time and resources to scan the complete data set, let’s leave the default option of selecting dataset based on the first 200 rows. After completing your selection, you have three options – Load, Edit or Cancel.

- Load, loads the data from the source into Power BI Desktop for you to start creating reports.
- Edit allows you to perform data shaping operations such as merging columns, adding additional columns, changing data types of columns as well as bringing in additional data.
- Cancel gets you back to the main canvas.

14. Click Edit as shown in the screenshot. A new window opens. You should be in the Query Editor window as shown in the screenshot to the right. Query Editor is used to perform data shaping operations. Notice the sales file you connected to shows as a query in the left panel. You see a preview of the data in the center panel. Power BI predicts data type of each field (based on the first 200 rows) which is indicated next to the column header. In the right panel, steps that Query Editor performs are recorded.

**Note:** You will be bringing in sales data from other countries as well as performing certain data shaping operations.

15. Notice Power BI has set Zip field to data type Whole Number. To ensure that Zip codes which start with zero don’t lose the leading zero, we will format them as text. Highlight the Zip column. From the ribbon, select Home -> Data Type and update it to Text. 16. Change Column Type dialog opens. Select Replace Current button which overwrites Power BI’s predicted datatype.

Now let’s get the data that is in excel source file.

17. From the ribbon, select Home -> New Source -> Excel.
18. Browse to DIAD\Data\USSales folder and select bi_dimensions.xlsx.

Navigator dialog opens.

19. Navigator dialog lists 3 sheets that are in the excel workbook. It also lists the Product named table. Select product from the left panel and in preview panel notice the first row is the header. This is not part of the data.
20. Unselect product from the left panel. Select Product_Table. Notice this has only the contents of the named table. This is the data we need.

**Note:** Table names are differentiated from Worksheet names by using different icons.

21. From the left panel, select geo. In the preview panel notice the first couple of rows are headers that are not part of the data. We will remove them shortly.
22. From the left panel, select manufacturer. In the preview panel notice the last couple of rows are footers that are not part of the data. We will remove them shortly.
23. Select OK. (Make sure Product_Table, geo and manufacturer are selected in the left panel) Notice all 3 sheets are added as queries in the Query Editor.

## Power BI Desktop - Adding additional data

International subsidiaries have agreed to provide their sales data so that the company’s sales can be analyzed together. You’ve created a folder where they each put their data.

To analyze all the data together you will want to import the new data from each of the subsidiaries and combine it with the US Sales you loaded earlier. You can load the files one at a time similar to the US Sales but Power BI provides an easier way to load all the files in a folder together.

24. Click on the New Source drop down in the Home menu tab of the Query Editor.
25. Select More… as shown in the figure.

Get Data dialog opens.

26. In the Get Data dialog select Folder as shown in the diagram.
27. Click Connect.

Folder dialog opens.

28. Click Browse… button.
29. In the Browse for Folder dialog navigate to the location where you unzipped the class files.
30. Open the DIAD folder.
31. Open the Data folder.
32. Select the InternationalSales folder.
33. Click OK (to close the Browse for Folder dialog box).
34. Click OK (to close the Folder dialog box).

**Note:** This approach will load all files in the folder. This is useful when you have a group that puts files on an ftp site each month and you are not always sure of the names of the files or the number of files. All the files must be of the same file type with columns in the same order. Dialog displays the list of files in the folder.

35. Since we want to combine data, click Combine & Edit.

**Note:** Date accessed, Date modified and Date created might be different compared to the dates displayed in the screenshot.

Combine Files dialog opens. By default, Power BI again detects the data type based on the first 200 rows. Notice there is an option to select various file Delimiters. The file we are working with is Comma delimited, so let’s leave Delimiter option as Comma. There is also an option to select each individual file in the folder (using Example File dropdown) to validate the format of the files.

36. Select OK.

You will be in the Query Editor window with a new query called InternationalSales.

37. If you do not see the Queries pane on left, click on the > icon to expand.
38. If you do not see the Query Settings pane on the right as shown in the figure, click on View in the ribbon and click Query Settings to see the pane.
39. Click on the Query InternationalSales.

Notice that column Zip is of type Whole Number. Based on the first 200 rows Power BI thinks Zip is of type Whole Number. But zip code could be alpha numeric in some countries or leading zeros (similar to USA data). If we do not change the data type, we will see an error when we load the data shortly. So, let’s change Zip to data type Text.

40. Highlight the Zip column and change the Data Type to Text.
41. Change Column Type dialog opens. Select Replace Current button.

In Queries panel, notice Transform File from InternationalSales folder is created. This contains the function used to load each of the files in the folder.

If you compare InternationalSales and sales table, you will see the InternationalSales table contains two new columns, Source.Name and Country.

42. We do not need Source.Name column. Select Source.Name column. From the ribbon, select Home -> Remove Columns -> Remove Columns.
43. Click on the drop down next to Country column to see the unique values.
44. You will only see Australia as shown in the figure. By default, Power BI only loads the first 1000 rows. Click on Load more to validate you have data from various countries included.

You will see the countries, Australia, Canada, Germany, Japan, Mexico and Nigeria.

45. Click OK.

**Note:** You can perform various types of filters, sorting operations using the drop down to verify the imported data.
