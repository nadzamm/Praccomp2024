# SeaSnail PracComp Project
## Meghan Nadzam
### Data Reorganization Prior to R Entry

Data was recorded on field data sheets and entered into individual Excel datasheets per site. 

Data was entered after each field day, dissection of snails, determination of snail infection, and identification of parasitic trematode species infecting a snail. 

Field sheets were scanned in for storage and filed in order by date comprehensively in a binder.

Upon completing all data entry and dissections from the 2024 field seasons 
- Early Summer
- Late Summer
- Fall

Data reorganization and comprehension begain in a single large Excel file (xlsx) for the purpose of data analysis in RStudio. 

This file is referred to as tidydata_SeaSnail_2024.csv.

**Note:** Multiple columns in tidydata_SeaSnail_2024.csv are completely empty. 

- These are for seagrass processing and biomass measurements of seagrass blades and epibionts. Seagrass samples have not been processed.  

#### Project Summary

Specific species of trematodes are known to influence consumption of epiphytes off seagrass blades by their host the eastern mudsnail (*Ilyanassa obsoleta*). 

The proposed study seeks to:

- **understand the indirect consequences parasite diversity has upon ecosystem structure though host behavior modulation.**

Data is collected across 10 sample sites:
- Manatee Street Park
- 103 Sunny Point
- 135 Jones Landing
- 113 Mary Lane (hereafter Reference Marsh)
- Pine Knoll Shores
- University of North Carolina: Institute of Marine Science (UNC IMS)
- Carrot Island
- Harkers Island Bridge
- Miramar Road
- 465 Oak Hammock

Also collected across:
- 3 seasons (Early SUmmer, Late Summer, Fall)
- 3 regions of North Carolina's coastal shores (Bogue Sound, Back Sound, and the Straits).

Lastly, the following abiotic measurements were recorded using a YSI and transect: 
- water temperature (C)
- air temperature (C)
- salinity (ppt)
- water depth (cm)
- low tide height (from https://www.saltwatertides.com/)

### RStudio Tidydata

- Identify working directory and import data file tidydata_SeaSnail_2024.csv
- Create a new variable "seasnail <-" to represent the entrire dataset
- Use typeof command to identify each variable's mode and identify when what variable modes would need to be changed upon future filtering
- str command to visualize all 43 variables as a list for seasnail
- Pulled tidyverse, ggplot, ggExtra, ggstatsplot, paletteer, and statsExpressions from library
- Piping R to read left to right when using dplyr::select
- Use dplyr::select to subset variable columns in the seasnail dataset, removing all columns completely empty and do not contain data
- (-) symnbol in front of each column name to remove it from the new subset
- Create new variables based on the subset created with piping between dplyr::select and filter
    - seasnail_season_salinity
        - Comparing salinity across all sites and seasons, so need to include site_id, date, season, and salinity_ppt
        - Mutate command on date to change its mode to ymd(date) instead of "integer"
        - Filter command (!is.na) to remove all rows that did not include salinity measurements (had N/A)
- Repeat creation of new variables, piping, dplyr::select, mutate, and filter for remaining comparisons
    - seasnail_season_watertemp
    - seasnail_season_airtemp
    - seasnail_season_ltheight
    - seasnail_season_waterdepth
- Create histograms and scatter plots using ggplot, followed by saving images of each graph
- ggplot each variable using X axis always as Date, fill always as season, and Y axis as the changing measurable variable
    - Axis labels and title created with labs command
    - geom_col or geom_point command used to show distribution of data
    - theme_ggstatsplot() + scale_colour_paletteer_d
        - used to visualize data distribution with gridlines and simple axes
    - facet_wrap ( ~ site_id) to show differences of each variable across site and season
        - only on the histograms
    - seasnail_season_waterdepth used geom_point and geom_smooth
        - geom_point assigns color per season and the data correlating with each season by date
        - geom_smooth for the GLM and confidence intervals across each season
    - scale_x_date(date_breaks = "1 month", date_labels = "%b")
    - scale_y_continuous(limits = c(15,35))
        - both used to adjust x and y axes to specifically read the value ranges we want

Create general linear models between parasite prevalence and an abiotic variable
- water temperature
- salinity

- Made new datasheets and new variables, deriving from the original data csv file: seasnail
    - filter and mutate again to remove rows with N/a
    - each plot created with:
        - geom_smooth(method='lm', se=TRUE)
        - geom_point(aes(color = site_id), size=3)
        - theme_ggstatsplot() 
        - labs
        -  theme(plot.title), theme(legend.position=), scale_colour_paletteer_d("MetBrewer::Hiroshige"), and scale_y_continuous(limits = c())
            - above parameters set in specific to which abitic variable being analyzed
        - created "model" variables to calculate statistic summaries

Create Rank abundance curves for all parasite species abundance across each season in 2024 and then specifically in Pine Knoll Shores

- create new data CSV files with all necessary data
- filter and mutate each season's data CSV files to remove rows and columns with N/a's
- create date and season as factors
- installing new packages "BiodiversityR", "ggrepel" and new themes to create the rank abundance curves
- use "patchwork" package to form a figure for my thesis propsal
- PKS curve
    - same filtering of new data CSV files, but only creating the factor for date and now site_id
      - site is the same across all abundances quantified
      - is a comprehensive curve of parasite abundance across all seasons in 2024, so no seasonal factor is needed


### For final output, see tidydata_SeaSnail_2024_proposal.Rmd
### For final visual output, see tidydata_SeaSnail_2024_proposal.pdf
### For final rank curve output, see RankAbundance_2024 copy.Rmd
### For final rank curve visual output, see RankAbundance_2024 copy.pdf
