# MTA Turnstile EDA

### Description
In this project, we analyze turnstile data in New York City by the Metropolitan Transit Authority (MTA) to assist the Women Tech Women Yes (WTWY) in maximizing attendance at its annual gala and increasing awareness around the organization's efforts to increase the participation of women in technology. Additionally, we analyze income tax data for NYC provided by the IRS to further understand the target demographic of people who work in tech and ride the subway to and from work each day.

### Target Variables
The target variables for this project include daily turnstile entries across the top 10 busiest subway locations, as well as higher income families and tech companies and their proximity to subway stations.

### Data Used
We used turnstile data from the MTA for 6 separate weeks over the first 6 months of the 2020 to include the weeks of: January 18, February 8, March 21, April 11, May 30, and June 6. The data can be retrieved here:

http://web.mta.info/developers/turnstile.html

Geographic data (the variables GTFS Latitude and GTFS Longitude) on the stations in our turnstile data were retrieved from a second source published on the MTA website:

http://web.mta.info/developers/data/nyct/subway/Stations.csv

Because the station names and IDs of the geographic data were published in a different form from our turnstile data, a separate dataset was required to map the stations in our turnstile data with an ID variable called "Complex ID." The Complex ID variable for each station name and remote unit for our turnstile data was identified in a dataset published on qri, a platform for datasets. A link to this data can be found here:

https://qri.cloud/nyc-transit-data/remote_complex_lookup

We note that no code was taken from the separate analysis  performed by the author on aggregating turnstile entries and exits from the MTA data.

With our geographic coordinates mapped to our turnstile data, we then relied on the following dataset that contained the geographic coordinates of US Zip Codes:

https://public.opendatasoft.com/explore/dataset/us-zip-code-latitude-and-longitude/table/?q=

Zip Codes from this dataset were mapped to each MTA station's geographic coordinates by taking identifying the zip code closest to the station. This was operationalized by taking the Euclidean distance between the station's coordinates and the zip code's coordinates.

Once zip code information was mapped to our turnstile data, we used the Individual Income Tax Statistics from the IRS for 2018 in NYC. Here, we looked at the total number of tax returns made at each income level for each zip code. We calculated the proportion of total tax returns made by individuals and households with annual incomes greater than $200K for each zip code as our measure for high-income earners. The data can be retrieved here:

https://www.irs.gov/statistics/soi-tax-stats-individual-income-tax-statistics-2018-zip-code-data-soi

We used this article detailing top-funded NYC start-up zip codes to create one of our graphs and to locate stations in those same zip codes:

https://www.builtinnyc.com/2016/08/09/nyc-fundings-zipcode-2016

### Tools Used
* Jupyter
* MATPLOTLIB
* Seaborn
* Pandas

### Possible Impacts of the Project
The information we obtained can be used by organizations such as WTWY to place street teams at subway stations that are likely to gain the most signatures from individuals interested in tech. The information can also be used to further focus in on the target demographic such as the percentage by station or location that are women and their average age and the time of day that sees the greatest traffic.
