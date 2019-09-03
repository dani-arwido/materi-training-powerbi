# Power BI Desktop - Importing Data

## Load Data

> 1.  If you don’t have the **Power BI Desktop open**, launch it now.
> 2.  Startup screen opens. Click on Sign In and sign in using your Power BI credentials. Signing in to Power BI Desktop helps later when you are publishing to Power BI Service.

   <img src="https://raw.githubusercontent.com/dani-arwido/materi-training-powerbi/master/Assets/>001. jpg"  width="600" height="300">

Let’s set up the locale to US English, to make it convenient to go through the rest of this lab.

> 3.  From the ribbon, select File -> Options and settings -> Options. 4. In the left panel of Options dialog, select Regional Settings. 5. From the Locale drop down select English (United States).
> 4.  In the left panel of Options dialog, select Regional Settings.
> 5.  From the Locale drop down select English (United States).

First step is to load data to Power BI Desktop. We will load USA Sales data which is in CSV files.

> 6.  From the ribbon, select Home -> Get Data. 7. Select Text/CSV
> 7.  Select Text/CSV.
> 8.  Browse to DIAD\Data\USSales folder and select bi_salesFact.csv.
> 9.  Click Open.

Power BI detects the data type of each column. There are options to detect the data type based on the first 200 rows or based on the entire dataset or not detect it. Since our dataset is large and it will take time and resources to scan the complete data set, let’s leave the default option of selecting dataset based on the first 200 rows. After completing your selection, you have three options – Load, Edit or Cancel.

- Load, loads the data from the source into Power BI Desktop for you to start creating reports.
- Edit allows you to perform data shaping operations such as merging columns, adding additional columns, changing data types of columns as well as bringing in additional data.
- Cancel gets you back to the main canvas.

> 10. Click Edit as shown in the diagram. Now you have loaded the Sales data into the file.

You should be in the Query Editor window as shown in the picture to the right. Notice data type of each field is indicated next to the column header.

**Note**: You will be bringing in sales data from other countries as well as performing certain data shaping operations.

> 11. Notice Power BI has set Zip field to data type Whole Number. To ensure that Zip codes which start with zero don’t lose the leading zero, we will format them as text. Highlight the Zip column and change the Data Type to Text. >12. Change Column Type dialog opens. Select Replace Current button.

Now let’s get the data that is in excel source file.

> 13. From the ribbon, select Home -> New Source -> Excel.
> 14. Browse to DIAD\Data\USSales folder and select bi_dimensions.xlsx.

Navigator dialog opens.

> 15. In the Navigator window select all the tables. Select each table to preview the columns and rows.

**Note**: The first four items are the named Excel Tables and the second set are the Excel Worksheet names. Table names are differentiated from Worksheet names by using different icons. The preview window retrieves a sample of data and shows the data for you to understand the columns, data type and the data.

> 16. Click OK to edit these tables in the query editor.

Notice 4 new queries are added to the query editor.

## Power BI Desktop - Adding additional data

Your international subsidiaries have agreed to provide their sales data so that the company’s sales can be analyzed together. You’ve created a folder where they will each put their data.

To analyze all the data together you will want to import the new data from each of the subsidiaries and combine it with the US Sales you loaded earlier.

> 17. Click on the New Source drop down in the Home menu tab of the Query Editor. >18. Select More… as shown in the figure.

Get Data dialog opens

> 19. In the Get Data dialog select Folder as shown in the diagram.
> 20. Click Connect.

Folder dialog opens.

> 21. Click Browse… button.
> 22. In the Browse for Folder dialog navigate to the location where you unzipped the class files.
> 23. Open the DIAD folder.
> 24. Open the Data folder.
> 25. Select the InternationalSales folder.
> 26. Click OK (to close the Browse for Folder dialog box).
> 27. Click OK (to close the Folder dialog box).

**Note:** This approach, uses folders instead of individual files. This will load all files in the folder. This is useful when you have a group that puts files on an ftp site each month and you are not always sure of the names of the files or the number of files. **Note:** All the files must be of the same file type with columns in the same order.

Dialog displays the list of files in the folder.

> 28. Since we want to combine data, click Combine & Edit.

**Note:** Date accessed, Date modified and Date created might be different compared to the dates displayed in the screenshot.

Combine Files dialog opens. By default, Power BI again detects the data type based on the first 200 rows. Notice there is an option to select various file Delimiters. The file we are working with is Comma delimited, so let’s leave Delimiter option as Comma. There is also an option to select each individual file in the folder (using Example File dropdown) to validate the format of the files.

> 29. Select OK.

You will be in the Query Editor window with a new query called InternationalSales.

> 30. If you do not see the Queries pane on left, click on the > icon to expand.
> 31. If you do not see the Query Settings pane on the right as shown in the figure, click on View in the ribbon and click Query Settings to see the pane.
> 32. Click on the Query InternationalSales.

Notice that column Zip is of type Whole Number. Let’s change it to Text as before.

> 33. Highlight the Zip column and change the Data Type to Text.
> 34. Change Column Type dialog opens. Select Replace Current button.

In Queries panel, notice Transform Binary from International Sales folder is created. This contains the function used to load each of the files in the folder.

If you compare this table and bi_salesFact table you imported earlier, you will see the InternationalSales table contains two new columns, Source.Name and Country.

> 35. We do not need Source.Name column. Select Source.Name column. From the ribbon, select Home -> Remove Columns > Remove Columns.

> 36. Click on the drop down next to Country column to see the unique values.
> 37. You will only see Australia as shown in the figure. Click on Load more to validate you have data from various countries included.

You will see the countries, Australia, Canada, France, Japan and Mexico.

> 38. Click OK.

**Note:** You can perform various types of Filters, sorting ascending/descending operations using the drop down to verify your data import and shaping operations.
