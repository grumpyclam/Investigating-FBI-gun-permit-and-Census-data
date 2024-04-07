# Investigate-FBI-Census-data
> Assessing, cleaning and analyzing FBI gun background checks from 1998-2017, as well as data points from the US Census from 2011-2016. gun_data.xlsx and US_Census_Data.csv are the two datasets included in the repository that I worked with. 
> 
>fbi_census_merge.html/ipynb are the final assessed, cleaned, and analyzed dataset. If you would like to skip directly to visualizations, they are at the bottom half of fbi_census_merge.ipynb. Below is the introduction you will also find the fbi_census_merge.ipynb, I figured I'd put it here so that everyone knows what they're reading before hand. 
>
>This project is one of my favorite projects that I've worked on and hope to eventually expand on it, I hope you enjoy!



For this project I wanted to investigate the trends in gun permits that were issued from 1998-2017. The provided materials were FBI background check data from 1998-2017 as well as US census information from 2010-2016. Below are the questions I'd like to answer. 

1. From the gun data that was provided, what was the overall trend in gun permits issued from 1998-2017?

2. From the answer above (the overall trend of gun permits issued) in what year and states were the highest amount of gun permits issued?

3. What states from 2011-2015 had the highest amount of gun permits issued? The census data has provided certain variables from 2011-2015, I'd like to see in the states that had the highest amount of gun permits issued from 2011-2015 and find the following:

   - The percentage of people with a bachelors degree or higher

   - The percentage of people with a disability

   - The percentage of people who went without health insurance

   - The percentage of persons in poverty

   - The percentage of people who are foreign born

   - The percentage of people (5 years or age and older) who speak more than one language at home

# gun_data_xlsx

Each column represents the type of transaction submitted to the National Instant Criminal Background Check System (NICS). In addition, each type of transaction is broken down by the type of firearm—handgun, long gun, and other. The types of firearms are defined by the Bureau of Alcohol, Tobacco, Firearms and Explosives as follows:

 - **month:** The month in which the background check took place.
 - **state:** The state in which the background check took place.
 - **permit:** The number of permits that were issued to individuals upon successful completion of a background check.
- **permit_recheck:** How many of the above permits that were issued were rechecked.
- **handgun:** (a) any firearm which has a short stock and is designed to be held and fired by the use of a single hand; and (b) any combination of parts from which a firearm described in paragraph (a) can be assembled.
- **long_gun:** a weapon designed or redesigned, made or remade, and intended to be fired from the shoulder, and designed or redesigned and made or remade to use the energy of the explosive in (a) a fixed metallic cartridge to fire a single projectile through a rifled bore for each single pull of the trigger; or (b) a fixed shotgun shell to fire through a smooth bore either a number of ball shot or a single projectile for each single pull of the trigger.
other: refers to frames, receivers, and other firearms that are neither handguns nor long guns (rifles or shotguns), such as firearms having a pistol grip that expel a shotgun shell, or National Firearms Act firearms, including silencers.
- **multiple:** denotes a background check where more than one type of firearm is associated to a single background check.
- **admin:** denotes the administrative checks that are for other authorized uses of the NICS.

What does **'prepawn'** mean?
background checks requested by an officially-licensed FFL on prospective firearm transferees seeking to pledge or pawn a firearm as security for the payment or repayment of money, prior to actually pledging or pawning the firearm. This will be associated with the prepawn_handgun, prepawn_long_gun, and prepawn_other columns.

What does **'redemption'** mean?
background checks requested by an officially-licensed FFL on prospective firearm transferees attempting to regain possession of a firearm after pledging or pawning a firearm as security at a pawn shop. This will be associated with the redemption_handgun, redemption_long_gun, and redemption_other columns.

What does **'returned'** mean?
background checks requested by criminal justice/law enforcement agencies prior to returning a firearm in its possession to the respective transferee, to ensure the individual is not prohibited. These will be associated with the returned_handgunreturned_long_gun and returned_other columns.

What does **'rentals'** means?
background checks requested by an officially-licensed FFL on prospective firearm transferees attempting to possess a firearm when the firearm is loaned or rented for use off the premises of the business. These will be associated with the rentals_handgun and rentals_long_gun columns.

What does **'private sale'** mean?
background checks requested by an officially-licensed FFL on prospective firearm transferees attempting to possess a firearm from a private party seller who is not an officially-licensed FFL. These will be associated with the private_sale_handgun, private_sale_long_gun and private_sale_other columns.

What does **'return to seller'** mean?
background checks requested by an officially-licensed FFL on prospective firearm transferees attempting to possess a firearm from a private party seller who is not an officially-licensed FFL. This will be associated with the return_to_seller_handgun, return_to_seller_long_gun, and return_to_seller_other columns.

**totals:** The total calculation of each row from every column.

**The above information was taken directly from https://www.fbi.gov/file-repository/nics_firearm_checks_-_month_year_by_state_type.pdf/view, which is an originial pdf file of the gun_data_csv. Supplemental information was taken from https://www.fbi.gov/how-we-can-help-you/need-an-fbi-service-or-more-information/nics. Both of these sources were provided via link from the original project on Github, https://github.com/BuzzFeedNews/nics-firearm-background-checks/blob/master/README.md.**

# US_Census_Data_csv
This data set is supplemental to the above gun_data_csv. It is census data that has variable data points. Some for the year 2010, 2012, 2016 as well as some cumilative data for 2010-2015 in certain rows. The columns are "Facts", "Fact Note", as well as individual columns for all 50 states. Under the "Facts" column are the variable for which the state data is provided. The "Facts" are seperated into individual rows. They are listed below and self explanatory.

- **Population estimates**, July 1, 2016, (V2016)
- **Population estimates base**, April 1, 2010, (V2016)
- **Population**, percent change - April 1, 2010 (estimates base) to July 1, 2016, (V2016)
- **Population**, Census, April 1, 2010
- **Persons under 5 years**, percent, July 1, 2016, (V2016)
- **Persons under 5 years**, percent, April 1, 2010
- **Persons under 18 years**, percent, July 1, 2016, (V2016)
- **Persons under 18 years**, percent, April 1, 2010
- **Persons 65 years and over**, percent, July 1, 2016, (V2016)
- **Persons 65 years and over**, percent, April 1, 2010
- **Female persons**, percent, July 1, 2016, (V2016)
- **Female persons**, percent, April 1, 2010
- **White alone**, percent, July 1, 2016, (V2016)
- **Black or African American alone**, percent, July 1, 2016, (V2016)
- **American Indian and Alaska Native alone**, percent, July 1, 2016, (V2016)
- **Asian alone**, percent, July 1, 2016, (V2016)
- **Native Hawaiian and Other Pacific Islander alone**, percent, July 1, 2016, (V2016)
- **Two or More Races**, percent, July 1, 2016, (V2016)
- **Hispanic or Latino**, percent, July 1, 2016, (V2016)
- **White alone, not Hispanic or Latino**, percent, July 1, 2016, (V2016)
- **Veterans**, 2011-2015
- **Foreign born persons**, percent, 2011-2015
- **Housing units**, July 1, 2016, (V2016)
- **Housing units**, April 1, 2010
- **Owner-occupied housing unit rate**, 2011-2015
- **Median value of owner-occupied housing units**, 2011-2015
- **Median selected monthly owner costs -with a mortgage**, 2011-2015
- **Median selected monthly owner costs -without a mortgage**, 2011-2015
- **Median gross rent**, 2011-2015
- **Building permits**, 2016
- **Households**, 2011-2015
- **Persons per household**, 2011-2015
- **Living in same house 1 year ago, percent of persons age 1 year+**, 2011-2015
- **Language other than English spoken at home**, percent of persons age 5 years+, 2011-2015
- **High school graduate or higher**, percent of persons age 25 years+, 2011-2015
- **Bachelor's degree or higher**, percent of persons age 25 years+, 2011-2015
- **With a disability**, under age 65 years, percent, 2011-2015
- **Persons without health insurance**, under age 65 years, percent
- **In civilian labor force, total**, percent of population age 16 years+, 2011-2015
- **In civilian labor force, female**, percent of population age 16 years+, 2011-2015
- **Total accommodation and food services sales**, 2012 ($1,000)
- **Total health care and social assistance receipts and revenue**, 2012 ($1,000)
- **Total manufacturers shipments**, 2012 ($1,000)
- **Total merchant wholesaler sales**, 2012 ($1,000)
- **Total retail sales**, 2012 ($1,000)
- **Total retail sales per capita**, 2012
- **Mean travel time to work (minutes)**, workers age 16+ years, 2011-2015
- **Median household income (in 2015 dollars)**, 2011-2015
- **Per capita income in past 12 months (in 2015 dollars)**, 2011-2015
- **Persons in poverty**, percent
- **Total employer establishments**, 2015
- **Total employment**, 2015
- **Total annual payroll**, 2015 ($1,000)
- **Total employment, percent change**, 2014-2015
- **Total nonemployer establishments**, 2015
- **All firms**, 2012
- **Men-owned firms**, 2012
- **Women-owned firms**, 2012
- **Minority-owned firms**, 2012
- **Nonminority-owned firms**, 2012
- **Veteran-owned firms**, 2012
- **Nonveteran-owned firms**, 2012
- **Population per square mile**, 2010
- **Land area in square miles**, 2010

**FIPS Code**
For the column, "Fact notes", there are letters that correspond to denote certain meanings in each row. They are listed below.

- **(a)** Includes persons reporting only one race.
- **(b)** Hispanics may be of any race, so also are included in applicable race categories
- **(c)** Economic Census - Puerto Rico data are not comparable to U.S. Economic Census data

In each state column where there is no value, certain letters are in place instead of a value. They are listed below.

- **-** == Either no or too few sample observations were available to compute an estimate, or a ratio of medians cannot be calculated because one or both of the median estimates falls in the lowest or upper interval of an open ended distribution.
- **D** == Suppressed to avoid disclosure of confidential information.
- **F** == Fewer than 25 firms.
- **FN** == Footnote on this item in place of data.
- **NA** == Not available.
- **S** == Suppressed; does not meet publication standards.
- **X** == Not applicable.
- **Z** == Value greater than zero but less than half unit of measure shown.
