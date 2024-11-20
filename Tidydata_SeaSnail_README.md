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

- There is little known about how parasites present across multiple sites and seasons could indirectly affect seagrass ecosystems through host behavior modulation. 

The proposed study seeks to:

- **understand the indirect consequences parasite diversity has upon ecosystem structure though host behavior modulation.**
- I will investigate the cascading trait-mediated indirect effects of different trematodes on ecosystem structural components: biodiversity and species richness of meiofauna and infauna.
- I will also investigate the potential mechanisms in which trematodes indirectly instigate these structural changes (host movement behavior, benthic chlorophyll-a, nutrient flux, and sediment properties)

**I hypothesize that differences in trematode size and physiological impact are the likely mechanisms behind trait-mediated indirect effects upon mudflat ecosystem structure: HQ is the largest trematode with the most physiological effect on I. obsoleta, followed by LS, and lastly ZL.**

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

*I. obsoleta* is a macroconsumer gastropod host to 9 known digenean trematode parasites. 

This parasite-host community is observed in seagrass beds of shoalgrass (*Halodule wrightii*) and eelgrass (*Zostera marina*). 

In addition to collecting snails and seagrass samples, samples of mesograzers residing within seagrass beds are also taken. 

Each site is visited once across each sample season, adding up to 10 site visits per season and 30 site visits across 2024. 

During each site visit at peak low tide, snails were located based on distance from shore and seagrass beds. 
- Snail population density was measured within 0.5 m^2 quadrats (n=5) every 6 m along a 24-m transect, starting near shore at 0 m and going out as the tide receded
- Randomly collected to gain a population’s natural range of shell size and infection prevalence
- Snails smaller than 10 mm were not collected due to infection status being more likely in snails with longer exposure time in their habitats. 

At the tip of the 24-m transect, seagrass shoot density and species metrics were collected with random placements of a 0.5 m2 quadrat within or next to seagrass beds (n=5). 
- Shoot density was counted by the number of shoots intact in the sediment within the quadrat.
- All dead seagrass was removed from the quadrat prior to counting shoot density.
- Within each quadrat, five blades of each seagrass species were snipped with shears just above the sediment line and placed into sample bags labeled with quadrat numbers 1-5, site name, and sample date.
- Distance between each quadrat was recorded, as well as water depth.
- A sample of amphipods and microfauna was collected in each quadrat with a small aquarium net and deposited into a plastic container with a small amount of 70% isopropyl ethanol and seawater, labeled with quadrat number, site name, and sample date.
- If any second intermediate or definitive hosts were spotted at sites, common names of species were recorded on data sheets.

Lastly, the following abiotic measurements were recorded using a YSI and transect: 
- water temperature (C)
- air temperature (C)
- salinity (ppt)
- water depth (cm)
- low tide height (from https://www.saltwatertides.com/)

### RStudio Tidydata

1 Identify working directory and import data file tidydata_SeaSnail_2024.csv
2 


### For final output, see tidydata_SeaSnail_2024_NEW.Rmd
### For final visual output, see tidydata_SeaSnail_2024.knit.pdf