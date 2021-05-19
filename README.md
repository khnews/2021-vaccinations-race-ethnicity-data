# Data: Vaccinations by state and race/ethnicity

This repository contains data used in the KHN story, [“Stark Racial Disparities Persist in Vaccinations, State-Level CDC Data Shows”](https://khn.org/news/article/covid-vaccination-stark-racial-disparities-persist-state-level-cdc-data/
 ).

The Centers for Disease Control and Prevention provided data on May 14 in response to a public records request. The original, unaltered Excel file is included here, in addition to a file of KHN’s analysis that includes population totals and computed vaccination rates.

The data includes people who have received at least one covid vaccine dose. The data covers shots as of May 14 given to 155 million people that were administered through federally run programs and federal agencies as well as by state and local authorities. The data reflects the state where a vaccine was administered, not the state of the recipient’s residence.

The [CDC file](Copy%20of%20FOIA%2021-00688%20Updated%20data%20pull%20(007).xlsx) includes vaccinations administered in all 50 states, the District of Columbia, Puerto Rico, American Samoa, Federated States of Micronesia, Guam, Marshall Islands, Northern Mariana Islands, Palau and the U.S. Virgin Islands.

The CDC data includes the following categories:

- Hispanic = Hispanic of any race or combination of races
- NHAIAN = non-Hispanic American Indian or Alaska Native
- NHAsian = non-Hispanic Asian
- NHBlack = non-Hispanic Black
- NHNHOPI = non-Hispanic Native Hawaiian or other Pacific Islander
- NHWhite = non-Hispanic white
- NHOther = non-Hispanic other race
- NHMultiracial = non-Hispanic multiracial
- Unable_to_report = unable to report race or ethnicity
- Unknown = unknown race or ethnicity

For analysis, we combined the “unknown” and “unable to report” categories into “unknown.” We merged “other” and “multiracial” into “other.”

To calculate vaccination rates by group, we joined the Census Bureau’s American Community Survey 2019 population data to the CDC data. This ACS data is not available for U.S. territories other than Puerto Rico.

Race or ethnicity is missing for 44% of people who have received doses — or nearly 69 million people — despite federal officials’ [vow](https://www.whitehouse.gov/wp-content/uploads/2021/01/National-Strategy-for-the-COVID-19-Response-and-Pandemic-Preparedness.pdf)[s](https://www.whitehouse.gov/wp-content/uploads/2021/01/National-Strategy-for-the-COVID-19-Response-and-Pandemic-Preparedness.pdf) to improve outdated data systems to better inform their vaccination efforts.

Eight states — Alabama, California, Michigan, Minnesota, South Dakota, Texas, Vermont and Wyoming — either refuse to provide race and ethnicity details in the data they send to the CDC or are missing that information for more than 60% of people vaccinated. Those states are excluded from the KHN analysis, though the CDC includes all but Texas in its [published national rates](https://covid.cdc.gov/covid-data-tracker/#vaccination-demographics-trends). KHN’s national vaccination rates by race and ethnicity include the remaining 42 states, the District of Columbia and Puerto Rico.

In some states, such as Massachusetts, Louisiana and Oregon, the multiracial category comprises a significant share of vaccines, far more than what the census lists as that state’s multiracial non-Hispanic population. This is also an issue for data in the states’ dashboards. We do not analyze any multiracial data because of concerns about the discrepancies.

The share of Native Hawaiians and Pacific Islanders who are vaccinated exceeds the population of that group in 13 states and the District of Columbia. We did not present this data in our story because of those data-quality concerns.

The CDC Excel file includes a category called “Other Unknown due to data being provided in Aggregate Form (not included in data pull)” containing 11.7 million records of the total 155 million. The vast majority of this “other unknown” data is from Texas, which does not provide demographic details of vaccine recipients to the CDC. An additional 744,000 are listed with the state as “UNK,” or unknown, which also mostly have unknown race and ethnicity. KHN excluded those records from the analysis.

The [KHN data analysis file](khn-state-raceeth-vaccinations.csv) contains the following columns:

- fips_state = 2-digit state number
- state_code = 2-letter postal code
- state_name = state/territory name
- group = race/ethnicity category
- vaxx_count = number of people with at least one covid vaccine dose
- pct_of_vaxx_total = percentage of all vaccinated people in the state/territory who are in that race/ethnicity category
- pct_of_vaxx_known = percentage of vaccinated people with known race and ethnicity in the state/territory who are in that race/ethnicity category
- vaxx_total = sum of people who are vaccinated in the state/territory
- vaccination_rate = percentage of people in the category who are vaccinated
- state_residents = number of all state/territory residents who are in that race/ethnicity category, according to ACS 2019 data
- pct_of_state = percentage of all state/territory residents who are in that race/ethnicity category, according to ACS 2019 data

## Attribution

The raw data should be credited as “CDC data provided by KHN.” The computed rates and other analysis provided here should be cited as: “according to a KHN analysis of CDC data.”

## FAQ

**Why are the national rates by race and ethnicity in the KHN analysis different from the national rates provided by the CDC? Why are some states excluded from KHN’s analysis?**

We include only states where race and ethnicity is known for at least 40% of people vaccinated. Eight states — Alabama, California, Michigan, Minnesota, South Dakota, Texas, Vermont and Wyoming — either refuse to provide race and ethnicity details in the data they send to the CDC or are missing that information for more than 60% of people vaccinated. KHN’s national vaccination rates by race and ethnicity include the remaining 42 states, the District of Columbia and Puerto Rico.

The CDC includes all states and territories except Texas, even though race and ethnicity are missing for nearly everyone in some of those other states and territories. That means that those states are effectively excluded from the [CDC dashboard’s](https://covid.cdc.gov/covid-data-tracker/#vaccination-demographics-trends) vaccination rates by race numerators (people vaccinated) while present in its denominators (total population).

**Why are these numbers different from the numbers on my state dashboard?**

Vaccine data on state dashboards excludes vaccines provided by some federal programs, such as the Indian Health Service. The CDC-provided data shared here includes vaccines provided by federal, state and local sources.

This data also reflects the state where a vaccine was administered, not the state of the recipient’s residence. This difference is most significant in the District of Columbia because a large number of people who work in the district and were vaccinated there live in Maryland and Virginia.

**Why do the Hispanic versus white rates for some states look different here than in other analyses?**

This analysis has distinct, mutually exclusive race and ethnicity categories that can be directly compared, such as white non-Hispanic and Hispanic of any race. It uses consistent categories in all states. Additionally, this data includes federal vaccine sources while state-published data does not include many of those programs.

Many states, such as Florida and Missouri, report race separately from Hispanic ethnicity in their own public reports, unlike in this CDC data. In those states, the white category is white regardless of Hispanic ethnicity, and the Hispanic category is Hispanic regardless of race. A person who is Hispanic and white would be counted in both groups. Rates for white and Hispanic should not be directly compared in those states.

**Why is the percentage with race or ethnicity unknown in this data higher than on my state dashboard?**

Some states have issues reporting complete data to the CDC. Others, including Texas, redact or refuse to share this data.

Race and Hispanic ethnicity are asked separately and are presented separately on some state websites. In many states, the percentage of records missing ethnicity is higher than the percentage missing race information. Since the CDC combines these fields in its dataset, that means that records with known race and unknown ethnicity are classified as unknown.

**Why are all of the national vaccination rates by race/ethnicity lower than the [overall vaccination rate](https://covid.cdc.gov/covid-data-tracker/#vaccinations)?**

The CDC data is missing race or ethnicity for 44% of people who have been vaccinated. The true rates by race/ethnicity group would each be higher if we had data that was complete.

**Can I compare rates by state? For example, why is the Black vaccination rate in Florida lower than the Black vaccination rate in North Carolina?**

In general, no, you should not directly compare rates for one racial/ethnic group in one state to the rate of that group in another state.

States have varying rates of data completion. For example, only 9% of records for people vaccinated in North Carolina are missing race or ethnicity, while 47% in Florida are missing that information. See answers to the previous questions about why some states have high rates of missing data. Look more at the overall trends and how rates compare within a state: Are the rates by race/ethnicity similar within the state? Is one much higher or lower?

To compare states’ overall vaccination rates regardless of race and ethnicity, look at the CDC’s [overall data by state](https://covid.cdc.gov/covid-data-tracker/#vaccinations), which does not have significant missing data problems.