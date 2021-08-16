Instructor notes:
- I'm seeing two impacts: one is to determine where to put a third location and the other is to prevent extra fulfillment spend. Which is the primary and which is the secondary impact? Each would include different types of modeling. What kinds of models align with each impact? What is your primary project here? Or you could discuss both goals. --- Primary impact: determine where to put a third location, an appropriate location should prevent extra fulfillment spend
- I would leave off customer satisfaction unless you want to go deeper into determining a metric for satisfaction and evaluating what success would look like. You can definitely use it! But it's a third (and as you mention, contingent) impact. --- An appropriate location would also improve customer satisfaction (rating of each order, etc.)
- Looks good! I would just sort out your impacts and modeling goals. Also think about what other solution paths might exist. ---

# Minimum Viable Product
## The Problem with Pandemic Puppies: improving fulfillment efficiency at Chewy

### Opportunity
According to the [ASPCA](https://aspca.app.box.com/s/v4t7yrwalwk39mf71a857ivqoxnv2x3d), since the beginning of the COVID-19 crisis, approximately one in five households in the US has acquired a cat or dog. This "pet boom" placed a serious strain on the supply chain of many pet supply companies; in particular, Chewy&mdash;an exclusively online retailer of pet food and pet-related products&mdash;[reported $20 million in extra fulfillment spend](https://news.alphastreet.com/chewy-inc-nyse-chwy-q1-2020-earnings-call-transcript/) during 2020 Q1, due to inventory imbalances and an increase in expedited (one- to three-day shipping) orders. To prevent further losses, by the end of 2020, Chewy opened additional fulfillment facilities in Archbald, PA, and Salisbury, NC.

With a new wave of COVID-19 infections projected to occur in the US in the coming fall/winter months, with further lockdowns expected (and likely more pandemic pet adoptions!), Chewy hopes to get ahead of potential fulfillment and supply chain breakdowns by opening another new fulfillment facility. The company needs to determine where to locate this new facility in order to best serve parts of the country with (1) a lack of other pet supply stores, (2) increasing pet ownership, (3) an increasing number of orders, and (4) the highest risk of late delivery from Chewy.

### Impact Hypothesis

We want to determine where to locate a new Chewy fulfillment center. We hypothesize that understanding the number of pet-owning households and the number of existing options available for pet supplies at the county-level (and how those metrics have changed since March 2020) will allow us to determine an ideal location for the fulfillment center.
- Primary impact: determine an ideal location for the fulfillment center
- Secondary impacts: prevent extra fulfillment spend (and therefore, increase net profits), decrease the fraction of late deliveries (i.e., longer than the promised, three-day delivery), decrease average order delivery time, increase customer satisfaction


### Solution

The solution path pursued here is to build a model to predict customer buying patterns based on these (and other) factors, specifically from online retailers like Chewy, to better inform this expansion.

- How would you specify "customer buying patterns"? How much they spend? How many orders they make? How many items per order? Will they repurchase? List out the different kinds of models you might want to build. --- Under "Solution"


- Measurem of success: After the new facility is opened, the success of the project will be measured by the amount of fulfillment spend above or below that of the previous quarter, and by the fractional decrease in late orders.

#### Other possible Solution Paths:
- Determine the location (within the continental US) that would maximize the distance between all existing centers and the new fulfillment center
- Analyze fulfillment data&mdash;e.g., the largest fraction of incorrect fulfillments and longest average order delivery time&mdash;to determine warehouses that might be at/over-capacity; locate new facility nearby (within 100 miles) the struggling facility
- Rather than optimizing the location to be in a region with a lack of other pet supply stores, optimize to be in a competitive area (i.e., with a high number of pet-owning households, and many other pet supply options); potential to take business from other/smaller companies


#### Risks and Assumptions

### Data and Methods

For the preliminary analysis, I plan to use data from the American Veterinary Medical Association, which provides the total number of households owning pets per state, along with data from the US Census to estimate the number of pet-owning household per county. Data from the County Business Patterns (CBP) economic survey (carried out by the US Census Bureau, Business Statistics Branch) provides the number of veterinary/pet care (e.g., grooming) and pet supply store businesses per county. I will use these data to determine what counties have very few pet service businesses per pet-owning household to determine how "under-served" (or "over-served") pet owners are in each county.

There are approximately 3000 counties in the US, so each dataset has at least 3000 rows; the CBP data have multiple rows for each county, with one row for each business type (i.e., one row for veterinary service businesses, one for pet care services, and one for pet supply businesses). The CBP data include columns for the county, state, and geolocation of each county, the NAICS code for each business type (i.e., unique identifier), the meaning of the NAICS code, the employment size range for each group, and the number of establishments in that range, the annual payroll, the Q1 payroll, and the total number of employees at those establishments.

### Preliminary Viz/EDA
