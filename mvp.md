# Minimum Viable Product
## The Problem with Pandemic Puppies: improving fulfillment efficiency at Chewy

### Opportunity
According to the [ASPCA](https://aspca.app.box.com/s/v4t7yrwalwk39mf71a857ivqoxnv2x3d), since the beginning of the COVID-19 pandemic, approximately one in five households in the US has acquired a cat or dog. This "pet boom" placed a serious strain on the supply chain of many pet supply companies; specifically, Chewy&mdash;an exclusively online retailer of pet food and pet-related products&mdash;[reported $20 million in extra fulfillment spend](https://news.alphastreet.com/chewy-inc-nyse-chwy-q1-2020-earnings-call-transcript/) during 2020 Q1, due to inventory imbalances and an increase in expedited (one- to three-day shipping) orders. To prevent further losses, by the end of 2020, Chewy had opened additional fulfillment facilities in Archbald, PA, and Salisbury, NC.

A new wave of COVID-19 infections are projected to occur in the coming fall/winter months, with further lockdowns, extended work-from-home, and (likely) more pandemic pet adoptions expected. Chewy hopes to get ahead of further fulfillment and supply-chain breakdowns by opening another new fulfillment facility, and needs to determine where to locate this new facility.

### Impact Hypothesis

We hypothesize that understanding (1) the number of pet-owning households, (2) the number of existing options available for in-person purchase of pet supplies, and (3) the total customer spend on Chewy products at the county-level&mdash;and how those metrics have changed since March 2020&mdash;will allow us to determine an ideal location for the fulfillment center. We will use these metrics to determine the location for the new fulfillment center.


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
    <td>Slow delivery times might actually be due to one or more existing, understaffed facilities that simply require more fulfillment specialists</td>
  </tr>
  <tr>
    <td>Location should depend on where there is a high density of pet-owning households per pet supply store (generally, few pet supply stores to support the population)</td>
    <td>Few pet supply stores in an area may mean that there is not a market for these products or that one particular store already has a monopoly on the market</td>
  </tr>
</table>

### Solution

The solution path pursued here is to build a spatio-temporal clustering model to predict customer buying patterns based on these (and other) factors, specifically from online retailers like Chewy, to better inform this expansion. in order to best serve parts of the country with (1) a lack of other pet supply stores, (2) increasing pet ownership, (3) an increasing number of orders, and (4) the highest risk of late delivery from Chewy

- How would you specify "customer buying patterns"? How much they spend? How many orders they make? How many items per order? Will they repurchase? List out the different kinds of models you might want to build. --- Under "Solution"

- Measurem of success: After the new facility is opened, the success of the project will be measured by the amount of fulfillment spend above or below that of the previous quarter, and by the fractional decrease in late orders.



**Other possible Solution Paths:**
- Determine the location (within the contiguous US) that would maximize the distance between all existing centers and the new fulfillment center
- Analyze fulfillment data&mdash;e.g., the largest fraction of incorrect fulfillments and longest average order delivery time&mdash;to determine warehouses that might be at/over-capacity; locate new facility nearby (within 100 miles) the struggling facility
- Rather than optimizing the location to be in a region with a lack of other pet supply stores, optimize to be in a competitive area (i.e., with a high number of pet-owning households, and many other pet supply options); potential to take business from other/smaller companies


### Data

For the preliminary analysis presented here, we used data from the American Veterinary Medical Association, which provides the total number of pet-owning households per state (within the contiguous US), along with data from the US Census (population per county), to estimate the number of pet-owning households per county. Data from the County Business Patterns (CBP) economic survey (carried out by the US Census Bureau, Business Statistics Branch) provides the number of veterinary, pet care (e.g., grooming), and pet supply store businesses per county. We have used these data to determine what counties have very few pet service businesses per pet-owning household to determine how "under-served" (or "over-served") pet owners are in each county.

**Future Modeling:**
To build the full model proposed here, we require additional data... These data would need to be provided by Chewy.



### Preliminary Viz/EDA

Insert EDA plots here
