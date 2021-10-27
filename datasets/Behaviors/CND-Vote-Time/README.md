# Vote-Time Export Codebook
> From [Center for New Data](https://www.newdata.org)

## Introduction
This dataset was produced by way of the Center for New Data’s replication of the [Chen et al](https://www.scientificamerican.com/article/smartphone-data-show-voters-in-black-neighborhoods-wait-longer1/) [methodology](https://www.nber.org/system/files/working_papers/w26487/w26487.pdf).
The paper examines "*Racial Disparities in Voting Wait Times*" ([doi](https://direct.mit.edu/rest/article/doi/10.1162/rest_a_01012/97747/Racial-Disparities-in-Voting-Wait-Times-Evidence)).
It used geolocation data to estimate arrival times and voting durations at polling locations on election day for the 2020 General Election.


### Hackathon Usage
The [codebook](./Vote-Time_Export_Codebook.pdf) as well as statistical summaries of an Iowa-subset ([here](./iowa_data_description.html)) are provided in this repo.

Given licensing restrictions on downstream uses of this data, please contact [Osonde Osoba](mailto:oosoba@rand.org) for access to the data.

### Notes on Data Quality and Data Cleaning
- Devices with UPPER_MINUTES_WAITING > 180 minutes have been removed.
- Polling locations (and associated devices) with < 25 devices have been omitted.
- There are devices in the dataset that were detected at the same polling location multiple times in the same day. The Chen et al method that was replicated for this work did not establish a filter for this type of aberrant data, and our replication of the data provided here do not offer a correction. Therefore, for these devices, correct interpretation is not currently clear. We advise multiple ways to deal with these data, including potentially:
  - Collapsing repeated visits into a single visit if they are under X minutes together (on the logic that perhaps they represent a single visit that was interrupted by an aberrant ping or itinerant movement activity in and outside the detected threshold); and/or
  - Excluding devices with more than one visit to the same polling location in the same day.
