---
title: "COVID-19 Hospitalization Analysis"
author: "Jeff Cegan"
date: "2022-03-17"
output: html_document
---

<br>

USACE-ERDC's analysis to deliver weekly status updates to FEMA Region 1 on COVID-19 hospitalizations in New England (MA, CT, RI, VT, NH, ME).
This README refers to the file “hospital_data_analysis.Rmd,” which is used to generate plots for the weekly PowerPoint report named “Region I COVID Hospital Utilization Analysis.”

### Initialization:
-	The script “hospital_data_analysis.Rmd” is an R markdown script. Therefore, R Project and R Studio Desktop needs to be installed on the machine where the script is run. R Studio can be downloaded for free at https://www.rstudio.com/products/rstudio/download/#download
-	The first time the script is run, tools for working with CDC ensemble forecast data will need to be downloaded (http://reichlab.io/covidHubUtils/articles/covidHubUtils-overview.html). Uncomment the first code chunk and run, installing two libraries:
    - devtools::install_github("reichlab/zoltr")
    - devtools::install_github("reichlab/covidHubUtils")
-	Two data files are also needed to run the analysis. To be read by the code, these files must be stored in the “data” folder, which must be located in the folder where the script “hospital_data_analysis.Rmd” resides.
    - Population breakdown (“NST-EST2021-POP.xlsx”) - located in this repository
    - HHS Protect data (“[Unified] Hospital Analytic.csv”) - not located in this repository due to large file size (>3GB)
        - Downloaded each week from HHS Protect
        - Must be placed in the "data" folder before running the code
        - An HHS account is required to access HHS Protect
-	Set dates in the “Set Important Variables” chunk
    - 3 dates will be updated each week (described in Upkeep section below)
-	Set location for analysis in “Import Libraries” chunk
    - Note: If analyzing HRRs outside Region 1, change encoding in “Divide into Target HRRs” section

### Upkeep:
-	Before running, the most recent “[Unified] Hospital Analytic.csv” file needs to be downloaded from HHS Protect to the “data” folder
-	The user needs to specify new collection dates (“Set Important Variables” section)
    - Date most hospitals reported for HHS data (typically the previous Wednesday)
    - Latest CDC forecast date (typically the previous Monday)
    - Latest JHU case count (typically the previous Friday)

### Outputs:
- Visualizations for Slides (“Region I COVID Hospital Utilization Analysis”)
    - Screenshot the plots generated in the script on R Studio and paste in slides
- Most recent values for relevant quantities
    - These are saved as variables beginning with “current” (i.e. current_deaths, current_cases, etc.)
    - Use these values to get the most up to date values as needed

