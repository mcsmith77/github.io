# github.io
Data Analytics Portfolio
Divvy_Exercise_Full_Year_Analysis for Google Data Analytics Certification

Overview
Cyclistic is a bike-share program that features more than 5,800 bicycles and 600 docking stations. Cyclistic sets itself apart by also offering reclining bikes, hand tricycles, and cargo bikes, making bike-share more inclusive to people with disabilities and riders who can’t use a standard two-wheeled bike. The majority of riders opt for traditional bikes; about 8% of riders use the assistive options. Cyclistic users are more likely to ride for leisure, but about 30% use them to commute to work each day.
The director of Marketing has set a clear goal. Design marketing strategies aimed at converting casual riders into annual members. In order to do that, however, the marketing analyst team needs to better understand how annual members and casual riders differ, why casual riders would buy a membership, and how digital media could affect their marketing tactics. The Marketing team is interested in analyzing the Cyclistic historical bike trip data to identify trends.

The Business Questions that my analysis must answer are:

How do annual members and casual riders use Cyclistic bikes differently?
Why would casual riders buy Cyclistic annual memberships?
How can Cyclistic use digital media to influence casual riders to become members?

Citations:
Data is from Motivate International Inc, under this license: https://ride.divvybikes.com/data-license-agreement
R code is modified from a Divvy case study "'Sophisticated, Clear, and Polished’: Divvy and Data Visualization" written by Kevin Hartman (found here: https://artscience.blog/home/divvy-dataviz-case-study)

STEP 1: COLLECT DATA
Upload a year's worth of Divvy monthly trip datasets (csv files)

STEP 2: WRANGLE DATA AND COMBINE INTO A SINGLE FILE
Compare column names each of the files While the names don't have to be in the same order, they DO need to match perfectly before we can use a command to join them into one file

Convert ride_id and rideable_type to character so that they can stack correctly

STEP 3: CLEAN UP AND ADD DATA TO PREPARE FOR ANALYSIS
Inspect the new table that has been created.

Problems that may need fixing
In the "member_casual" column, there are two names for members ("member" and "Subscriber") and two names for casual riders ("Customer" and "casual"). We will need to consolidate that from four to two labels.
The data can only be aggregated at the ride-level, which is too granular. We will want to add some additional columns of data -- such as day, month, year -- that provide additional opportunities to aggregate the data.
We will want to add a calculated field for length of ride since the data did not have the "tripduration" column. We will add "ride_length" to the entire dataframe for consistency.
There are some rides where tripduration shows up as negative, including several hundred rides where Divvy took bikes out of circulation for Quality Control reasons. We will want to delete these rides. (Note: not seeing these rides in the data).
In the "member_casual" column, replace "Subscriber" with "member" and "Customer" with "casual" Before 2020, Divvy used different labels for these two types of riders ... we will want to make our dataframe consistent with their current nomenclature. Begin by seeing how many observations fall under each usertype

Add columns that list the date, month, day, and year of each ride This will allow us to aggregate ride data for each month, day, or year ... before completing these operations we could only aggregate at the ride level.
Add a "ride_length" calculation to all_trips (in seconds). Inspect the structure of the data, and convert ride_length to numeric so summary statistics can be provided on it.

Remove "bad" data
Remove any records where ride_length is negative. We will create a new version of the dataframe (v2) since data is being removed.

STEP 4: CONDUCT DESCRIPTIVE ANALYSIS
Descriptive analysis on ride_length (all figures in seconds). You can condense separate calls to the mean, median, min and max functions to one line using summary() on the specific attribute.
Compare members and casual users by ride_length.
Put the days of the week in order, and find the average ride time by each day for members vs casual users.
Analyze ridership by member type and week day.

Data Visualizations
Create data visualizations of ridership versus ride length, and ridership versus day of the week.

STEP 5: Answers to the business questions:
How do annual members and casual riders use Cyclistic bikes differently? It appears that casual riders ride for longer, especially on weekends.Member riders take shorter trips, and ride more in the middle of the week. It is likely that the member users are riding to work and the casual users are riding for pleasure.
Why would casual riders buy Cyclistic annual memberships? Casual riders would buy memberships if they could be convinced to ride to work as well as for pleasure.
How can Cyclistic use digital media to influence casual riders to become members? Cyclistic can mount a digital ad campaign targeting the casual user, and showing the benefits of riding to work (no traffic or mass transit hassles, greener option, healthier, etc.)
