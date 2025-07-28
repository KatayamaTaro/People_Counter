# People\_Counter



<div align="center">
  <img src= "https://github.com/taroNPS/People_Counter/blob/main/Temp/7-2d-girl-side-walk-animation-gif.gif" width="500">
</div>

## The People Counter project has three major components:

### 1\) R Script

The People\_Counter.Rproj file opens an R project that helps the user create a series of processed datasets from the raw dataset imported from eco-visio (Eco-visio is the platform that manages people counter data). The newly created processed dataset can then be used for analysis in the PowerBI dashboard. The PowerBIScript.Rmd script allows the user to process raw people counter data (from Data/Raw) and outputs processed files in the Data/Processed/PowerBI folder. Note that processed datasets can also be used for analysis separate from the powerBI dashboard.

## R Script How to:

If you are completely new to R, then good luck!  

<img src= "https://github.com/taroNPS/People_Counter/blob/main/Temp/larry.jpg" width="200">

Just kidding. However, I am assuming that you have R downloaded on your computer and know how to open scripts. Alright, first open the script People_Counter\Scripts\PowerBIScript.Rmd. 
Next, you will want to update the script with the newest raw data. Update the file path accordingly! 

<img width="500" height="200" alt="image" src="https://github.com/user-attachments/assets/e8a436fe-452d-4a4d-bdcd-a1354e1c6559" />

Next press run by clicking on the green arrow.
<img width="500" height="200" alt="image" src="https://github.com/user-attachments/assets/8e0e0f07-4287-4f3d-bc68-1551388ef41f" />

That's it! The processed dataset should live in Data/Processed/PowerBI folder.

<img src= "https://github.com/taroNPS/People_Counter/blob/main/Temp/e.gif" width="200">

### 2\) Power BI Dashboard

The power BI Dashboard lives in the People\_Counter root folder. It allows users to select date range, counter, weekday/weekend to see usage trends. The counts utilize the 'IN' count of all the counters. This ensures that counters are not double counting, meaning it does not count the "IN" and the "OUT".The dashboard has three pages.

1. The first 'Instructions' page gives the user more information about the other pages and gives instructions on how to use the dashboards.
2. The 'Macro Trends' page allows user to see ALL the collected data from all counters. It also tallies the total trail usage counts since the counters started recording.
3. The second page named 'Weekly Trends' shows the trail usage broken down by weekday. It is mainly intended for the user to see how trail usage changes depending on day of week. You can sort by counter, date range, weekend/weekday.
4. The third page named 'Annual Projections' shows the annual trail use prediction based on available data and extrapolation. This does not account for seasonality. It is a simple average daily usage calculation multiplied by 365.

  To updated the dashboard, press the "Refresh" button on the Home tab
  <img width="1351" height="531" alt="image" src="https://github.com/user-attachments/assets/86c26d82-2dff-437e-b2dd-9d9596034318" />


### 3\) Data folder

The data folder contains a Processed folder, Raw folder. The raw data downloaded from eco-visio should go in the Raw folder. The data file naming convention should follow All\_20250507\_mmdd.csv format! mmdd represents the two digit month and two digit date.

## Process for downloading data from eco-visio

1. Go to https://www.eco-visio.net/
2. Log in with credentials
3. Go to 'Analysis' tab
4. Click on 'Period' and change selection to 'Manual Selection'.
5. Set custom date range from 5/7/2025-xxxx. Replace xxxx with the most recent date. Click 'OK'
6. Do not change the 'Sites'. Keep at 'Whole Domain'
7. Click 'Time Series'. Keep the 'Type of Graph' on 'Curve'. Change the 'Interval' to 'Hour'. 'Keep 'Show Events'
8. Click on 'Show More', and toggle on 'In' and 'Out' and toggle off 'Total'
9. Click on 'Table' at the top right
10. Click on 'Download'
11. Save the file in the appropriate location as csv with the appropriate naming convention. Location, something like- C:\\Users\\tkatayama\\OneDrive - DOI\\Documents\\Projects\\R\\People\_Counter\\Data\\Raw
12. Naming convention: All\_20250507-mmdd.csv
13. Change mm and dd to appropriate two digit month and date

## Process for Updating Dashboard

1. Save new raw data file in the Data/Raw folder.
2. Update the file\_path in the PowerBI.Rmd R script
3. Run PowerBI.Rmd R script in RStudio
4. Open your Power BI file
5. Click Home -> Refresh
6. Your dashboard automatically updates with new data!
7. Verify that the "Last Updated" Card shows latest update
