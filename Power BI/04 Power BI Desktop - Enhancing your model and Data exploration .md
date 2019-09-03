# Power BI Desktop - Enhancing your model and Data exploration

`In this section, you will do initial data exploration along with model enhancements to create a calculated column, set up relationships and create a measure using DAX (Data Analysis Expression).`

You have been asked to analyze the sales over time

> 1.  Click on the Report icon on the left panel to get to the Report view.
> 2.  Select the Stacked column chart visual in Visualizations as shown in the figure.
> 3.  From Fields section, expand the Date table.
> 4.  Drag and drop Year into Axis.
> 5.  From Fields section, expand the Sales table.
> 6.  Drag and drop Revenue to Value as shown in the figure.
> 7.  You now see the total revenue of all manufacturers by years.
> 8.  Resize the visual as needed by dragging the edges.

Let us say an executive at your company asks “How were the sales at my company (VanArsdel) by months in addition to years?” You can answer this question very easily by enabling the “drill up/down” functionality in Power BI desktop.

> 9. To enable this functionality in the visual drag MonthName column from the Date Table into the Axis below the Year. You have now created a Year/Month “Hierarchy” in the Axis column.

You should see additional icons enabled on the top left and right hand side of the visual. These icons allow you to “Drill down/up”.

> 10. You can drill down from Year level to see Revenue at a month level across all data points by clicking on the double down arrow at the top left corner of the visual. Clicking on the split arrow on the top left corner of the visual provides the capability to view Inline hierarchy i.e., you will be able to view Year and Month information on the X-axis. Click on both the arrow types to view the difference in experience.

To go back up to Revenue by Year click on the up-arrow button on the extreme top left corner of the visual.

When you drill down you will notice that the months are sorted in alphabetical order. Power BI offers you the ability to change the sort order on a column.

> 11. To change the sort order, go to the Data view. Select Date table from the Fields list on the right. Then highlight the MonthName column within that table. From the ribbon, select Modeling -> Sort by Column -> MonthNo.
> 12. Navigate back to the report view and notice the months are now sorted in the right order.

Year and month is concatenated in the XAxis. Let’s say we want we want the months grouped by years.

> 13. With the column chart highlighted, in the Visualization section, click on the Format (paint roller) icon.
> 14. Expand X-Axis and using the slider turn Off Concatenate Labels option.
> 15. Using Minimum category width change the column width as needed.
> 16. Using Text Size option, change the size as needed.
> 17. Navigate up to the Year level by clicking on the up arrow in the top left corner.
> 18. If you would like to drill down on the month level revenue numbers for a specific year say “2017” then click on the single down arrow on top right-hand corner of your visual. The arrow should turn black showing that “Single data point” drill is now enabled. Now single click on the column for year 2017.
> 19. You should now see the revenue breakdown by month for 2017. You can go back up to Year level revenue numbers by clicking on the up arrow in the top left corner.

Now let’s compare how my company (VanArsdel), is doing as compared to other manufacturers.

> 20. From the Fields section, expand Manufacturers table and drag and drop Manufacturer column to the Legend section as shown in Figure.

You will see the stacked column chart of sales by various companies and the legend on the top as shown in the figure.

You are primarily interested comparing VanArsdel with the top competitors and the rest of the competitors. Power BI Desktop has the option to create groups. Let’s try it out.

> 21. Select the Stacked column chart visual. In the Legend section, select the arrow next to Manufacturer and select New Group.

Group dialog opens.

> 22. In the Ungrouped values section, using Ctrl key, select Aliqui, Currus, Natura and Pirum.
> 23. Select Group button. Notice a new group is added in the Groups and members section.
> 24. Double click the newly created group and rename it to Top Competitors.
> 25. Select VanArsdel from the Ungrouped values section and select Group button to create VanArsdel Group.
> 26. Select the check box Include Other group. This will create an Other group which will include all the other manufacturers.
> 27. Select OK to close Groups dialog.

In the Fields section, notice Manufacturer group is created under Manufacturer table.

Manufacturer (groups) field is added to the Legend section.

Now we have a visual that shows Revenue by Year for VanArsdel, the top competitors and the rest of the competitors.

> 28. From the Visualization section, select Format (brush icon).
> 29. Expand X-Axis and scroll down.
> 30. Using the slider enable Title.
> 31. Change the Title color to Green.
> 32. Change the Title text size as needed.

Notice there is an option to enter a custom Axis title. When you drill from Year to Month level, notice the X-axis title changes to MonthName. Similarly, Y-axis can also be formatted.

Suppose you want to investigate the records that make up VanArsdel’s sales for the year 2017.

> 33. With the Stacked column chart selected, from the ribbon, select Data/Drill - See Records.

Selecting See Records, enables the ability to view the records based on the selection.

> 34. Click on VanArsdel section of the column for the year 2017.

All the records that make up VanArdel’s data for 2017 is displayed.

> 35. Click on Back to Report to get back to the chart view.
> 36. From the ribbon select Data/Drill -> See Records again to disable viewing records.
> 37. From the ribbon select Data/Drill -> See Data.

Notice now the canvas is divided into two panes, top displays the chart and bottom displays the data that makes the chart.

> 38. Clicking on Switch to vertical layout icon on the top right corner will change the layout to display chart on the left and data on the right.
> 39. Click on Back to Report to get back to the chart view.

For the next visualization, assume you want to be able to analyze the sales of units by various countries along with the sales by years/months.

> 40. Click on the white canvas in Power BI Desktop.
> 41. From Visualizations section, select Stacked column chart. You will see the column chart appear.
> 42. From Fields section, expand Geography table. Drag and drop the Country column to Axis.
> 43. From Fields section, expand Sales table. Drag and drop the Units column to the Value.

You will see all the countries having about 11.4 Million units. The reason you see the same value is due to the fact there is no relationship between the Geography table and the Sales table.

You now need to set up the correct relationship between these tables. To create a relationship between the two tables we need a “joining” or “relating” column.

In this case the columns Zip and Country will help us establish the relationship since you can uniquely identify each row in the Geography table with Zip and Country. We need to create a new column in both the Geography table and the Sales table that combines “Zip” and “Country”. Let us start by creating a new column in the Sales table.

> 44. In the Fields section, click on the ellipsis next to Sales table. Select “New Column” as shown in the figure.

You will see a formula editor appear as shown in the figure to help create this new column.

> 45. We can combine or concatenate the Zip and Country columns into a new column called ZipCountry separated by a comma. Let us create this column called ZipCountry using the following calculation in the editor.

    ZipCountry = Sales[Zip] & "," & Sales[Country]

> 46. Once you are done entering the formula click in the check mark on the left side of the formula editor.

You will notice that as you type the expression the Power BI desktop guides you to choose the right columns using a Technology called Intellisense. As you type half way through you can select the right column by double clicking on it using your mouse or by continuing to hit tab until you see the correct name.

The language you used to create this new column is called DAX (Data Analysis Expression) which is very similar to writing expressions in Excel where you are concatenating the two columns (Zip and Country) in each row by using the “&” symbol.

You will see a new column ZipCountry in Sales table. The icon with a (fx) indicates you have a column that contains an expression, also referred to as calculated column.  
You can also create a new column by selecting the table and then clicking on Modeling -> New Column from the ribbon. Let us use this method to create a “ZipCountry” column in the Geography table.

> 47. From Fields section, select Geography table and from the ribbon select Modeling -> New Column as shown in the figure.
> 48. Formula bar appears. Enter the following DAX expression in the formula bar:

    ZipCountry = Geography[Zip] & "," & Geography[Country]

You will see a new column ZipCountry in Geography table. The final step is to setup the relationship between the two tables using the newly created “ZipCountry” columns in each of these tables.

> 49. From the ribbon select Modeling -> Manage Relationships.
> 50. In the Manage Relationships dialog you will see all existing relationship between the tables. You can also create new relationships in this dialog.
> 51. Click on the New button to create a new relationship.
> 52. In the Create Relationship dialog first select Geography from the top drop down as shown in the figure.
> 53. Select the column ZipCountry.
> 54. Select Sales table from the second drop down as shown in the figure. Power BI automatically selects the ZipCountry column for you because you selected a column with a same name in the Geography table.
> 55. Click OK in the Create Relationship dialog.
> 56. You will see the new relationship created as shown in the figure.
> 57. Click Close in the Manage Relationships dialog.
> 58. When you look at the report canvas you will immediately see that the relationship has taken effect. You can now see the total units sold in each country. You can hover over USA to see the actual value.

Let’s compare non-USA sales by using exclude functionality.

> 59. Right click on the USA column of the column chart.
> 60. Select Exclude. Notice this filters out USA from the visual. Also, notice a filter is added to in the Visual level filters section in the right panel.
> 61. To remove the exclude filter, click on the “x” in the Filter section.

Similarly, there is an option to Include as well.

> 62. Click on bar for USA in the bottom graph to analyze what portion of the units sold in USA contributes towards to overall Sales.

You will immediately notice that in the bottom graph the rest of the bars fade away and USA remains highlighted in the bold. Similarly, in the graph on the top a portion of each bar is highlighted in bold and the rest is faded. This visually shows the proportion of sales from USA (for each manufacturer and in each Year/Month). This is called Cross filtering in Power BI. You can remove the cross-filtering effect by clicking anywhere on the bottom graph.

**Note:** You have now created a visual filter on the top graph while the bottom graph on units sold includes all manufacturers.

Since the units sold are by country, you can easily map your sales.

> 63. Select the bottom column chart and click on the map visual icon (not the filled map visual) in Visualizations. You will see the bottom visual change to a map visualization and the size of the bubble in each country shows the total number of units sold.
> 64. Resize the map as needed.

**Note:** Microsoft Bing is used to create the map; hence you must be connected to the internet for the map visual to work.

**Note:** You didn’t have to do any complex operations to change the visual type, Power BI desktop automatically understood the Country column and add it to the location and the units to the values.

Let’s assume we want to create a table visual to display the Revenue by year and add a column that displays the % of revenue for each year to help figure out the years where sales were high.

> 65. Click on the white space in the canvas. From the Visualizations section, select Table.
> 66. From the Fields section, expand Date table and select Year.
> 67. From the Fields section, expand Sales and select Revenue.

Notice that Year is summed by default since the data type is of type Whole Number. We would never sum Year, so let’s change it.

> 68. In the Fields section, click on Year.
> 69. From the ribbon, select Modeling -> Default Summarization -> Do Not Summarize.
> 70. From the Values section of the Table visual, delete Sum of Year field by clicking on the “x”.
> 71. From the Date table, drag Year field and drop it above Revenue in Values section of the table visual.

Notice Year is not summed anymore.

> 72. From the Values section, select the arrow next to Revenue field.
> 73. Select Conditional formatting -> Data bars.
> 74. Data bars dialog opens. There are options to format the data bar. Select OK.

Notice data bar helps to easily identify the years with high revenue and those years with low revenue.

> 75. From the Sales table, drag Revenue field and drop it below Revenue in Values section of the table visual. Notice the newly added Revenue field is not summed.
> 76. Click the arrow next to the newly dropped Revenue field.
> 77. Select Sum.

Notice now both the Revenue fields are summed.

> 78. Click the arrow next to the second Revenue field.
> 79. Select Show value as -> Percent of grand total.

Notice now we have % GT Revenue field. With Quick Calc feature we can add a calculation to the report and meet the requirement of displaying % of revenue by year. Let’s rename the field.

> 80. In the Values section of the table report, click on the arrow next to % GT Revenue.
> 81. From the menu select Rename.
> 82. Rename the field to % of Total Revenue.

Alternately, we can use Color scales on the table so we can easily identify the years where sales were good versus bad.

> 83. In the Values section of the table report, click on the arrow next to % of Total Revenue.
> 84. From the menu select Conditional Formatting -> Background color scales.

Color scales dialog opens. By default, there are options to format minimum and maximum.

> 85. We want to format center value as well, so select the Diverging checkbox.
> 86. Select Lowest Value from Minimum drop down.
> 87. Select Middle Value from Center drop down.
> 88. Select Highest Value from Maximum drop down.
> 89. Pick Red color for the minimum value, Yellow for center and Green for maximum.
> 90. Click OK.

Notice now we can quickly figure out that sales peaked in 2008. Feel free to explore other table formatting options available in the format section (paint roller) section of the visual. E.g. Word wrap column header, etc. Similarly, there is an option to conditionally format font color scales as well. Feel free to try this option.

Let’s add a date slicer, so we can filter by date.

> 91. From the Visualization section, select Slicer visual.
> 92. From the Fields section, expand Date table and select Date. This creates a Date slicer.
> 93. Using the slider, change the date filter. Notice the visuals on the page change based on the filter selection.

Clicking on the date field opens a date picker which provides the ability to pick a date. Hover on the visual and select the arrow on the right corner. Notice there are options to display the date slicer in the following formats: Between, Before, After, List, Dropdown, Relative.

It will be helpful to know how the Products are clustered. E.g. Products that have lower quantity sales but bring in higher revenue versus products that have higher quantity sales but lower revenue, etc. This will also help with finding outliers.

> 94. From Visualizations section, select Scatter chart.
> 95. From Fields section, expand Product and drag and drop Product field to Details section.
> 96. From Fields section, expand Sales and drag and drop Units to X-Axis section.
> 97. From Fields section, expand Sales and drag and drop Revenue to Y-Axis section.
> 98. Click on the dropdown next to Units in X-Axis. Select Average. This will provide Average Units Sold.
> 99. Similarly, click on the dropdown next to Revenue in Y-Axis. Select Average. This will provide Average Revenue.

Next let’s create clusters.

> 100.  Click on the ellipsis on the top right corner of the Scatter chart.
> 101.  Select Automatically find clusters.
> 102.  Clusters dialog opens. We have option to provide cluster Name and Description and the Number of clusters. Enter 4 for Number of Clusters.
> 103.  Click OK.

Using clustering algorithm 4 clusters are created by default. Notice it clusters products with low average units sold and low average revenue, products with low average units sold and high average revenue and so on.

> 104.  On the bar chart click on Top Competitors and notice the change in clustering. Notice that most the competitor products are in two major clusters – low to medium average units sold and low to medium average revenue.

You can change the number of clusters to see how the distribution changes.
