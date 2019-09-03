# Power BI Desktop – Data Modeling and Exploration

In this section, we will learn the key parts of the Power BI desktop, to model and explore the data and build visuals.

## Power BI Desktop - Layout

You will land on the main Power BI Desktop window. Let’s get familiar with the distinct sections available in the Power BI Window.

1. On the top, you see the Home tab where the most common operations you perform are available.
2. View tab has options to format the page layout.
3. Modeling tab in the ribbon enables additional data modeling capabilities like adding custom columns and calculated measures.
4. Help tab provides self-help options like guided learning, training videos and links to online communities, partner showcase and consulting services.
5. On the left side, you have three icons, Report, Data and Model. If you hover over the icons, you can see the tool tips. Switching between these allows you to see the data and the relationships between the tables.
6. The center white space is the canvas where you will be creating visuals.
7. Visualizations panel on the right allows you to select visualizations, add values to the visuals and add columns to the axes or filters.
8. The Fields window on the right panel, is where you will see the list of tables which were generated from the queries. Click the icon next to a table name to expand to the field list for that table.
9. Click on the Data icon. Expand Sales table in the Fields as shown in the figure

Scroll up and down to notice how fast you can navigate through ~ 3 Million rows.

10. Click on the Model icon on the left panel of Power BI Desktop. You will see the tables you have imported along with some Relationships. The Power BI Desktop automatically infers relationships between the tables.

- A relationship is created between Sales and Product tables using ProductID column.
- A relationship is created between Product and Manufacturer tables using ManufacturerID column.

  Power BI supports 1 to many, 1 to 1 and many to many types of relationships between the tables.

  In this lab we will be using 1 to many type of relationship. This is the most common type of relationship between tables. This means one of the tables involved in the relationship should have a unique set of values.

  Notice there is no relationship between the Geography and Sales tables. If you want to explore sales data across state or city or country, you will need to setup the relationship between the Geography and Sales tables. You will create the relationship shortly.

  **Note**: Tables may not appear as shown in the figure. You can zoom in and out of the Relationships page by dragging the zoom slider in the bottom right corner of the window. Also, if want to ensure you are seeing all the tables, use the fit to
  page icon: . Drag and move the tables to appear as shown in the figure.

## Power BI Desktop – Data Exploration

We loaded data from different countries. So, let’s start with analyzing sales by country.

11. Click on the Report icon on the left panel to navigate to the Report view.
12. Select the Clustered column chart visual in Visualizations as shown in the screenshot.

13. From the FIELDS section, expand Geography table and click the checkbox next to the Country field.
14. From the FIELDS section, expand Sales table and click the checkbox next to the Revenue field.
15. Resize the visual as needed by dragging the edges. Notice revenue of each country is the same. This is because there is no relationship between Sales and Geography tables. Let’s create one.

**Note**: You now need to set up the correct relationship between these tables. To create a relationship between the two tables we need a “joining” or “relating” column.

16. Click on the Model icon on the left panel to navigate to the Relationship view.
17. Sales data is by Zip code. Hence, we need to connect Zip column from Sales table with Zip column in Geography table. You can do this by dragging the Zip field in Sales table and connecting the line with Zip field in Geography table.

You will notice Create relationship dialog opens with a warning message at the bottom stating the relationship has a many-many cardinality. The reason for the warning is that we don’t have unique Zip values in Geography.

This is because multiple countries could have the same Zip code. Let’s concatenate Zip and Country columns to create a unique value field.

18. Select Cancel in Create relationship dialog. We need to create a new column in both the Geography table and the Sales table that combines “Zip” and “Country”. Let us start by creating a new column in the Sales table.
19. Click on the Report icon on the left panel to navigate to the Report view.
20. In the Fields section, click on the ellipsis next to Sales table. Select “New Column” as shown in the figure. You will see a formula bar appear as shown in the screenshot to help create this new column.
21. We can combine or concatenate the Zip and Country columns into a new column called ZipCountry separated by a comma. Let us create this column called ZipCountry using the following calculation in the editor.
    ZipCountry = Sales[Zip] & "," & Sales[Country]

22. Once you are done entering the formula press Enter or click in the check mark on the left side of the formula bar.

You will notice that as you type the expression the Power BI desktop guides you to choose the right columns using a Technology called Intellisense. As you type half way through you can select the right column by double clicking on it using your mouse or by continuing to hit tab until you see the correct name.

The language you used to create this new column is called Data Analysis Expression (DAX) which is very similar to writing expressions in Excel where you are concatenating the two columns (Zip and Country) in each row by using the “&” symbol.

You will see a new column ZipCountry in Sales table. The icon with a (fx) indicates you have a column that contains an expression, also referred to as calculated column.

You can also create a new column by selecting the table and then clicking on Modeling -> New Column from the ribbon. Let us use this method to create a “ZipCountry” column in the Geography table.

23. From Fields section, select Geography table and from the ribbon select Modeling -> New Column as shown in the figure.
24. Formula bar appears. Enter the following DAX expression in the formula bar:
    ZipCountry = Geography[Zip] & "," & Geography[Country]

You will see a new column ZipCountry in Geography table. The final step is to setup the relationship between the two tables using the newly created “ZipCountry” columns in each of these tables.

25. Click on the Model icon on the left panel to navigate to the Relationship view.
26. Drag ZipCountry field from Sales table and connect it to ZipCountry field in Geography table. Now we have successfully created a relationship. The number 1 next to Geography indicates it is on the one side of the relationship and \* next to Sales indicates it is on the many side of the relationship.

27. Click on the Report icon on the left panel to navigate to the Report view. Notice the clustered column chart we created earlier. It shows different sales for each country. USA has the most sales followed by Australia and Japan. By default, it is sorted by Revenue.
28. Click on the ellipsis on the top right corner of the visual. Notice there is option to Sort by Country as well.

Now let’s analyze Sales by Country by Manufacturer and see if we get more insights.

29. With the Clustered column chart selected, from the Fields section expand Manufacturer table.
30. Drag and drop Manufacturer field to Legend section.

There are many manufacturers and clustered column chart does not represent the information well. Let’s change the visual.

31. With the Clustered column chart selected, from the VISUALIZATIONS section select Stacked column chart visual.
32. Resize the visual as needed.

Now we can figure out the top manufacturers by country. It will be nice to narrow down to the top 5 competitors to better analyze the data.

33. With Clustered column chart selected
34. In the Filters pane, expand Manufacturer.
35. From the Filter Type drop down select Top N.
36. Enter 5 in the text box next to Top.
37. From Sales table, drag and drop Revenue field to By value section.
38. Select Apply filter.

Notice now the visual is filtered to display the Top 5 manufacturers by Revenue. We see that VanArsdel has higher percentage of sales in Australia compared to other countries.

Let’s see if there is another way to build this visual.

39. Click on the white space in the canvas and from the ribbon select Home -> Ask A Question.
40. In the dialog start typing Top 5 Manufacturer. Notice a table with the top 5 manufacturers is displayed.
41. Continue typing Top 5 Manufacturer by country by revenue. Notice a bar chart is created.
42. Continue typing Top 5 Manufacturer by country by revenue as stacked column chart. Notice we can create the same visual we did earlier by typing the question.
43. With the visual selected, under VISUALIZATIONS section, scroll down to Visual level filters. Expand Manufacturer. Notice the Top N filter is applied.
44. We have two of the same visuals, so let’s delete this one. Hover over the visual and select the ellipsis on the top right corner. Select Remove.

We are interested in the top 5 competitors by revenue. Let’s group them so we don’t have to add a filter in every visual. Before we do that let’s remove the Top 5 visual level filter.

45. With Clustered column chart selected
46. Hover over and select the Clear filter icon (erase) next to Manufacturer field in the Filters Pane.

47. From the FIELDS section, click on the Manufacturer field name (**note**: do not check the checkbox) from Manufacturer table.
48. From the ribbon select Modeling -> New Group. Groups dialog opens.
49. In the Ungrouped values section, using Ctrl key, select Aliqui, Currus, Natura and Pirum.
50. Select Group button. Notice a new group is added in the Groups and members section.
51. Double click the newly created group and rename it to Top Competitors.
52. Select VanArsdel from the Ungrouped values section and select Group button to create VanArsdel Group.
53. Select the check box Include Other group. This will create another Other group which will include all the other manufacturers.
54. Select OK to close Groups dialog.
55. With the Stacked column chart selected, click on the X next to Manufacturer in the Legend section. This will remove Manufacturer.
56. From the FIELDS section, drag the newly created Manufacturer (groups) to the Legend section.

Now we can clearly see that VanArsdel has nearly 50% share in Australia.

57. Hover over VanArsdel section of the Australia column. You will see a tooltip with the Revenue.
58. Hover over Top Competitors section of Australia column to get the Revenue value.

Let’s find a better way to view the data without creating a new visual.

59. Hover over one of the columns and right click.
60. Select Show Data. You will be in Focus mode with the chart displayed on top and the data displayed below. It is easy to see that VanArsdel has a big percent of the Australian market.
61. You can use the icon on the top right corner to switch to vertical layout. In this layout you will view the chart on the left and data on the right panel.
62. Select Back to Report to go back to Report canvas.

63. There is also an option to see the records. Hover over one of the columns and right click.
64. This time select See Records. You will see the detailed records.
65. Select Back to Report to go back to Report canvas.

**Note**: See Records and Show Data options are also available in the ribbon under Data/Drill menu option.  
Let’s remove Manufacturer from the Legend and create a visual which represents Revenue by Manufacturer and check if it will help with any new insights.

66. With the Stacked column chart selected, click on the X next to Manufacturer (groups) in the Legend section. This will remove Manufacturer.

Let’s create Revenue by Manufacturer visual.

67. Click on the white space in the canvas. From the FIELDS section, click the checkbox next to Revenue field in Sales table.
68. From the FIELDS section, click the checkbox next to Manufacturer field in Manufacturer table.
69. From the VISUALIZATIONS section, select Treemap visual.
70. Resize the visual as needed. We have Revenue by Manufacturer. Let’s figure out the interaction between the Stacked column chart and the Treemap visuals.
71. Click on USA column in the Stacked column chart and notice the Highlighted section of Treemap updates.
72. Click on Australia column in the Stacked Column chart and notice the Highlighted section of Treemap updates.
73. Similarly, select VanArsdel in the Treemap and notice Stacked column chart is filtered. This confirms that VanArsdel has a big percent of the Australian market.
74. To remove the filter select VanArsdel again. The interaction between visuals is called cross filtering.

Previously we added Top 5 Visual level filter. Let’s add a filter to the Page level, so we are working with the Top Competitors and VanArsdel and filter out the other manufacturers. Page level filters apply to all the visuals on the page whereas Visual level filter applies to a visual.

75. From FIELDS section, drag Manufacturer (groups) from Manufacturer table to the Filters on this page box in the Filters Pane
76. Select Top Competitors and VanArsdel.

Let’s add a visual that will provide sales information over time.

77. Click on the white space in the canvas.
78. Click the checkbox next to the Date field in Sales table. Notice a Date Hierarchy is created.
79. Click the checkbox next to the Revenue in Sales table field. Notice a Clustered column chart is created. Also notice in the Axis section, a date hierarchy is created. There are arrows on the top bar of the chart. This is used to navigate through the hierarchy.

80. Click on USA column in the Revenue by Country visual. Notice sales is on the upward trend over time.
81. Click on Australia column in the Revenue by Country visual. Again, the trend is upwards.
82. We see a similar scenario with Japan as well. With the current interaction the visuals are slicing the data. It will be nice to filter data across visuals. This might give us a better perspective. Let’s try that.

83. Click on Australia column in the Revenue by Country visual.
84. With the Revenue by Country visual selected, from the ribbon select Format -> Edit Interactions. Notice on the top right of the other two visuals we see new icons with the highlight icon selected.
85. Select filter icon for both visuals. Notice now in both Revenue by Year and Revenue by Manufacturer data is filtered for Australia.

86. Now select Revenue by Year visual.
87. Select filter icon on the other two visuals.
88. Similarly, select Revenue by Manufacturer visual and select filter icon on the other two visuals. Once you are done, all the visuals should be in filter mode.
89. With the Revenue by Manufacturer visual selected, from the ribbon select Format -> Edit Interactions to remove the icons.
90. Click on VanArsdel in the Revenue by Manufacturer visual. Notice sales is on an upward trend over time.
91. Click on Natura column in the Revenue by Manufacturer visual. Notice sales in 2018 for Natura was on a downward trend. Similarly, you can analyze other manufacturers performance.

We had already noticed that VanArsdel has a big share of the market in Australia. Let’s check how VanArsdel has done over time in Australia.

92. Click on VanArsdel in the Revenue by Manufacturer visual.
93. Ctrl+Click Australia column in Revenue by Country visual. Now we have filtered the charts by both VanArsdel and Australia. We see a spike in 2018 sales for VanArsdel in Australia.
94. Let’s see what’s happening in USA. Click USA column in Revenue by Country visual.
95. Ctrl+Click on VanArsdel in the Revenue by Manufacturer visual. Now we have filtered the charts by both VanArsdel and USA. We see a steady growth. Similarly, we can analyze data for different countries, manufactures and time frame.

We are intrigued by the spike in 2018 for VanArsdel in Australia. Let’s investigate further.

96. Click on VanArsdel in the Revenue by Manufacturer visual.
97. Ctrl+Click Australia column in Revenue by Country visual
98. Select the down arrow on the top right corner of the Revenue by Year visual. This enables drill down capability.
99. Select 2018 column in Revenue by Year visual. Notice you have drilled down to quarter level of 2018. There is a big spike in the 4th quarter. Interesting let’s dig further…

100.  Click on the double arrow icon on the top right of Revenue by Year visual. This drills down to the next level of the hierarchy which is month. Looks like sales picked up in September and October and is holding steady since then. Ok this is interesting. Now is this a yearly trend. Let’s check?
101.  Click on the up arrow icon on the top right of Revenue by Year visual to drill up to Quarter level.
102.  Click on the drill up icon again to go up to Year level.
103.  Click on the split arrow icon on the top right of Revenue by Year visual. This expands down to the next level of the hierarchy which is quarter for all the years. Notice 4th quarter sales have always been high but in 2018 there is a bigger spike in the 4th quarter.
104.  Let’s expand down to the month level. Click on the split arrow icon on the top right of Revenue by Year visual. This expands down to the next level of the hierarchy which is month for all the years. There is a lot of information on the visual and we must scroll left and right to compare.
105.  Click on focus mode icon on the top right of Revenue by Year visual.

Now Revenue by Year takes over the complete canvas. Notice that sales have typically been high that last 4 months of the year. It confirms the spike in 2018.

**Note**: Drill up/down functionality is available in the ribbon as well.

106. From the ribbon, select Data/Drill -> Drill up to move to Quarter level. 107. From the ribbon, select Data/Drill -> Drill up to move to Year level. 108. Click on Back to Report on the top left corner of the visual to go back to report canvas. 109. Click on VanArsdel in the Revenue by Manufacturer visual to remove filters.
