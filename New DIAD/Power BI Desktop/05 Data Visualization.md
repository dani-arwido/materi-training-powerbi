# Power BI Desktop – Data Visualization

Having done the data exploration and visualization you have found good insights to share with your team. In this section, you will create a professional report from which you and your entire team can benefit.

At the end of this section, you will build a report like the one shown in the screenshot.

Let’s add Collapse and Expand capability to the Matrix visual. 1. Select Matrix visual. 2. In the VISUALIZATIONS panel, select the paint roller icon to format the visual. 3. Scroll down and expand Row headers section. 4. Scroll down to +/- icons and using the slider, turn the feature On. Notice now you have the Expand/Collapse icon in the matrix, giving a pivot table like experience. Color/size of these icons can be further formatted.

Let’s remove Revenue by Category clustered bar chart. 5. Hover over Revenue by Category visual. 6. From the top right corner select the ellipsis 7. Select Remove to delete the visual.

Initially we added a filter to load 3 years of data. Let’s load the complete data. 8. From the ribbon, select Home -> Edit Queries. Power Query Editor window opens. 9. From the left panel, select Sales query.

10. From the right panel, under APPLIED STEPS click on the X next to Filtered Rows1 to remove the 3-year filter.
11. Select Home -> Close & Apply to load the data. Sales data is reloaded, this time all the data is loaded. It might take a couple of minutes as we are loading ~7 million rows.
    Make sure the report is filtered by VanArsdel using Manufacturer slicer. Remove all other filters.

At this point your report page should look something like the screenshot. Once data is loaded, notice Revenue by Year visual. You will see columns for years 2012 through 2018.

Let’s add a Date slicer so we can control how many years of data we want to analyze.

12. Click on the white space in the canvas. From the VISUALIZATIONS section, select Slicer visual.
13. From FIELDS section, click the checkbox next to Date field in Date table. Notice we have a range slicer with a slider.
14. Move the slicer to filter the data to 1/1/2014 to 12/31/2018 or type in the values.

15. Hover over the date slicer.
16. Select the arrow from the top right corner. Notice following options are available – Before, After, List, Dropdown and Relative. Feel free to try out the various options.
17. Select Relative. Notice this has options to filter data by the Last x years, months, days or Next x years, months, days, etc. Feel free to try out various options.
18. Hover over Manufacturer slicer visual.
19. On the top right corner select the arrow.
20. Select List.
21. in VISUALIZATIONS panel select the paint roller icon. This opens the formatting options available for a visual.
22. Expand General section, select Horizontal from the Orientation dropdown.
23. Notice the Slicer visual is updated. You can resize the visual, so all the manufacturers are listed horizontally. Note: There are other options to change the Outline color, weight, etc.
24. Select VanArsdel.
25. Collapse General section.
26. Note: Expand Selection Controls section. Notice there is an option to enable Select All option in the visual. There is also an option to make the slicer multi select. Feel free to explore other formatting options.

It will be nice to add logos of the manufacturer to the slicer. Let’s do it.

27. From FIELDS section, select Logo field from Manufacturer table.
28. From the ribbon, select Modeling -> Data Category -> Image URL. Setting data category to Image URL helps Power BI to understand that it is a URL and it can access the data.

29. From the canvas, select Manufacturer slicer.
30. From FIELDS section, drag and drop Logo from Manufacturer table to Field well.
31. Select Logo field.
32. Resize slicer visual as needed.
33. Select VanArsdel logo to filter all the other visuals.

34. Select Revenue by Year visual.
35. From VISUALIZATIONS panel, select Line and clustered column chart to change the visual type.
36. From FIELDS section, drag and drop % Growth field from Sales table to Line values.

This provides a representation of the revenue and growth over time.

37. Select Revenue Card visual. Let’s change this to a Gauge visual.
38. From VISUALIZATIONS panel, select the Gauge visual.
39. From FIELDS section, drag and drop PY Sales field to Target value.
40. Resize the visual as needed. Now we can compare Revenue with the target.

It will be nice to change the colors on the visuals.

41. Select Gauge visual.
42. From VISUALIZATIONS panel, select paint roller icon.
43. Expand Data Colors section.
44. Select the arrow next to Fill color.

Notice you can pick a color from the default color palette or pick Custom colors.

Let’s check out some of the themes available.

45. From the ribbon, select Home -> Switch Theme -> Sunset. Notice colors on all the visuals updated. Feel free to try the other out of the box themes.

Marketing department has provided standard color themes to be used across reports. We can use Report Theme feature in Power BI by uploading a theme. Report Theme requires a JSON file where the data colors, background, foreground and table Accent colors are defined. The JSON file can be used across all the reports.

46. From the ribbon, select Home -> Switch Theme -> Import Theme.
47. File browser dialog opens. Navigate to /Data/Theme folder.
48. Select DIADTheme1 file and select Open.
49. Once theme is imported, a success dialog opens. Select Close.
    Notice colors on all the visuals updated. Your report should look something like the screenshot at this point. This one is good, but too much red in it. Marketing team has provided one more theme, let’s try it.
50. From the ribbon, select Home -> Switch Theme -> Import Theme.
51. File browser dialog opens. Navigate to /Data/Theme folder.
52. Select DIADTheme2 file and select Open.
53. Once theme is imported, a success dialog opens. Select Close.  
    Notice colors on all the visuals updated. Your report should look something like the screenshot at this point.

This theme looks good. Now most of the visuals are blue in color, let’s add some contrast.

54. Select the Gauge visual.
55. From VISUALIZATIONS panel, select paint roller icon.
56. Expand Data colors section.
57. Select the drop down next to Target. Notice the color palette is different now.
58. Select black color. Notice the change in the visual.

59. Collapse Data colors section.
60. Expand Data Labels section.
61. Increase Text size to 10.
62. Expand Target section.
63. Increase Text size to 10.

64. Select Matrix visual.
65. Drill up to Segment level.
66. Select Revenue by Country visual.
67. Drill up to Country level.
68. From VISUALIZATIONS panel, select paint roller icon.
69. Expand Data colors section.
70. Select a light shade of gray as the Default color.
71. Enable and expand Data labels.
72. Change Display units to Millions.

Notice there a lot of formatting options. E.g. visual title can be changed and formatted, you can add a border and background to the visual, etc. Feel free to explore the options.

73. Select Revenue and % Growth by Year visual.
74. From VISUALIZATIONS panel, select paint roller icon.
75. Expand Data colors section.
76. Select black color for % Growth.
77. Select a light shade of gray as the Default Column color.

Let’s add a report title.

78. From the ribbon, select Home -> Text box. Notice a text box visual is added.
79. Resize the visual as needed.
80. Enter Manufacturer Analysis in the Text box.
81. Highlight Manufacturer Analysis to format the text.
82. Select Segoe (Bold) as the font.
83. Select 36 as the font size.
84. Resize the text box as needed.

85. From the ribbon, select View.
86. Select the checkbox next to Show Gridlines and Snap Objects to Grid. This will help with aligning the visuals.
87. Move and align the visuals like the screenshot. As you move visuals notice the red smart guide helps aligning them. Uncheck Show Gridlines and Snap Objects to Grid options to disable these features.
88. Rename the page to Manufacturer.

We can also use a background image to format the reports. Let’s try it.

89. Select + icon in the bottom of the page to create a new page. You will be navigated to a Page 1.
90. Click on the white space in the canvas.
91. From VISUALIZATIONS panel, select paint roller icon.
92. Expand Page Background section.
93. Select Add Image button.
94. File browser dialog opens. Browse to /DIAD/Data folder.
95. Select Background file.
96. Select Open.

97. From Image Fit drop down, select Fit.
98. Slide Transparency slider to 0%. Notice we have a template which has place for header and slots for images.
99. Navigate to Manufacturer page.
100.  Select Revenue by Country visual.
101.  From the ribbon select Home -> Copy.
102.  Navigate to Page 1.
103.  From the ribbon select Home -> Paste.
104.  Resize the visual and place it as shown in the screenshot.

105.  Navigate to Manufacturer page.
106.  Select Manufacturer slicer.
107.  From the ribbon select Home -> Copy.
108.  Navigate to Page 1.
109.  From the ribbon select Home -> Paste.
110.  Sync visuals dialog opens. Select Sync. This will keep Manufacturer slicer in both the pages in sync. Changing slicer in one of the pages will update visuals in both the pages.
111.  Resize the slicer and place it as shown in the screenshot.

112.  Similarly, copy the report title, gauge, matrix and the line and clustered column visual.
113.  Resize and arrange the visuals as shows in the screenshot.

Let’s add a logo.

114. From the ribbon, select Home -> Image.
115. File browser dialog opens. Browse to /DIAD/Data folder.
116. Select VanArsdel_Logo file.
117. Select Open.
118. Resize the visual as needed.
119. Drag the visual to the top left corner of the page. Note: The logo is transparent. You need to place it on the blue background to see it.  
     Let’s change the font color of report title.
120. Highlight Manufacturer Analysis.
121. Select the arrow next to A for font color.
122. Select white color.

Out of the box, Power BI has a good selection of visuals. However, there is always a use-case where you need a custom visual. To meet this need, the visualization engine is open sourced. Power BI community contributes visuals which are available in the marketplace. You can add and use these visuals in your reports. There is also an option to create your own visual and import it into Power BI Desktop. Let’s add a custom visual.

123. From VISUALIZATIONS section, select the ellipsis in the last row of visuals.
124. Select Import from marketplace.
125. Type play axis in the search box and select search.
126. Select Add next to Play Axis (Dynamic Slicer). Note: Notice the checkmark in the blue star. This sign is used to identify certified custom visuals. Custom visuals that meet Power BI teams coding requirements are certified. Certified custom visuals support features like export to Power Point, ability to display in subscription emails which is not supported by non-certified custom visuals.
127. Import custom visual dialog opens. Select OK. Notice a new visual is added to the list of available visuals.

128. Click on the white space in the canvas.
129. From VISUALIZATIONS section, select the newly imported Play Axis visual.
130. From FIELDS section, click the checkbox next to Date field in Date table.
131. From VISUALIZATIONS panel, select paint roller icon.
132. Expand Colors section.
133. Enable Show all option.
134. Resize and position the visual as shown in the screenshot.

135. Enable drill mode in matrix visual.
136. Select Extreme category to drill down to Extreme products.
137. Select Play in the Play axis visual. Notice all the visuals update as play axis moves through years. You can view Product performance over time as well as performance of countries over time. Play axis provides an option to analyze data over time (or any other dimension) across all visuals in the page.
138. Once you are done playing through the years, in the matrix visual drill back up to Product Category level.
139. Disable drill mode in matrix visual. There are a lot of custom visuals available and new ones are added periodically.
     Now we have a report ready, let’s use Bookmarks to tell the story we discovered. Bookmarks capture the currently configured view of a report page, including filtering and the state of visuals which makes it easy to present the story.
140. From the ribbon, select View.
141. Select the checkbox next to Bookmarks Pane to enable Bookmarks. BOOKMARKS pane opens.
142. Click on Add in BOOKMARKS pane. This will add the current state of the visual to the bookmark.

143. Click on the ellipsis next to the newly created Bookmark 1.
144. Select Rename to rename it to Initial State
145. In Revenue by Country visual, select USA column.
146. Hover over Revenue by Country visual and select the ellipsis on the top right corner.
147. Select Spotlight.
148. In the BOOKMARKS pane, select Add. This will add a new bookmark with the current state of the report.
149. Click on the canvas.
150. Select Australia in Revenue by Country visual.
151. In the BOOKMARKS pane, select Add. This will add a new bookmark with the current state of the report.

152. From the BOOKMARKS pane, select View. You are in Bookmarks slide show mode. You will be in the first bookmark which we called Initial State. Notice on the bottom of the report pane there is an option to navigate between bookmarks.
153. You can use the arrows to navigate between bookmarks and tell your story.
154. From BOOKMARKS pane, select Exit to exit Bookmarks slide show mode.

If time permits, feel free to explore other options available with Bookmarks like Selected Visuals and more as you continue to build the story.

155. From the ribbon, select View.
156. Uncheck Bookmarks Pane.
157. Collapse the Visualizations and Filters pane by clicking on the arrows. Report should look as shown in the figure. Save the file.
158. Select File -> Save.

You have built your first report!!!

159. Navigate to /DIAD/Reports folder.
160. Open DIAD Final Report.pbix file.

This file uses the same dataset that you used for the lab. We have added a few more visuals and formatted the reports. Feel free to explore the report.

You have successfully completed the hands-on lab in creating a report to share to your team. The next section covers creating a dashboard from this report so that you can easily share it to your team. You have learned a quick overview of various functionality in Power BI Desktop to get accelerated. There are a lot more features for you to build upon this on your own data.
