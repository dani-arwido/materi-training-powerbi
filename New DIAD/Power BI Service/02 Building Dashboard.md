# Power BI Service – Building Dashboard

In this section, we will create a dashboard that will combine data from the Market Share report as well as Social report.

At the end of the section, we will create a dashboard that looks like the screenshot.

Let’s start with exploring the report.

1. From the left menu, select REPORTS > DIAD Final Report. You will be navigated to the report you just uploaded.
2. In the map visual, enable drill down by hovering over the visual.
3. Select the down arrow on the top right corner of the visual.
4. Select Australia to drill down to State level.
5. In the map visual, disable drill mode by selecting the down arrow on the top right corner of the visual.
6. Select the bubbles on different states and notice that as you select the states, other visuals get cross filtered. The behavior is like that of Power BI Desktop.
7. Select the top arrow on the top left corner to drill up to Country level.
8. Hover over the bubble chart on the bottom right of the screen.
9. Select Focus mode icon so the visual fits in the canvas.
10. Select Extreme from the legend. This will highlight the performance of Extreme segment over time. Notice the spike in 2018.
11. Select the Play axis on the bottom left of the screen. This will show the revenue and % growth of each Product Segment over time.
12. Select Extreme from the legend again to remove the filter.
13. Select Back to Report on the top left to navigate back to report view.

Let’s pin visuals to the dashboard.

14. Hover over VanArsdel Market Share card visual.
15. Select the pin icon on the top right of the visual. Pin to dashboard dialog opens.
16. We do not have a dashboard yet. Let’s create one. With New dashboard selected, enter VanArsdel in the text box.
17. Select Pin.

Notice alert messages are displayed stating the dashboard is ready to view.

Notice in the left panel, VanArsdel Dashboard is created under DASHBOARDS.

18. From the left panel, select DASHBOARDS -> VanArsdel. Notice the VanArsdel Market Share tile is pinned to the dashboard.
19. Click on VanArsdel Market Share, notice you are navigated to the report.

Tiles in dashboard are not interactive.

20. Hover over % Growth by Manufacturer visual.
21. Select the pin icon on the top right of the visual. Pin to dashboard dialog opens.
22. Make sure VanArsdel is selected in the dropdown.
23. Select Pin.
24. Close out alert dialogs.
25. Hover over Revenue by Year and Manufacturer visual.
26. Select the pin icon on the top right of the visual. Pin to dashboard dialog opens.
27. Make sure VanArsdel is selected in the dropdown.
28. Select Pin.
29. Close out alert dialogs.
30. Navigate to By Manufacturer page.
31. From the top right corner, select the down arrow. Notice manufacturer slicer displays.
32. Select VanArsdel from the slicer. This will filter the visuals.
33. From the top right corner, select the up arrow. Notice manufacturer slicer collapses.
34. Pin the gauge visual to the dashboard.
35. Pin Revenue by Country visual to the dashboard.
36. Close out alert dialogs.

Note: VanArsdel filter is applied to the tile that is pinned to the dashboard.

37. From the left panel, select DASHBOARDS -> VanArsdel. Notice all the visuals are pinned as tiles to the dashboard. You will see the visuals on the dashboard like the screenshot.

Each visual on the dashboard is called a tile. The tiles represent the data chosen and will be kept up to date as the data in the data model updates. Tiles are not interactive.

Let’s organize the dashboard now.

38. Select and move the gauge tile as shown in the screenshot.
39. Select the bottom right corner of the tile and move it diagonally to change the image size.

Tiles can be of various sizes (1x1 to 5x5). Drag the tile using the bottom right corner to resize. As you are dragging, note the gray shadow which indicates the size of the tile when you stop dragging.

40. From the top menu, select Add tile. Add tile dialog opens.
41. Select Image as the source.
42. Select Next.
43. In URL text box, enter https://raw.githubusercontent.com/Char lesSterling/DiadManu/master/Vanarsdel. png Note: URL is case sensitive.
44. Select Apply.

Notice a new tile with VanArsdel logo is added to the dashboard.

45. Resize and rearrange the tiles as shown in the screenshot.

Revenue by Country tile shows Revenue by Country for VanArsdel, so let’s rename it.

46. Hover over Revenue by Country tile.
47. Select the ellipsis on the top right corner of the tile.
48. Select Edit Details. Tile Details dialog opens.
49. Change Title to VanArsdel Revenue.
50. Select Apply.

It will be nice to have a visual that represents Market Share by country. Notice on the top of the visual, there is an option to Ask a question about your data. This is similar to Ask a question in the desktop.

51. In the text box start typing, VanArsdel market share. Notice a card visual is created.
52. Continue typing VanArsdel market share by country. Notice a bar chart is created.
53. Continue typing VanArsdel market share by country as treemap. Notice a treemap visual is created.

Note: Remember we renamed tables. One of the reasons we did it is to make it user friendly for Q&A.

54. From the top right of the screen, select Pin Visual.
55. Pin to dashboard dialog opens. Select Pin to pin the visual to VanArsdel dashboard.
56. Close the alert dialogs.
57. Select Exit Q&A to navigate back to the dashboard.

Notice the visual is added as tile to the dashboard. Clicking on the tree map visual will navigate you back to the Q&A section.

Power BI quickly searches different subsets of your dataset while applying a set of sophisticated algorithms to discover potentially-interesting insights. You can run insights against a dataset or dashboard tile. Let’s generate insights on a dashboard tile. When we run insights on a dashboard tile, instead of searching for insights against an entire dataset, search is narrowed to the data used to create a single dashboard tile. This is often referred to as scoped insights.

58. Hover over the line chart on the dashboard.
59. Select the ellipsis on the top right corner. Select View Insights.

You will be navigated to Focus mode for the line chart.

59. Scroll on the Insights panel to review the various insights Power BI can generate. Notice that there is an option to pin insight visuals to the dashboard.
60. Click on Exit Focus mode on the top left to navigate back to the dashboard.

We want to be notified when VanArsdel’s Market Share goes above or below a threshold. We can set up alerts to achieve this.

61. Hover over VanArsdel Market Share tile.
62. Click on the ellipsis on the top right corner of the tile.
63. Select Manage alerts. Manage alerts dialog opens.
64. Select Add alert rule dialog. Notice you can add Above and Below threshold and notification frequency can be set.

This is an introduction to managing alerts. Complete functionality is not covered in this lab.

65. Select Cancel to close the dialog.
66. Select Don’t Save.
67. Click on VanArsdel Market Share tile to navigate to the report.
68. In map visual, right click on Australia bubble and select Drillthrough -> By Manufacturer.
69. You will be navigated to By Manufacturer page of the report with Australia filter applied to the report page.
70. Hover over matrix visual.
71. Select focus mode icon on the top right corner of the visual.
72. From the top menu, select Explore -> Show Next Level. Notice now data is at Product Segment level. From the top menu, select Explore -> Drill up.
73. This time from the top menu, select Explore -> Expand to next level. Notice now data is at Segment level but laid out as a hierarchy.
74. Select Back to Report to navigate back to the report view.
75. Notice all the functionality that is available in Power BI Desktop is available in the service. E.g. Show Data, See Records, etc.
76. From the top menu, select View and enable Bookmark pane. Bookmark pane opens on the right. There are 2 options, Personal bookmarks and Report bookmarks. Report bookmarks: are the bookmarks report author created (we did this in Power BI Desktop). Personal bookmarks: Report consumer can create their own bookmarks.
77. Select View in the Report bookmarks pane. Notice you can view and navigate through the bookmarks using the arrow in the bottom of the screen. The behavior is like in Power BI Desktop. Select Exit in Bookmark pane to close it.

Power BI provides an option to get quick insights into the complete dataset.

78. In the left panel, hover over DATASETS -> DIAD Final Report.
79. Select the ellipsis. 99. Select Quick Insights.

It might take a few minutes for the insights to be created. Once insights are ready a message appears of the top right corner.

80. Select View insights.
81. A quick insights report is displayed based on the dataset. This provides insights into data you may have missed and helps to get a quick start with creating dashboards. Hovering over each report provides an option to Pin it to a dashboard. As you scroll down, notice there is a bar chart % Growth BY PRODUCT. Might be interesting to analyze this.

Marketing team has captured data from social networks and built a Power BI report. Let us publish this report to Power BI service and analyze the data.

82. From the bottom of the left panel, select Get Data.
83. Get Data screen is displayed. Under Import or Connect to Data, select Files.
84. From Get Data -> Files screen select Local File.
85. File browser dialog opens. Navigate to /DIAD/Reports folder.
86. Select Social.pbix file and click Open.
87. Once the report is published, an alert message appears. Close the alert dialog. In the left panel, notice under REPORTS, we see Social.

88. Select REPORTS -> Social to be navigated to the Twitter page of the Social report. Marketing team has captured the retweets of #VanArsdel. Notice there is a spike in 2018. Does this have any correlation to the spike in sales in Australia? Let’s investigate. Hover over Retweets visual and click on Focus mode icon.
89. Enable drill mode.
90. Drill down to month level for the year 2018. Notice there is a big spike in retweets in the last few months of 2018. If you remember from the demo this is the reason for the increase in sales.
91. Drill back up to Year level.
92. Select Back to Report to navigate back to report view.
93. Let’s add this visual to our Dashboard
94. Hover over Retweets visual.
95. Select the pin icon on the top right of the visual. Pin to dashboard dialog opens. Pin the visual to VanArsdel dashboard.
96. Close the alert dialogs.
97. From the left panel, select DASHBOARDS -> VanArsdel to navigate to the dashboard. Notice two new tiles are added to the dashboard. The retweets tile we just pinned and a default tile that is added when a new dataset is added.
98. Hover over Social.pbix tile.
99. Click on the ellipsis on the top right corner.
100.  Select Delete tile to remove the tile.
101.  Notice you can have tiles from multiple reports and Q&A section on a single dashboard.
102.  Navigate back to VanArsdel dashboard.
103.  Notice on the top right of the menu bar, there is options to add this dashboard to the favorites. Click on Favorite option.
104.  Now click on Favorite in the left panel. Notice the dashboard is added to the list. This is an easy way to access all your favorite or most used dashboards quickly. Click on the ellipsis on the top right corner of the page, next to Share option. Notice there are options to duplicate, print and refresh dashboard.

On the top right corner of the screen, next to Favorite, there is Set as featured option. Set as Featured dashboard sets the dashboard as the default dashboard that user will land on every time they login.

105. In the left panel, select VanArsdel Dashboard.
106. Select Set as Featured from the top menu.
107. A confirmation dialog is displayed. Select Set as Featured Dashboard. This sets VanArsdel as the featured/default dashboard.
108. Navigate back to VanArsdel dashboard.
109. If you have not already done so, move the visuals to look like the screenshot. You have successfully built a dashboard.
