# Project Proposal
## The Problem with Pandemic Puppies: improving fulfillment efficiency at Chewy

According to the [ASPCA](https://aspca.app.box.com/s/v4t7yrwalwk39mf71a857ivqoxnv2x3d), since the beginning of the COVID-19 crisis, approximately one in five households in the US has acquired a cat or dog. This "pet boom" placed a serious strain on the supply chain of many pet supply companies; in particular, Chewy&mdash;an exclusively online retailer of pet food and other pet-related products&mdash;reported $20 million in extra fulfillment spend during the first quarter of 2020, due to inventory imbalances and an increase in expedited orders.




### Question:
In this project, we seek to **determine the impact of lead-actor demographics** (primarily, gender and age) **on worldwide, lifetime movie gross** of some of the most successful movies of all time. The impact of these specific features will be interpreted from a linear regression model built to predict the lifetime revenues (target) of the top 1000+ grossing movies of all time based on e.g., the budget, rating, run time, genre, and actor demographics (features) for each movie.


### Data description:
The data required to build this model will be scraped, using `requests` and `BeautifulSoup`, from Box Office Mojo and IMDb. We will first obtain the information detailed below for 1000 movies, which will be used to build the linear regression model. Given sufficient time, we will continue scraping and obtain this information for up to &sim;10000 movies.

#### Box Office Mojo
From [Box Office Mojo](https://www.boxofficemojo.com/chart/ww_top_lifetime_gross/?offset=0), we will scrape a list of the movies with the top worldwide, lifetime grosses; this website will provide the rank and title of each movie, as well as the worldwide, domestic, and foreign lifetime grosses, and the release year for each film.

By following the available link to the detailed summary of each ranked movies (e.g., [Avatar](https://www.boxofficemojo.com/title/tt0499549/?ref_=bo_cso_table_1)), we will also obtain the domestic opening gross, budget, release date, MPAA rating, run time, and genre. Further, by exploring the ["Cast and Crew" tab](https://www.boxofficemojo.com/title/tt0499549/credits/?ref_=bo_tt_tab#tabs) for each movie, we will scrape the name and an external link (to an IMDb webpage) for the lead-actor (i.e., top billed actor) for each film.

#### IMDb
Given the name and IMDb webpage link for the lead-actor of each film, we will scrape from the actor's IMDb webpage (e.g., for [Sam Worthington](https://www.imdb.com/name/nm0941777/), lead-actor in Avatar) a basic bio, including their birth date, height, and gender. Their birth dates will be used to calculate their age at the time of release of the film.

For each movie (i.e., an individual sample of analysis), our dataset will therefore include: title, world and domestic/foreign gross, domestic opening gross, budget, MPAA rating, run time, genre, lead-actor age (at the time of release), height, and gender. Here, the total world gross will act as the target, and all other observations (excepting the movie title) will act as the features in the model.

### Tools:
Excel will be used for cleaning and connecting the various datasets described, and for the preliminary exploratory analysis of the data. Tableau will be used to visualize significant findings.

### MVP:

The minimal viable product (MVP) for this project will likely be a more throughly scoped project proposal, including a more thoroughly developed impact hypothesis and some possible solution paths, as well as one or more key visualizations.
