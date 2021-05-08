1. Download the datasets Walk Score, Average Healthy Food Availability Index, Median Household Income, and Life Expectancy from Baltimore Open Data [5][6][7][8]. Ensure that all datasets are organized by Community Statistical Area.
2. Copy and paste each dataset into its own sheet in a new Excel analysis file.
3. Create a new sheet called “Relevant Columns.” From the Life Expectancy tab, copy and paste the columns “OBJECTID,” “CSA2010,” and “lifexp11” into the Relevant Columns tab. These represent the indices, the Community Statistical Area name, and life expectancy in 2011. From the Healthy Food Availability Index tab, copy and paste the column “hfai12” into the Relevant Columns tab. This represents the healthy food availability index in 2012. From the Walk Score tab, copy and paste the column “wlksc11” into the Relevant Columns tab. This represents the walk score in 2011. From the Median Household Income tab, copy and paste the column “mhhi11” into the Relevant Columns tab. This represents the median household income in 2011.
4. Copy and paste the data in Relevant Columns into a new sheet called “Cluster Analysis,” with the top left corner sitting in cell G13.
5. Add four new columns for the z-scores of each of the four measured statistics.
6. Record the mean and standard deviation with Excel formulas =AVERAGE(range) and =STDEV(range) respectively for each of the four columns in rows 1 and 2 respectively, with the values aligning with the corresponding data.
7. Use the =STANDARDIZE(value, mean, stdev) equation to find the z-scores for each of the six characteristics for every school in columns M through P in the main dataset.
8. In cell H3, type table heading “OBJECTID.” In cell H4, type table heading “CSA2010.” Label four additional table headings for the z-scores of each of the four metrics.
9. In I3:L3, input 9-14, the column numbers for each of those z-scores.
10. In the “OBJECTID” column, type 5 arbitrary numbers from 1-55 as initial guesses for the Solver problem.
11. In I5, type the equation =VLOOKUP($G5,$G$14:$P$68, I$3). Drag this equation through the column. This returns the CSA corresponding to the number.
12. In J5, type the equation =VLOOKUP($G5,$G$14:$P$68, J$3). Drag this equation through the row, then through the columns. This returns the z-scores of the neighborhoods chosen.
13. In Q13:U13, add new headings “Distance^2 to 1,” “Distance^2 to 2,” etc. until “Distance ^2 to 5”.
14. In V13, add the new heading “Min Distance.” In W13, add the new heading “Cluster.”
15. In Q14, type the equation =SUMXMY2($M14:$P14, $I$5:$L$5). This returns the squared distance between that row’s z-scores and the first anchor neighborhood’s.
16. Drag this equation horizontally through Distance^2 to 5. In R14, change all the 5’s to 6’s; in S14, change all the 5’s to 7’s, and so on.
17. Drag the Distance equations through their columns.
18. In V14, type the equation =MIN(Q14:U14). This returns the minimum distance. Drag this equation through the column.
19. In W14, type the equation =MATCH(V14, Q14:U14,0). This returns the cluster number that corresponds to the minimum distance. Drag this equation through the column.
20. In V8, type the equation =SUM(V14:V68). This returns the sum of the minimum distances. Label this value as such.
21. In the Data tab, click Solver.
22. Set the objective to V8 to Min.
23. In “By Changing Cells,” select the column of OBJECTID’s ($G$5:$G$9).
24. Set the constraints so that the column values are greater than or equal to 1, less than equal to 55, and are integers.
25. Select the Evolutionary Solving Method. Click Options, then the Evolutionary tab and set the Mutation rate to 0.5. Click OK.
26. Click Solve. When the solver is done, make sure “Keep Solver Equation” is selected, and click OK. The Anchor Schools should now reflect the Solver’s solution.
27. Copy and paste the table with the anchor school characteristics into a new sheet called “Visualization.”
28. Create a bar graph with the z-scores, with each category being a different series and the Horizontal Axis Labels being the Community Statistical Area names.
29. Add a legend and title the axes and the bar graph.
30. In a new Excel file called Clusters 1.csv, copy and paste the columns OBJECTID, CSA2010, and Cluster. Upload this to GitHub for use in Python analysis.
