---
title: "COVID-19 Hospitalization Analysis"
author: "Jeff Cegan"
date: "2022-03-17"
output: html_document
---

<br>

This work was done for FEMA to give a weekly status update on COVID-19 in Region 1 (R1) covering New England (MA, CT, RI, VT, NH, ME).
This documentation refers to the file “hospital_data_analysis.Rmd,” which is used to generate plots for the weekly PowerPoint report named “Region I COVID Hospital Utilization Analysis.”

### Initialization:
-	The script “hospital_data_analysis.Rmd” is an R markdown script. Therefore, R Studio Desktop needs to be installed on the machine where the script is run. R Studio can be downloaded for free at https://www.rstudio.com/products/rstudio/download/#download
-	The first time the script is run, tools for working with CDC ensemble forecast data will need to be downloaded (http://reichlab.io/covidHubUtils/articles/covidHubUtils-overview.html). Uncomment the first code chunk and run, installing two libraries:
    - devtools::install_github("reichlab/zoltr")
    - devtools::install_github("reichlab/covidHubUtils")
-	Several files will be needed to run analysis. These are stored in the “data” folder attached, which must be downloaded to the same folder where the script “hospital_data_analysis.Rmd” is located:
    - Population breakdown (“NST-EST2021-POP.xlsx”)
    - HHS Protect data (“[Unified] Hospital Analytic.csv”)
        - Downloaded each week from HHS Protect
        - An HHS account is required to access HHS Protect
-	Set dates in the “Set Important Variables” chunk
    - 3 dates will be updated each week (described below)
-	Set location for analysis in “Import Libraries” chunk
    - NOTE: If analyzing HRRs outside R1, change encodings in “Divide into Target HRRs” section

### Upkeep:
-	Each week, a new “[Unified] Hospital Analytic.csv” will need to be downloaded from HHS Protect to the “data” folder
-	Each week, new collection dates need to be set (“Set Important Variables” section)
o	Date most hospitals reported for HHS data (typically the previous Wednesday)
o	Latest CDC forecast date (typically the previous Monday)
o	Latest JHU case count (typically the previous Friday)

### Outputs:
- Visualizations for Slides (“Region I COVID Hospital Utilization Analysis”)
    - Screenshot the plots generated in the script on R Studio and paste in slides
- Most recent values for relevant quantities
    - These are saved as variables beginning with “current” (i.e. current_deaths, current_cases, etc.)
    - Use these values to get the most up to date values as needed

