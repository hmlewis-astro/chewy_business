# Minimum Viable Product
## The Problem with Pandemic Puppies: improving fulfillment efficiency at Chewy


### Opportunity
According to the [ASPCA](https://aspca.app.box.com/s/v4t7yrwalwk39mf71a857ivqoxnv2x3d), since the beginning of the COVID-19 pandemic, approximately one in five households in the US has acquired a cat or dog. This "pet boom" placed a serious strain on the supply chain of many pet supply companies; specifically, Chewy&mdash;an exclusively online retailer of pet food and pet-related products&mdash;[reported $20 million in extra fulfillment spend](https://news.alphastreet.com/chewy-inc-nyse-chwy-q1-2020-earnings-call-transcript/) during 2020 Q1, due to inventory imbalances and an increase in expedited (one- to three-day shipping) orders. To prevent further losses, by the end of 2020, Chewy had opened additional fulfillment facilities in Archbald, PA, and Salisbury, NC.

A new wave of COVID-19 infections are projected to occur in the coming fall/winter months, with further lockdowns, extended work-from-home, and (likely) more pandemic pet adoptions expected. Chewy hopes to get ahead of further fulfillment and supply-chain breakdowns by opening another new fulfillment facility, and needs to determine where to locate this new facility.


### Impact Hypothesis
We hypothesize that understanding the density of pet-owning households per pet supply store and the total customer spend on Chewy products per capita (total customer spend depends on the total population, and needs to be standardized across counties of differing size)&mdash;and how those metrics have changed since March 2020 (the start of the pandemic)&mdash;will allow us to determine an ideal location for the fulfillment center.


**Primary impact:** determine an ideal location for the fulfillment center <br>
**Secondary impacts:** prevent extra fulfillment spend (and therefore, increase net profits), decrease the fraction of late deliveries (i.e., longer than the promised, three-day delivery), decrease average order delivery time, increase customer satisfaction


<table style="width:100%">
  <tr>
    <th>Assumptions</th>
    <th>Risks</th>
  </tr>
  <tr>
    <td>Observed increase in pet and pet supply spending since March 2020 will persist through the next wave of COVID-19 infections</td>
    <td>If pet supply spending returns to pre-pandemic levels, new fulfillment center may be under-utilized and lead to a loss in net profits</td>
  </tr>
  <tr>
    <td>Extra fulfillment centers are required to meet additional fulfillment needs</td>
    <td>Slow delivery times might be due to one or more existing, understaffed facilities that simply require more fulfillment specialists</td>
  </tr>
  <tr>
    <td>Location should depend on where there is a high density of pet-owning households per pet supply store (i.e., few pet supply stores to support the population)</td>
    <td>Few pet supply stores in an area may mean that there is not a market for these products or that one particular store already has a monopoly on the market</td>
  </tr>
</table>


### Solution
The solution path pursued here is to build a geospatial clustering model to predict customer spend based on:
1. the number of pet-owning households,
2. the number of existing options available for in-person purchase of pet supplies,
3. the historical total customer spend (per capita) on Chewy products, and
4. how these factors have changed (e.g., increase/decrease of pet ownership) since March 2020.

**Data:**<br>
To fully pursue this solution path, the data _required_ are:
- a complete survey of pet-owning households continued over several years that has been updated since March 2020,
- a complete survey of existing pet supply stores continued over several years that has been updated since March 2020, and
- data on historical customer spend at Chewy, ideally, at a small, geographically granular-level.

The data _available_ are:
- an approximate count of the number of pet-owning households in each state from a survey carried out in December 2016 (not updated since March 2020),
- an approximate count of the number of veterinary, pet care, and pet supply businesses in each US county from a survey carried out in December 2019 (not updated since March 2020),
- (likely) data on historical customer spend at Chewy at a small, geographically granular-level (though not availably publicly)

**Measures of success:**
- Technical: model achieves a high silhouette score (how similar a datapoint is to other datapoints in its cluster, relative to datapoints not in its cluster) and identifies a reasonable location for the new fulfillment center (i.e., not too close to an existing fulfillment center, not in an area with very few pet-owning households)
- Non-technical: amount of fulfillment spend above or below that of the previous quarter, amount of change in the fraction of late deliveries, amount of change in the average order delivery time

**Other possible Solution Paths:**
- Determine the location (within the contiguous US) that would maximize the distance between all existing centers and the new fulfillment center
- Analyze fulfillment data&mdash;e.g., the largest fraction of incorrect fulfillments and longest average order delivery time&mdash;to determine warehouses that might be at/over-capacity; locate new facility nearby (within 100 miles) the struggling facility
- Rather than optimizing the location to be in a region with a lack of other pet supply stores, optimize to be in a competitive area (i.e., with a high number of pet-owning households, and many other pet supply options); potential to take business from other/smaller companies


### EDA
For the preliminary analysis presented here, we used data from the American Veterinary Medical Association, which provides the total number of pet-owning households per state (within the contiguous US), along with data from the US Census (population per county), to estimate the number of pet-owning households per county. Data from the County Business Patterns (CBP) economic survey (carried out by the US Census Bureau, Business Statistics Branch) provides the number of veterinary, pet care (e.g., grooming), and pet supply store businesses per county; each of these three types of business generally sell some pet products, from medications and prescription diet foods, to toys and accessories. We have used these data to determine what US counties have very few pet service businesses per pet-owning household (i.e., the density of pet-owning households per pet service business) to determine how "under-served" (or "over-served") pet owners are in each US county.

Approximately 59% of households (~72 million households) in the US own one or more pets. On average, over all US counties and states, pet supply retailers&mdash;which here includes veterinarians, pet care (e.g., groomers), and pet supply stores&mdash;each serve 1,400 pet-owning households, though this number ranges widely from ~100 pet-owning households served per retailer (for Carter County and Powder River County, MT) to nearly 6,000 pet-owning households per retailer (in Robertson County, TN). Of the top 5 states with the highest average number of pet-owning households served per retailer, three of these states lie along the southern Gulf Coast: Mississippi, Louisiana, and Alabama; these states are, on average, the most "under-served" by in-person pet supply stores. Without seeing Chewy customer spend data from all regions, we cannot decisively say that one of these states will be an ideal location for the new fulfillment center; however, there is not an existing Chewy fulfillment facility in this area of the country. These three states may provide a starting point for future modeling.

**Future Modeling:**<br>
To build the full model proposed here, we require some additional data. We need data on historical customer spend at Chewy, as well as some information about changes in pet-ownership (at the state- or county-level) over the course of the COVID-19 pandemic. The first of these dataset would need to be provided by Chewy. The second required dataset might be able to be derived from changes in Chewy customer spend in each US county since March 2020.

Given access to the required data, continued efforts on this project include developing a full geospatial clustering model (likely using K-means or density-based spatial clustering/DBSCAN) incorporating these data. The model will identify spatial clusters of US counties with similar characteristics in the number of pet-owning households per pet supply store and customer spend (per capita) at Chewy; we will then choose from among these clusters the one that appears to be most "under-served" by other pet supply stores, and select a precise location for the new fulfillment center.



### Preliminary Viz/EDA

Below is a beta version of the dashboard that we plan to submit to Chewy for review of the initial EDA.

<p align="center">
<img src="https://github.com/hmlewis-astro/chewy_business/blob/main/chewy_dashboard_mvp.png" width="1000" />
</p>
