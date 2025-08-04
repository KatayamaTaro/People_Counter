# People_Counter

<div align="center">
  <img src="https://github.com/taroNPS/People_Counter/blob/main/Temp/7-2d-girl-side-walk-animation-gif.gif" width="500">
</div>

## Overview

The People Counter project at Cabrillo National Monument helps to understand trails and lighthouse usage trends. It processes raw visitor count data and visualizes usage statistics using R and Power BI. While this repository is tailored towards people counter data processing and dashboard generation specific to Cabrillo National Monument, it can easily be tailored for other NPS units looking to immplement their own people counter system. For more information or help on this process, contact taro_katayama@nps.gov

## Table of Contents

- [Overview](#overview)
- [File Structure](#File-Structure)
- [Project Components](#project-components)
- [Installation](#installation)
- [Usage Example](#usage-example)
- [Process for Downloading Data from eco-visio](#process-for-downloading-data-from-eco-visio)
- [Process for Updating Dashboard](#process-for-updating-dashboard)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## File Structure
```
People_Counter/
├── Data/
│   ├── Processed/
│   │   └── PowerBI/
│   └── Raw/
├── Scripts/
│   └── PowerBIScript.Rmd
├── People_Counter.Rproj
├── PowerBI Dashboard (PowerBI .pbix file)
├── Temp/
│   ├── 7-2d-girl-side-walk-animation-gif.gif
│   ├── larry.jpg
│   └── e.gif
├── README.md
```

## Project Components

### 1) R Script

The People_Counter.Rproj file opens an R project that helps the user create a series of processed datasets from the raw dataset imported from eco-visio (Eco-visio is the platform that manages people counter devices).

#### R Script How to:

If you are completely new to R, then good luck!  

<img src="https://github.com/taroNPS/People_Counter/blob/main/Temp/larry.jpg" width="200">

Just kidding. However, I am assuming that you have R downloaded on your computer and know how to open scripts. Alright, first open the script `People_Counter/Scripts/PowerBIScript.Rmd`.  
Next, you will want to update the script with the newest raw data. Update the file path accordingly! 

<img width="900" height="400" alt="image" src="https://github.com/user-attachments/assets/e8a436fe-452d-4a4d-bdcd-a1354e1c6559" />

Next press run by clicking on the green arrow.
<img width="900" height="500" alt="image" src="https://github.com/user-attachments/assets/8e0e0f07-4287-4f3d-bc68-1551388ef41f" />

That's it! The processed dataset should live in `Data/Processed/PowerBI` folder.

<img src="https://github.com/taroNPS/People_Counter/blob/main/Temp/e.gif" width="200">

### 2) Power BI Dashboard

The Power BI Dashboard lives in the People_Counter root folder. It allows users to select date range, counter, weekday/weekend to see usage trends. The counts utilize the 'IN' count of all the counters.

1. The first 'Instructions' page gives the user more information about the other pages and gives instructions on how to use the dashboards.
2. The 'Macro Trends' page allows user to see ALL the collected data from all counters. It also tallies the total trail usage counts since the counters started recording.
3. The second page named 'Weekly Trends' shows the trail usage broken down by weekday. It is mainly intended for the user to see how trail usage changes depending on day of week. You can sort by counters.
4. The third page named 'Annual Projections' shows the annual trail use prediction based on available data and extrapolation. This does not account for seasonality. It is a simple average daily usage.

### 3) Data folder

The data folder contains a `Processed` folder and a `Raw` folder. The raw data downloaded from eco-visio should go in the Raw folder. The data file naming convention should follow `All_20250507_mmdd.csv` format.

## Installation

1. Install [R](https://cran.r-project.org/) (version >= 4.0 recommended).
2. Install [RStudio](https://posit.co/download/rstudio-desktop/) for easier script management.
3. Required R packages (install these in R):
    ```r
    install.packages(c("tidyverse", "readr", "lubridate", "dplyr", "ggplot2", "rmarkdown"))
    ```
4. Download and install [Power BI Desktop](https://powerbi.microsoft.com/desktop/).
5. Clone this repository:
    ```bash
    git clone https://github.com/taroNPS/People_Counter.git
    ```
6. Place raw data files in `Data/Raw` as described below.

## Usage Example

1. Place your latest eco-visio CSV file in `Data/Raw` (using the correct naming convention).
2. Open `Scripts/PowerBIScript.Rmd` in RStudio.
3. Update the file path in R script to match the new raw data file.
4. Run the script to generate processed data.
5. Open the Power BI file in the root directory and click "Refresh" to update the dashboard.

## Process for Downloading Data from eco-visio

1. Go to https://www.eco-visio.net/
2. Log in with credentials.
3. Go to 'Analysis' tab.
4. Click on 'Period' and change selection to 'Manual Selection'.
5. Set custom date range from 5/7/2025-xxxx. Replace xxxx with the most recent date. Click 'OK'.
6. Do not change the 'Sites'. Keep at 'Whole Domain'.
7. Click 'Time Series'. Keep the 'Type of Graph' on 'Curve'. Change the 'Interval' to 'Hour'. 'Keep 'Show Events'.
8. Click on 'Show More', and toggle on 'In' and 'Out' and toggle off 'Total'.
9. Click on 'Table' at the top right.
10. Click on 'Download'.
11. Save the file in the appropriate location as csv with the appropriate naming convention.
12. Naming convention: `All_20250507-mmdd.csv` (change mm and dd to appropriate month and date).

## Process for Updating Dashboard

1. Save new raw data file in the `Data/Raw` folder.
2. Update the file_path in the `PowerBI.Rmd` R script.
3. Run `Scripts/PowerBIScript.Rmd` R script in RStudio.
4. Open your Power BI file.
5. Click Home -> Refresh.
6. Your dashboard automatically updates with new data!
7. Verify that the "Last Updated" Card shows latest update on the Macro Trends page.

<img width="1351" height="931" alt="image" src="https://github.com/user-attachments/assets/86c26d82-2dff-437e-b2dd-9d9596034318" />

## Contributing

Contributions are welcome! Please open an issue or submit a pull request. For major changes, please discuss them first by opening an issue.

## License

This project is licensed under the [MIT License](LICENSE).

## Contact

For questions or feedback, please contact the repository owner via GitHub [issues](https://github.com/taroNPS/People_Counter/issues).

