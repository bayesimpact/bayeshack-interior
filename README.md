# Bayes Hack Interior Prompt

_How can data make access to the outdoors more equitable?_

## Prompt

Research suggests time in nature is an important component of physical, social, and mental wellbeing, but also that various barriers to access disproportionately impact urban communities [1](https://www.fullerlab.org/wp-content/uploads/2014/08/Shanahan-et-al-2014.pdf) [2](http://www.sciencedirect.com/science/article/pii/S1618866712000891). By making open spaces, parks, and public lands easier to reach and explore, more citizens can be part of the benefits that these lands afford society.

Transform droves of data about America's public lands into tools to drive new planning and policy or integrate models into applications that break down the inequities facing socially and economically underserved communities.

Increasingly, computational tools are becoming a part of how we understand and approach our great outdoors. Through a better understanding of the interactions between individuals and their natural environment, we can inform novel data-driven, cost-effective, and citizen-centric approaches.


## In this repo

* `analysis/` - Jupyter notebook files (which you can view right here on GitHub) loading the data and exploring a few things.

## Getting started

Install all the Python dependencies needed for the notebook by executing `pip install -r requirements.txt`.


## Available data sources

This paragraph will list the datasets we identified as interesting when we had a quick look at the available sources. This is however not a comprehensive list and **we encourage you to dig deeper into the portal**.


### Recreation Information Database

This an http API with extensive documentatin that can be found [here](https://usda.github.io/RIDB/). Register for an API key [here](https://ridb.recreation.gov/?action=register) and check out my [example notebook](examples/recreation_database_api.ipynb).

In case you don't feel like using their API, you can download the whole dataset from [here](https://ridb.recreation.gov/?action=datadownload).


### Data Dictionary for RIDB and NCSU

#### RIDB

http://usda.github.io/RIDB/#data-dictionary

#### NCSU

There are three NCSU datasets available at [https://cnr.ncsu.edu/geospatial/bayes-hack/] (https://velocity.ncsu.edu/dl/1uRTn6g/276112)

The [NRRS_PPL_reservationdata_AllYears.csv](https://velocity.ncsu.edu/dl/1uRTn6g/276112) file is the cleaned RIDB data compiled by NCSU.  There are two additional datasets that are aggregates of this information.  This section identifies the differences between the two datasets.  Contact Stacy if you use Matlab and want the .mat file for this dataset. 

This dataset includes most of the original RIDB fields along with newly calculated fields by NCSU.  The additional fields are:

1. Great circle distance - distance between visitor ZIP centroid and destination facility x y in km.
2. Duration - length of stay.  Difference between arrival and departure in days.
3. Lead time - difference between reservation order date and vacation start date.
4. Person nights - duration x number of ppl in the party.  Say I have two people in my party staying for 5 nights, total person nights would be 10.

### The Integrated Resource Management Applications Portal (IRMA)

The [portal](https://irma.nps.gov/Portal) offers a large amount of datasets in different formats. Notable categories are:

#### [Data Store](https://irma.nps.gov/DataStore/)

* [Park Boundaries](https://irma.nps.gov/DataStore/Reference/Profile/2224545?lnv=True)
* [Natural Resource Inventories](https://irma.nps.gov/DataStore/DataStoreReports/Public/Inventory%20Tracking) which contains statistics about natural resources. For example
  - air quality data
  - water quality
  - climate
  - species occurence
  - vegetation mapping
* [Natural Resource Data Series](https://irma.nps.gov/DataStore/Reference/Profile/2007596) contains results from many different studies, partly in the form of lengthy pdf reports, partly as data in tables, like for example the usage forecast of parks. Unfortunately [even the tables like this](https://irma.nps.gov/DataStore/Reference/Profile/2228011) are in pdf format.
* [Visitor Survey Card Program](https://irma.nps.gov/DataStore/Reference/Profile/2208605) has results from a Visitor Satisfaction Survey Results with **actual spreadsheets!**.


#### [STATS (Park Visitor Use Statistics)](https://irma.nps.gov/Stats/)

Starts with a graphical frontend to browse datasets for different parks (probably also possible to access the data programatically). There is pretty cool data for each park, for example

* anual visitors ([example](https://irma.nps.gov/Stats/SSRSReports/Park%20Specific%20Reports/Annual%20Park%20Recreation%20Visitation%20(1904%20-%20Last%20Calendar%20Year)?Park=ZION))
* visitation comments per park ([example](https://irma.nps.gov/Stats/SSRSReports/Park%20Specific%20Reports/Monthly%20Visitation%20Comments%20By%20Park?Park=ZION))
* traffic counts per month ([example](https://irma.nps.gov/Stats/SSRSReports/Park%20Specific%20Reports/Traffic%20Counts?Park=ZION))


#### [Species in the Parks](https://irma.nps.gov/NPSpecies/)

Get species lists with the occurrence and status of species in more than 300 NPS national parks. ([example](https://irma.nps.gov/NPSpecies/Search/SpeciesList/ZION))


### The U.S. Fish & Wildlife Service

On [their website](https://www.fws.gov/gis/data/national/) hosts comprehensive geospatial data describing parks and ecosystems. The highlights are:

* [USFWS Regional Boundaries](http://catalog.data.gov/dataset/us-fish-and-wildlife-service-regional-boundaries)
* Baseline [inventory of public assets](http://catalog.data.gov/organization/4d7ad1cd-3641-420b-8116-e4082f49cd44?q=Transportation&sort=score+desc%2C+name+asc&metadata_type=geospatial) owned and maintained by the USFWS.
* [Landscape Conservation Cooperatives](https://www.sciencebase.gov/catalog/item/55b943ade4b09a3b01b65d78)
* The [Critical Habitat portal](http://catalog.data.gov/organization/fws-gov?q=geospatial+critical+habitat+ngda+roy&sort=score+desc%2C+name+asc) is an online service for information regarding Threatened and Endangered Species final Critical Habitat designation across the United States.


### Bureau of Land Management GeoCommunicator

The Bureau of [Land Management GeoCommunicator](http://www.geocommunicator.gov/GeoComm/) hosts overviews of the administrative status of BLM areas and other federal lands.

* Oil and Gas lease sale parcels
* BLM Administrative Areas
* Federal Lands
* Federal National Monuments, Conservation Areas, and Wilderness Areas
* BLM Range Allotments and Pastures
* BLM Wild Horse and Burro Herd Areas and Herd Management Areas
* BLM Solar Energy Study Areas
* Public Land Survey System - PLSS (township, range, section, lots, surveys) - Downloadable
* Rights-of-Way (ROW)
