# Project Proposal
## The Problem with Pandemic Puppies: improving fulfillment efficiency at Chewy

According to the [ASPCA](https://aspca.app.box.com/s/v4t7yrwalwk39mf71a857ivqoxnv2x3d), since the beginning of the COVID-19 crisis, approximately one in five households in the US has acquired a cat or dog. This "pet boom" placed a serious strain on the supply chain of many pet supply companies; in particular, Chewy&mdash;an exclusively online retailer of pet food and pet-related products&mdash;[reported $20 million in extra fulfillment spend](https://news.alphastreet.com/chewy-inc-nyse-chwy-q1-2020-earnings-call-transcript/) during 2020 Q1, due to inventory imbalances and an increase in expedited (one- to three-day shipping) orders. To prevent further losses, by the end of the year, Chewy had opened additional fulfillment facilities in Archbald, PA, and Salisbury, NC.

With a now third (fourth?) wave of COVID-19 projected to occur in the US in the coming fall/winter months, with further lockdowns expected (and likely more pet adoptions!), Chewy hopes to get ahead of potential fulfillment and supply chain breakdowns by opening another new fulfillment facility. The company needs to determine where best to locate this new facility.


### Question:
In this project, we aim to determine the best location for a new fulfillment facility that will best serve parts of the country with (1) a lack of other pet supply stores, (2) increasing pet ownership, (3) an increasing number of orders, and (4) the highest risk of late delivery from Chewy (a prescriptive problem). One possible solution path is to build a model to predict customer buying patterns based on these (and other) factors, specifically from online retailers like Chewy, to better inform this expansion.

The desired impact of this project is to prevent extra fulfillment spend and to decrease the fraction of late orders (i.e., longer than the promised, three-day delivery). As a side-effect, these outcomes will also increase customer and shareholder satisfaction. The impact hypothesis then, is that building a new fulfillment center in an optimum location will improve profits and customer satisfaction at Chewy. This hypothesis assumes that customer satisfaction is tied most strongly to Chewy's fulfillment of promised delivery times, rather than to their like/dislike of a specific product.

After the new facility is opened, the success of the project will be measured by the amount of fulfillment spend above or below that of the previous quarter, and by the fractional decrease in late orders.



### Data description:
For the preliminary analysis, I plan to use data from the American Veterinary Medical Association, which provides the total number of households owning pets per state, along with data from the US Census to estimate the number of pet-owning household per county. Data from the County Business Patterns (CBP) economic survey (carried out by the US Census Bureau, Business Statistics Branch) provides the number of veterinary/pet care (e.g., grooming) and pet supply store businesses per county. I will use these data to determine what counties have very few pet service businesses per pet-owning household to determine how "under-served" (or "over-served") pet owners are in each county.

There are approximately 3000 counties in the US, so each dataset has at least 3000 rows; the CBP data have multiple rows for each county, with one row for each business type (i.e., one row for veterinary service businesses, one for pet care services, and one for pet supply businesses). The CBP data include columns for the county, state, and geolocation of each county, the NAICS code for each business type (i.e., unique identifier), the meaning of the NAICS code, the employment size range for each group, and the number of establishments in that range, the annual payroll, the Q1 payroll, and the total number of employees at those establishments.

### Tools:
Excel will be used for cleaning and connecting the various datasets described, and for the preliminary exploratory analysis of the data. Tableau will be used to visualize significant findings.

### MVP:

The minimal viable product (MVP) for this project will likely be a more throughly scoped project proposal, including a more thoroughly developed impact hypothesis and some additional possible solution paths, as well as one or more key visualizations.
