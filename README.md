# People_Counter

The People Counter project has three major components:
1) R Script
	The People_Counter.Rproj project opens an R project that helps the user create a processed dataset from the raw dataset imported from eco-viso.
	The PowerBI.Rmd script allows the user to process raw people counter data and outputs processed files in the Data/Processed folder and the Data/Processed/PowerBI folder
2) Power BI Dashboard
	The power BI Dashboard lives in the People_Counter directory. It allows users to see the people counter data and select date range, counter, weekday/weekend
3) Data folder
	The data folder contains a Processed folder, Raw folder. The raw data downloaded from eco-visio should go in the Raw folder

Process for Updating Dashboard!
1) Save new raw data file in the Data/Raw folder.
2) Update the file_path in the PowerBI.Rmd R script
3) Run PowerBI.Rmd R script in RStudio
4) Open your Power BI file
5) Click Home -> Refresh
6) Your dashboard automatically updates with new data!
7) Verify that the "Last Updated" Card shows latest update
