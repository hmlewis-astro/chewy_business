# Project Write-Up
## The Problem with Pandemic Puppies: locating a new Chewy fulfillment facility


### Abstract

The ultimate goal of this project is to determine an ideal location for a Chewy fulfillment center. We hypothesize that understanding the density of pet-owning households per pet supply store, as well as total customer spend on Chewy products in each US county will allow us to determine an ideal location for the fulfillment center. We suggest building a geospatial clustering model to identify clusters of counties with (1) few pet supply retailers per pet-owning household and (2) high customer spend at Chewy. From our initial analysis, we find that pet owners in Mississippi, Louisiana, and Alabama&mdash;states along the Gulf Coast&mdash;have relatively fewer options in pet supply retailers than pet owners in other parts of the US. Additional data on Chewy customer spend in each US county is required to fully complete the proposed model, and determine an ideal location for the fulfillment center.




### Design

According to the [ASPCA](https://aspca.app.box.com/s/v4t7yrwalwk39mf71a857ivqoxnv2x3d), since the beginning of the COVID-19 pandemic, approximately one in five households in the US has acquired a new pet. This "pet boom" placed a serious strain on the supply chain of many pet supply companies; specifically, Chewy&mdash;an exclusively online retailer of pet food and pet-related products&mdash;[reported $20 million in extra fulfillment spend](https://news.alphastreet.com/chewy-inc-nyse-chwy-q1-2020-earnings-call-transcript/) during 2020 Q1. To prevent losses in the future, Chewy hopes to get ahead of further fulfillment and supply-chain breakdowns by opening another new fulfillment facility, and needs to determine where to locate this new facility.

**Primary impact:** determine an ideal location for the fulfillment center <br>
**Secondary impacts:** prevent extra fulfillment spend (and therefore, increase net profits), decrease the fraction of late deliveries (i.e., longer than the promised, three-day delivery), decrease average order delivery time, increase customer satisfaction

### Data

For the preliminary analysis presented here, we used data from the American Veterinary Medical Association (AVMA), which provides the total number of pet-owning households per state (within the contiguous US), along with data from the US Census (population per county), to estimate the **number of pet-owning households per county**.

Data from the County Business Patterns (CBP) economic survey (carried out by the US Census Bureau, Business Statistics Branch) provides the number of veterinary, pet care (e.g., grooming), and pet supply store businesses per county; each of these three types of business generally sell some pet products&mdash;from medications and prescription diet foods, to toys and accessories&mdash;so we consider each of these types of businesses to be pet supply retailers. We calculate the total **number of pet supply retailers per county**, only for counties with three or more of _each_ of these types of businesses (required for anonymity).

We used these data to determine which US counties have very few pet service businesses per pet-owning household (i.e., the density of pet-owning households per pet service business) to determine how "under-served" (or "over-served") pet owners are in each US county.


### Algorithms

#### Cleaning & EDA
All cleaning and data analysis is carried out in Excel.

From the AVMA data, we find that approximately 59% of households (~72 million households) in the US own one or more pets. Because the AVMA data give pet-ownership by state, we divide the total number of pet-owning households per state into the counties by population. For example, in a state with 100,000 pet-owning households, we assume that a county with 1% of the human population also has 1% of the pet-owning households, i.e., 1,000 households.

Given the CBP database, we drop rows from the data that break the total number of pet supply retailers down into subcategories based on the number of employees; we only need information about the total number of pet supply retailers, and not the number of employees at each retailer.

#### Aggregation
The total number of pet supply retail establishments in each county is aggregated into a pivot table in the Excel workbook. The pivot table is joined with the table containing the number of pet-owning households per county, and this table is imported to Tableau for visualization.

#### Visualization
The interactive Tableau dashboard containing these data and analyses can be downloaded [here](https://github.com/hmlewis-astro/chewy_business/raw/main/Chewy_Fulfillment_Center_EDA.twbx) or can be accessed on the web [here](https://public.tableau.com/views/ChewyFulFillmentCenterEDA/PublicDashboard?:language=en-US&:display_count=n&:origin=viz_share_link).

**Figure**: Screencap of the interactive Tableau dashboard.

<p align="center">
<img src="https://github.com/hmlewis-astro/chewy_business/blob/main/final_pres/chewy_dashboard_full.png" width="800" />
</p>


### Tools
- Excel for data cleaning, aggregation, and analysis
- Tableau for plotting and interactive visualizations


### Communication

In addition to the slides and visuals presented here, the Tableau dashboard [Chewy Fulfillment Center](https://public.tableau.com/views/ChewyFulFillmentCenterEDA/PublicDashboard?:language=en-US&:display_count=n&:origin=viz_share_link) will be included in a blog post to be shared on my (work-in-progress) GitHub Pages [website](https://hmlewis-astro.github.io/).
