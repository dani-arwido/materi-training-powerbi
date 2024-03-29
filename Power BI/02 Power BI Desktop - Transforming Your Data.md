# Power BI Desktop - Transforming your Data

> In this section, we will explore methods to transform data in the data model. Transforming the data by renaming tables, updating data types, and appending tables together ensures that the data is ready to be used for reporting. In some instances, this means cleaning the data up so that similar sets of data are combined. In other instances, groups of data are renamed so that they are more recognizable by end users and simplifies report writing.

## Power BI Desktop - Renaming tables

> The Query Editor window should appear as shown in the diagram. • If formula bar is disabled, you can turn on the formula bar from the View ribbon. This enables you to see the “M” code generated by each click on the ribbons. • Select the options available on the ribbon – Home, Transform, Add Column and View to notice the various features available.

1. Under Queries panel, minimize Transform Binary from InternationalSales folder.
2. Select each query name in the Other Queries section.
3. Rename them in the Query Settings -> Properties section as shown below:

| Initial Name       | Final Name          |
| ------------------ | ------------------- |
| bi_salesFact       | Sales               |
| bi_date            | Date                |
| bi_geo             | Geography           |
| bi_manufacturer    | Manufacturer        |
| bi_product         | Product             |
| InternationalSales | International Sales |

4. From the left panel, select Date Query.
5. Using Ctrl left click key select Year, Quarter, MonthNo, MonthName and MonthID fields.
6. From the ribbon select Transform -> Fill -> Down.

> Notice now all the null values are filled with the appropriate Year, Quarter, MonthNo, MonthName, MonthID values.

## Power BI Desktop – Using Transpose feature

7. From the left panel, select Manufacturer Query. Notice ManufacturerID and Manufacturer data is laid across in rows. And the header is not useful. We need to transpose the table to meet our needs.
8. From the ribbon select Transform -> Transpose.

> Notice this transposes the data into columns. Now we need the first row to be the header.

9. From the ribbon select Home -> Use First Row As Headers.

> Notice now Manufacturer table is laid out the way we need it with a header and values along columns. Also, notice in the APPLIED STEPS section on the right panel, all the steps that we add is being recorded. Also, notice the data type of ManufacturerID and Manufacturer field is updated automatically.

## Power BI Desktop – Using Split feature

10. From the left panel, select Product Query. Notice Product field is a concatenation of Product Name and Product ID. For our scenario, we need only the Product Name.
11. Select Product column.
12. From the ribbon select Home -> Split Column -> By Delimiter.
13. Dialog opens. From the dialog, select – Custom—from the dropdown.
14. Enter “-“ in the text area since we want to split the column based on the hypen.
15. Select OK.

> Notice Product column is split into two columns, Product.1 and Product.2. We do not need Product.2 column since it is the Product ID, which is already available.

16. Select Product.2 column. 17. From the ribbon select Home -> Remove Columns to remove the column.

> Let’s rename Product.1 column to Product.

18. Right click on Product.1 column header. 19. From the menu select Rename to rename the column to Product.

## Power BI Desktop - Changing data types of columns

> Power BI Desktop automatically infers data types based on the data types from the source data. It is always a good idea to check the data types to make sure they are as you need them. This ensures that the data will appear in the right format when authoring reports.
>
> For time intelligence functions to work properly, it’s especially important to make sure the date columns data types are set to Date (or Date/Time).

20. From the left panel, select Sales Query. 21. Verify and if needed, Replace Current Data Type using Home -> Data Type drop down as shown below:

| Column  | Data Type            |
| ------- | -------------------- |
| Date    | Date                 |
| Revenue | Fixed Decimal Number |

> Select Replace Current in the Change Column Type dialog.
>
> Note: We formatted Zip column as text earlier to ensure that zip codes which start with zero don’t lose the leading zero.

22. From the left panel, select Date Query. 23. Verify and if needed Replace Current Data Type using Home -> Data Type drop down as shown below.

| Column | Data      |
| ------ | --------- |
| Type   | Date Date |

24. From the left panel, select International Sales Query.
25. Verify and if needed set Data Type using Home -> Data Type drop down as shown below.

| Column    | Data Type            |
| --------- | -------------------- |
| ProductID | Whole Number         |
| Date      | Date                 |
| Zip       | Text                 |
| Units     | Whole Number         |
| Revenue   | Fixed Decimal Number |

> Notice on the right panel under APPLIED STEPS you will see the list of transformations and steps that have been applied.
>
> You can navigate through each change made to the data by clicking on the step. Steps can also be deleted by clicking on the X that appears to the left of the step.
>
> The properties of each step can be reviewed by clicking on the gear to the right of the step.
>
> To analyze the Sales of all countries, it is convenient to have a single Sales table. Hence you want to append all the rows from International Sales to Sales.

26. Select Sales in the Queries window in the left panel as shown in the figure.
27. From the ribbon select Home -> Append Queries as shown in the figure.

> Append dialog opens. There is an option to append Two tables or Three or more tables. Leave Two tables selected since we are appending just two tables.

28. Select International Sales from the drop down and click OK.

> You will now see a new column in the Sales table called Country. Since International Sales had the additional column for Country, Power BI Desktop added the column to the Sales table when it loaded the values from International Sales. You see null values in the Country column by default for the Sales table rows because the column did not exist for the table with USA data. We will add the value “USA” as a data shaping operation.

29. From the ribbon select Add Column -> Conditional Column as shown in the figure.
30. In the Add Conditional Column dialog, enter name of the column as “CountryName”.
31. Select Country from the Column Name dropdown.
32. Select equals from the Operator dropdown.
33. Enter null in the Values text.
34. Enter USA in the Output text.
35. Select the dropdown under Otherwise and pick Select a column option.
36. Select Country from the column dropdown.
37. Click OK.

> This reads, if Country equals null then the value is USA else value is that of Country.

38. You will see the CountryName column in the Query editor window.

> The original Country column is only required as a temporary column. It is not required in the final table for analysis and can be removed.

39. Right click on the Country column and select Remove as shown in the figure.

> We can now rename CountryName column to Country.

40. Right click on the CountryName column and rename to Country.
41. Using Home -> Data Type, change the data type of the Country column to type Text.

> When the data is refreshed, it will process through all the “Applied Steps” that you have created.
>
> The newly named Country column will have names for all countries, including the USA. You can validate this by clicking on the drop down next to Country column to see the unique values.

42. At first, you will only see USA data. Click on Load more to validate you have data from all 4 countries included.
43. Click OK to close this filter.

44. From the ribbon select View -> Query Dependencies.

> This opens Query Dependencies dialog. The dialog shows the source of each of the query and dependencies. E.g. We see that Sales query has a csv file source and it has a dependency on International Sales query.

45. Select Close in the dialog.

> Query Dependencies view can be zoomed in and out as needed.

46. Let’s save the file before we proceed. From the ribbon select File -> Save As.
47. You will see a dialog box indicating that there are pending changes in your queries that have not been applied. Select Apply Later.

> Note: If you selected Apply, your queries would have been processed and all of your data would have been loaded to the data model. With Apply Later, your queries are saved but you control when the data is loaded. 48. Name the file as “MyFirstPowerBIModel” and select Save. Save the file in \DIAD\Reports folder.

> We don’t need the International Sales table to load to the data model now that its rows have been appended to the Sales table. Let’s prevent the International Sales table from loading to the data model.

49. From the Queries panel on the left, select International Sales query.
50. Right click and select Enable Load. This will disable loading International Sales.

> Note: The appropriate data from the International Sales table will load into the Sales table each time the model is refreshed. By removing the International Sales table, we are preventing duplicate data from loading into the model and increasing its file size. In some instances, storing very large amounts of data affects the data model performance.
>
> You have successfully completed import and data shaping operations and are ready to load the data into the Power BI Desktop data model which allows you to visualize the data.

51. Click on File -> Close & Apply.

> All the data will be loaded in memory within Power BI Desktop. You will see the progress dialog with the number of rows being loaded in each table as shown in the Figure.
>
> Note: It may take several minutes to load all the tables.

52. Select File -> Save to save the file after the data loading is completed.
