# Netflix Data Analysis Using PowerBI

We analyze Netflix movie data using Power BI to generate insights. Below is a screenshot of the final interactive dashboard created with PowerBI.

![Final Dashboard Screenshot](https://github.com/srheegit/Netflix-Data-Analysis-with-Power-BI/blob/main/Screenshots/Desktop%20Dashboard/Main%20Dashboard.png)

## Description of the Dataset

We have used the [Netflix Movie and TV Shows dataset from Kaggle](https://www.kaggle.com/datasets/snehaanbhawal/netflix-tv-shows-and-movie-list). The "dataset contains the list and metadata of all TV Shows and Movies available on Netflix currently about 7000 taken from the IMDB website." The name of the original table is `Listings`.

Below, we can see the first few rows of our dataset.

![first few rows of our data](https://github.com/srheegit/Netflix-Data-Analysis-with-Power-BI/blob/main/Screenshots/df.head().png)

## Business Questions we seek to answer

## Data Preprocessing

We have preprocessed our original data using various means, such as deleting irrelevant columns, creating new groups, and deleting certain rows with missing values.

All Data Preprocessing for this project is done within Power BI's Dataset Builder.

More specifically, we have done the following:

### Transform Data

#### Removing Unnecessary Columns

We remove the following columns from our original data: `popular_rank`, `certificate`, `endYear`, `episodes`, `language`, `summary`, `isAdult`, `cast`. We may have found the `isAdult` column, which indicates whether a film is supposedly an adult film or not, but checking the column values indicated that the column has only one value `0`, making the data useless for our purpose.

#### Renaming Columns and Change Their DataTypes

We now rename the columns for consistency and/or ease of use, as follows:

1. `imdb_id` --> `ID`
2. `title` --> `Title`
3. `startYear` --> `Start Year`
4. `runtime` --> `Runtime`
5. `type` --> `Type`
6. `origin_country` --> `Country`
7. `plot` --> `Plot`
8. `rating` --> `Rating`
9. `numVotes` --> `Votes`
10. `genres` --> `Genres`
11. `image_url` --> `Image URL`

After that, we change the datatype to appropriate datatypes; for example, the `ID` and `Title` columns are set to have a `text` datatype, `Start Year` column is set to have `text` datatype (since we don't want to apply numeric calculations to them and later want to group the years), `Runtime` is set to `Whole Number`, `Country` to `text`, `Rating` to `Decimal Number`, `Votes` to `Whole Number`, `Genres` and `Image URL` to `text`.

#### Excluding Rows with Missing Important Data

We then exclude rows that are missing values in certain columns - for example, we exclude all rows with null value or error in the `Runtime` column, and we replace all rows without a `Rating` or a `Country` value. This is because the rows that don't tell a story will not be as useful to us as rows that have all important data.

#### Creating New Columns

We also want to modify and/or create certain columns. Throughout this process, we use several DAX functions such as `SEARCH` and `SWITCH`.

We now create a new `Rating Group` column which will round down the decimal `Rating` values into a whole number, effectively binning the ratings into ten bins, from `1` through `9`. We also could have created a `Continent` group column, although this would've taken far more manual entry of various countries.

We then create a `Genre` column out of `Genres`, taking only the first genre that appears in each entry of the `Genres` value. This will help us in categorization and make our data analysis simpler.

After creating new columns, we separate the various columns we have into one of various folders, such as `z_hidden` (for less relevant columns), `Attributes`, `Measure`, and `Modeling`.

### Creating Calculations and Formatting Table

We create a series of new measures and store them under the `Calculations` table, and create another table called `Rating Group Formatting` that stores different hexadecimal color values and hexadecimal font colors for different rating groups that we created earlier.

Throughout the process, we use various DAX functions such as `AVERAGE`, `SUM`, and `FILTER`.

The `Calculation` table serves the purpose of providing convenient values for variou axis or filters required in various visual components of our dashboard. For example, the `Average Rating` measure was used in the table about Countries, appearing in the lower left portion of the dashboard. The `Calculation` table has the following groups of measures and is organized in the following hieriarchies:

```
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
```


Most measures' names are self-explanatory; for example, `# Votes` refers to the total number of votes, `% Movie Votes Label` indicates 

### Data Modeling

As we have three tables, we now organize our data model. We bidirectionally link the original `Listings` table and `Rating Group Formatting` table, via the `Rating Group` columns, in many-to-one.

## Styling

We have included in our dashboard various big-and-small details in how it looks. While it would be too long and not very informative to explain everything we have implemented, we followed a general rule: have a gradient background from black to white (mostly black), with gradient background from the Netflix red color to a white color with red tint. The trio of the three colors, red, black, and netflix red, is the theme of the whole dashboard.

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
