# Netflix Data Analysis Using PowerBI

We analyze Netflix movie data using Power BI to generate insights. Below is a screenshot of the final interactive dashboard created with PowerBI.

![Final Dashboard Screenshot]()


## Description of the Dataset

## Business Questions we seek to answer

## Data Preprocessing

We have preprocessed our original data using various means, such as deleting irrelevant columns, creating new groups, and deleting certain rows with missing values.

More specifically, we have done the following:

### Transform Data

### Create Calculations and Formatting Table

We create a series of new measures and store them under the `Calculations` table, and create another table called `Rating Group Formatting` that stores different hexadecimal color values and hexadecimal font colors for different rating groups that we created earlier.

The `Calculation` table serves the purpose of providing convenient values for variou axis or filters required in various visual components of our dashboard. For example, the `Average Rating` measure was used in the table about Countries, appearing in the lower left portion of the dashboard. The `Calculation` table has the following groups of measures and is organized in the following hieriarchies:

├── 0. Total
│   ├── # Titles
|   ├── # Votes
│   ├── # Votes Per Title
│   ├── Average Rating
│   ├── Dynamic Rating Fill
│   └── Dynamic Rating Font
├── 1. Movie
│   ├── # Movie Titles
|   ├── # Movie Votes
│   ├── % Movie Votes Label
│   └── Movie Average Rating
├── 2. TV
│   ├── # TV Titles
|   ├── # TV Votes
│   ├── % TV Votes Label
│   └── TV Average Rating

Most measures' names are self-explanatory; for example, `# Votes` refers to the total number of votes, `% Movie Votes Label` indicates 



## Dashboard Functionalities

Below, we explain some of the key interactive functionalities of our dashboard. The full dashboard can be explored by downloading the [PowerBI dashboard file]().

### Modified Funnel Chart for showing distribution of Ratings

![funnel chart for rating gourp]()

### Information about Titles By Country

![Country chart]()

In the lower left portion of the dashboard, I have included a table that shows, for each country, the number of titles, average rating, number of votes, and number of votes per title. One can click on a specific country to drill all data in the dashboard down to a specific country.

## KPIs and Movie-TV filter

On the top middle portion of the dashboard, I have included a filter that one can use to drill data down to only Movie, only TV Series, or both. 


### Mobile Dashboard

I have also created a mobile dashboard using similar visuals and same dataset. All the functionalities are the same, while the dashboard's layout is a little different due to screen difference. The full mobile dashboard can be found in the main Power BI file. Below, we include a few screenshots of the movbile dashboard.

| Page 1  | Page 2  | Page 3  | Page 4  | Page 5  |
| ------- | ------- | ------- | ------- | ------- |
| ![Page 1]() | ![Page 2]() | ![Page 3]() | ![Page 4]() | ![Page 5]() |




## Additional Insights
