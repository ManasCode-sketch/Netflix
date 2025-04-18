# Netflix Content Data Analysis

This repository contains a data analysis project focusing on the Netflix content library, using a dataset listing movies and TV shows available on the platform. The analysis explores various aspects of the content, including distribution by genre, release year, geographical origin, ratings, and trends over time.

## Project Goal

The main objective of this project is to perform an exploratory data analysis (EDA) on the Netflix content dataset to uncover patterns, trends, and characteristics of the available movies and TV shows.

## Dataset

The analysis was performed on the `netflix_titles.csv` dataset, which includes information about titles on Netflix such as:
*   `show_id`: Unique ID for every show/movie
*   `type`: Type of content (Movie or TV Show)
*   `title`: Title of the content
*   `director`: Director of the content
*   `cast`: Cast members
*   `country`: Country where the content was produced
*   `date_added`: Date the content was added on Netflix
*   `release_year`: Actual release year of the content
*   `rating`: TV rating of the content
*   `duration`: Duration (in minutes for movies, seasons for TV shows)
*   `listed_in`: Genres/categories the content belongs to
*   `description`: A brief description

## Libraries Used

The analysis relies on the following Python libraries:
*   `pandas`: For data manipulation and analysis.
*   `numpy`: For numerical operations.
*   `datetime`: For handling date and time information.
*   `plotly.express`: For creating interactive visualizations.
*   `google.colab`: For accessing files stored in Google Drive (if run in Google Colab).

## Analysis Steps

The analysis followed these main steps:

1.  **Data Loading and Initial Exploration:**
    *   The dataset (`netflix_titles.csv`) was loaded into a pandas DataFrame.
    *   Initial exploration included checking the first few rows (`.head()`), column data types and non-null counts (`.info()`), and the extent of missing values (`.isnull().sum()`).

2.  **Data Cleaning:**
    *   Missing values in `date_added` were handled by converting the column to datetime objects. Specific missing dates were manually imputed.
    *   Missing values in `director`, `cast`, and `country` columns were filled with the string 'Unknown'.
    *   Missing values in the `rating` column were manually imputed based on specific show/movie IDs.
    *   Missing values in the `duration` column were manually imputed based on specific show/movie IDs.
    *   A new column `genres` was created by extracting the first genre from the `listed_in` column.
    *   Movies and TV Shows were separated into different DataFrames (`df_1` for Movies, `df_2` for TV Shows) for type-specific analysis.
    *   For movies (`df_1`), a numeric `duration(min)` column was created by extracting the minute value from the `duration` string.

3.  **Descriptive Analysis:**
    *   Descriptive statistics were generated for numerical columns, particularly focusing on the distribution of movie lengths using `.describe()`.

4.  **Visualizations and Trend Analysis:**
    *   **Genre Distribution:** A bar chart was created to show the distribution of content across different genres.
    *   **Release Year Distribution:** A bar chart visualized the number of titles released in each year, showing the trend of content production over time.
    *   **Geographical Distribution:** A choropleth map displayed the distribution of content production across different countries.
    *   **Content Added Over Time:** A line chart showed the trend of content being added to Netflix over the years, based on the `date_added` column.
    *   **Content Ratings Distribution:** A grouped bar chart illustrated the distribution of different content ratings, separated by content type (Movie vs. TV Show).
    *   **Movie Length Analysis:** Histograms and box plots were used to visualize the distribution and trends in movie runtimes.
    *   **Top Ratings (Proxy for Popularity):** A bar chart showed the count of titles for each content rating, used as a proxy measure for user preferences since direct user ratings were not available.
    *   **Genre Popularity Over Time:** A line chart visualized the trends in the number of titles added per genre over the years.
    *   **Country & Genre Distribution:** A grouped bar chart showed the distribution of different genres within major contributing countries.
    *   **Diversity of Genres:** A bar chart highlighted the count of unique genres present in the dataset.
    *   **Content Type Popularity:** A bar chart compared the total number of Movies versus TV Shows.
    *   A combined dashboard visualization summarized key distributions (ratings, release year, genres, type).

## Key Insights and Conclusions

Based on the analysis:

*   **Content Distribution:** Netflix offers a diverse range of content, with a strong focus on international movies and TV shows. The United States remains a significant contributor, but other countries, particularly India, are emerging as major content creators.
*   **Genre Preferences:** Dramas, comedies, and documentaries are the most common genres available on Netflix, reflecting a broad appeal to different viewer preferences. International movies and TV shows offer a wide variety of genres, catering to diverse tastes.
*   **Content Trends Over Time:** The volume of content added to Netflix has steadily increased over the years, with a significant growth spurt observed in recent years (starting around 2015). This demonstrates Netflix's commitment to expanding its content library.
*   **Content Ratings:** While most of the content on Netflix is suitable for mature audiences (TV-MA, TV-14), a substantial portion is also available for younger viewers (PG, PG-13, TV-Y, TV-Y7), providing a balance between mature and family-friendly options.
*   **Movie Length:** The average length of movies on Netflix is around 99 minutes, with a typical range between 75 to 137 minutes. This consistency in movie length suggests a focus on providing viewers with a manageable viewing experience.
*   **User Preferences (Proxy):** Direct user rating data is not available. However, proxy metrics suggest that content with ratings such as "TV-MA" and "TV-14" is more prevalent, possibly indicating a preference for mature and engaging content among Netflix users. Dramas and comedies are among the most popular genres based on title count.
*   **Content Diversity:** Netflix showcases a significant diversity of content, with a wide range of genres and categories available. This reflects a commitment to inclusivity and providing a platform for various voices and perspectives.
*   **Content Type Preference:** Movies are slightly more popular than TV shows on Netflix in terms of the sheer number of titles, indicating a user preference for standalone films, though TV shows remain a significant part of the content library, offering binge-worthy experiences and diverse storytelling formats.

---
