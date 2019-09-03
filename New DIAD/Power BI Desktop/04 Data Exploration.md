# Power BI Desktop – Data Exploration Continued

In this section, you will continue to explore the data to try to identify the reasons for the spike in sales in Australia for the year 2018.
At the end of the section, you will create a view similar to the view on the right.

Let’s continue to investigate our findings of VanArsdel’s sales spike in 2018 in Australia. We will start by adding a new page.

1. Right click on Page 1 (bottom left).
2. Select Rename Page. Rename the page to Market Analysis.
3. Right click on Market Analysis page. This time pick Duplicate Page. We are duplicating the page since we can reuse some of the visuals. A new page is created, and you will be navigated to this new page. Let’s add a slicer so we can filter manufacturers.
4. Click on the white space in the canvas. From the FIELDS section, click the checkbox next to Manufacturer field in Manufacturer table.
5. From the VISUALIZATIONS section select Slicer visual.
6. You will see a list of Manufacturers. Select VanArsdel and notice all the visuals are filtered based on your selection.
7. Hover over the top right corner of the visual and click on the down arrow. Notice you have the option to change the slicer from a list to a drop down.
8. Select Dropdown.
9. Select VanArsdel from the dropdown.
10. Navigate to the Market Analysis page. In the FILTERS pane click on the X to remove the Manufacturer filter from Filters on this page. Since we have two pages and we want Manufacturer filter to apply to both pages it makes sense to move it to Filters on all pages in the Filters pane.
11. Navigate back to Duplicate of Market Analysis.
12. Click on the X to remove the Manufacturer filter from Filters on this page.
13. In the FIELDS section, from Manufacturer table drag Manufacturer (groups) field to the Filters on all pages box in the Filters pane.

14. Select Top Competitors and VanArsdel.

We use the Manufacturer slicer to analyze one manufacturer at a time. Notice when we do this, Revenue by Manufacturer Treemap visual is not the best representation of the data. Let’s change it.

15. Select Revenue by Manufacturer Treemap visual.
16. From the VISUALIZATIONS section, select Card visual.

The card visual will give us the Revenue as we filter and cross filter the visuals.

Notice all key dimensions/characteristics is in its own table with the related attributes except date. E.g. Product attributes are in Product table and we created a relationship between Product and Sales. It is good practice to have dimensions in different tables. In the future if we need to add date attributes like Week number, Day of Week, Holiday, etc., we need to have a Date table. Let’s create Date table.

17. Navigate to Data view by clicking on the Data icon on the left panel.
18. From the ribbon select Modeling -> New Table.

Notice a new table is created in the FIELDS section on the right and formula bar opens.

19. Enter Date =CALENDAR (DATE(2012,1,1), DATE(2018,12,31)) in the formula bar and click on the check mark. A Date table with a Date column is created. We are using 2 DAX functions: CALENDAR function which takes the start and end data. DATE function which takes year, month and date fields. We are creating Date from 2012 to 2018 since our dataset has data for those years. We can add more fields to this table like Year, Month, Week etc. by using DAX functions. Notice Date field is of type Date/Time. Let’s change it to data type Date.

20. Select the Date field in the Date table.
21. From the ribbon, select Modeling -> Data type -> Date.

Next, we need to create a relationship between the newly created Date table and Sales table. Previously we used the visual drag and drop feature to create a relationship. This time around let’s use a different option.

22. From the ribbon, select Modeling -> Manage Relationships.
23. Manage Relationships dialog opens. Select New button.
24. Create relationship dialog opens. Select Date from the top dropdown.
25. Select Sales from the second dropdown.
26. Highlight Date fields from both the tables.
27. Select OK to close Create relationship dialog.
28. Select Close to close Manage relationships dialog.
29. Navigate to Report view by clicking on the Report icon on the left panel. Notice Revenue by Date chart looks different. Let’s fix it.
30. Select Revenue by Date visual.
31. From the Axis click on “X” to remove the Date field.
32. From the FIELDS section expand Date table.
33. Drag Date field to Axis section. Notice with the new Date field behavior is like earlier.

There are two Date fields, it might get confusing to figure out which to use. Let’s hide the Date field in Sales table.

34. From the FIELDS section, Click on the ellipsis next to Date field in Sales table.
35. Select Hide. This hides Date field in the reports view. We have the option to view hidden fields and unhide fields as needed.
36. Similarly hide Country, ProductID, Zip and ZipCountry in Sales as well
37. Similarly hide ZipCountry from the Geography table.
38. Hide ManufacturerID from Manufacturer table.
39. Hide ProductID and ManufacturerID from Product table.
40. Note: It is best practice to hide fields that are not used in reports.Let’s get back to our data story, Australia, VanArsdel and 2018 – remember 😊. Let’s check if the spike occurred in a specific region in Australia.
41. Select Revenue by Country visual.
42. From the FIELDS section, drag State field from Geography table, below Country in the Axis section.
43. Drag District field below State in the Axis section. We just created a hierarchy.
44. Make sure VanArsdel is selected in the Manufacturer slicer.
45. Enable Drill mode by selecting down arrow on the top right corner of Revenue by Country visual.
46. Select Australia to drill down to State level.
47. From Revenue by Year visual select 2018 and notice Revenue by Country and State visual.
48. From Revenue by Year visual select 2018 and notice Revenue by Country and State visual.
49. Similarly, select
50. We don’t see a spike in a specific state.
51. Select 2016 again to remove year filter.
52. Drill up to country level.Let’s analyze by Product to figure out what’s happening there. Before we start with that let’s create a Product Hierarchy. This way we don’t have to drag multiple fields to the visual.
53. From the FIELDS section, click on the ellipsis next to Category in Product table.
54. Select New Hierarchy.Notice a new field called Category Hierarchy is created in the Product table.
55. Double click on Category Hierarchy and rename it to Product Hierarchy.
56. Click on the ellipsis next to Segment.
57. Select Add to Hierarchy -> Product Hierarchy.
58. Click on the ellipsis next to Product.
59. Select Add to Hierarchy -> Product Hierarchy. We have created a Product Hierarchy which is Category -> Segment -> Product.
60. Click on the white space in the canvas. From the VISUALIZATIONS section select Clustered bar chart.
61. From the FIELDS section, expand Product table.
62. Click the checkbox next to Product Hierarchy. Notice complete hierarchy is selected.
63. From the FIELDS section, expand Sales table.
64. Click the checkbox next to Revenue field.

Note: Make sure you have VanArsdel selected in the slicer. We see that VanArsdel has a presence in the Urban category and a small presence in the Rural category.

64. Drill down Urban category (yes you are an expert drilling up and down hierarchy 😊). If not, select the down arrow on the top right corner of the visual.
65. Select the Urban row to drill down to Urban segments.
66. In Revenue by Country visual select USA.
67. Ctrl+Click 2018 from Revenue by Year visual. Notice Convenience and Moderation are the key segments in USA.

68. In Revenue by Country visual select Australia.
69. Ctrl+Click 2018 from Revenue by Year visual. Notice sales in Extreme category is higher than Convenience and Moderation segments. We need to investigate further…

70. Select the down arrow on the top right corner of Revenue by Country visual to enable drill model.
71. Select Australia to drill down to State level.
72. Select 2018 in Revenue by Year visual.
73. Remove drill mode from Revenue by Category visual.
74. Ctrl+Click Extreme Segment in Revenue by Category and Segment visual.
75. Select 2017 in Revenue by Year visual.
76. Ctrl+Click Extreme Segment in Revenue by Category and Segment visual.

There is no significant spike by State.

77. Select Extreme again to remove cross filtering between visuals.
78. Drill up to Category level in Revenue by Category visual.

Let’s add a Matrix visual so we can view data in rows and columns. We can apply conditional formatting to the matrix visual to highlight outliers.

79. Click on the white space in the canvas. From the VISUALIZATIONS section, select Matrix visual.
80. From FIELDS section, drag and drop Product Hierarchy field from Product table to Rows section.
81. From Sales table in FIELDS drag and drop Revenue to Values section.

Note: Notice Revenue field needs to be formatted so it shows the same number of decimal points. We will do this shortly.

82. Enable drill mode in the matrix by selecting the down arrow on the top right corner of the visual.
83. Select Urban row to drill down.

Well the text is too small, let’s format the matrix and make it more readable.

84. In the VISUALIZATIONS panel, select the paint roller icon to format the visual.
85. Scroll down and expand Values section.
86. Scroll down and increase the Text size to
87. Notice there are a lot of formatting options. Feel free to explore them.
88. Scroll up and expand Column headers section.
89. Scroll to Text size and increase it to 10.
90. Scroll up and expand Row headers section.
91. Scroll to Text size and increase it to 10.

Let’s add percent of total field. This will give us a better perspective.

91. Navigate away from Format section to the Fields well.
92. From FIELDS section drag Revenue field from Sales table below the existing Revenue field in Values section.
93. Select the arrow next to the newly added Revenue field.
94. From the dialog select Show value as -> Percent of grand total.

We see that in Australia, Extreme segment has highest market share. Let’s check across time if this is true.

95. In the Revenue by Year visual select 2016 column. Notice Extreme segment has around 30% of the grand total.
96. In the Revenue by Year visual select 2017 column. Notice Extreme segment has around 30% of the grand total.
97. In the Revenue by Year visual select 2018 column. Notice Extreme segment has around 40% of the grand total.
98. In the Revenue by Year visual select 2018 column to remove the filter.

Let’s drill down Extreme Segment and figure out if a Product stands out.

99. In the matrix visual select Extreme row to drill down to Product level.
100. Resize the visual as needed.
101. Hover over matrix visual and select the ellipsis on the top right corner.
102. Select Sort By %GT Revenue and Sort Descending.

We see the top Products. Let’s analyze top Products over time.

103. In the Revenue by Year visual select 2016 column. Notice Maximus UE-04 and 11 are the top products.
104. In the Revenue by Year visual select 2017 column. Notice Maximus UE-16 and 17 are the top products.
105. In the Revenue by Year visual select 2018 column. Notice Maximus UE-04 and 21 are the top products. And Product 04 has nearly 7% of the grand total. Product 04 has a big spike.
106. In the Revenue by Year visual select 2018 column to remove the filter.

Earlier we created a calculated column (ZipCountry). Let’s create % Growth measure so we can compare sales over time. We are going to do this in two steps.

But first, what’s the difference between measure and calculated column. Calculated column is evaluated row by row. We extend a table by adding calculated columns. Measure is used when we want to aggregate values from many rows in a table.

107. In the FIELDS section, select Sales table.
108. From the ribbon, select Modeling -> New Measure. Formula bar opens.
109. Enter PY Sales = CALCULATE(SUM(Sales[Revenue]), SAMEPERIODLASTYEAR('Date'[Date])
110. Select the check mark next to the formula bar. You will see PY Sales measure in Sales table.

Let’s create another measure.

111. In the FIELDS section, hover over Sales table.
112. Click on the ellipsis on the right corner.
113. Select New Measure from the dialog. Formula bar opens.
114. Enter % Growth = DIVIDE(SUM(Sales[Revenue])-[PY Sales],[PY Sales])
115. Select the check mark next to the formula bar. You will see % Growth measure in Sales table.

116. Select the matrix visual.
117. In the FIELDS section, click the checkbox next to the newly created PY Sales and % Growth measures in Sales table. Notice fields need to be formatted.
118. From the FIELDS section, select % Growth field.
119. From the ribbon select Modeling -> Format -> Percentage
120. Similarly, from the FIELDS section, select PY Sales field.
121. From the ribbon select Modeling -> Format -> Currency -> \$ English (United States)
122. Similarly, from the FIELDS section, select Revenue field.
123. From the ribbon select Modeling -> Format -> Currency -> \$ English (United States)

124. In the Revenue by Year visual select 2018 column. Notice Maximus UE-04 has nearly 158% growth compared to last year.

125. Select Matrix visual.
126. From the Values section, select the arrow next to % Growth.
127. Select Conditional Formatting -> Background color.

Note: Conditional formatting can be applied using font color or data bars as well.

Background color dialog opens. This dialog provides options to format background color either using rules or diverging colors.

128. Select the Diverging checkbox.
129. Select OK.

Note: Conditional formatting can also be based on another column using Color based on drop down.
