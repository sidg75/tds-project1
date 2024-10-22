# tds-project1
TDS Project 1 - Quiz ID: Sydney:100
Roll No# 22f3003031

https://tools-in-data-science.pages.dev/project1


Each of these 3 bullets must be one sentence no more than 50 words.

- How the data was scraped - An explanation of how you scraped the data
- The most interesting and surprising fact you found after analyzing the the data
- An actionable recommendation for developers based on your analysis


# GitHub Users and Repositories Data Analysis

### Key Insights

- The data was scraped using the GitHub API, fetching users in Sydney with over 100 followers, followed by detailed information on each user's public repositories.
- The most surprising fact was how many high-profile users had a very low number of repositories despite a large follower count.
- Developers should focus on building more repositories that showcase their skills, as follower count alone doesn't necessarily reflect active project involvement.

## Overview

This project involves gathering user data from the GitHub API for users located in Sydney with over 100 followers. The script then scrapes detailed information about each user's public repositories. The data collected is organized into two CSV files: `users.csv` and `repositories.csv`.

### Files Generated:
- **users.csv**: Contains key information about each user such as their GitHub login, name, company, location (city), email, and number of repositories, followers, and followings.
- **repositories.csv**: Contains the public repositories for each user, including details like repository name, creation date, programming language, and license.

## How Data Was Scraped

1. The GitHub API was used to search for users located in Sydney with over 100 followers. This search was paginated to ensure all qualifying users were collected.
2. For each user found, a secondary API call was made to retrieve their detailed information and public repository data.
3. Data on repositories was collected for up to 500 of the most recently pushed repositories per user.

## Interesting Findings

Through analyzing the data, it was observed that some users with a large follower base had surprisingly few repositories, which may indicate that GitHub followers don’t always correlate to repository activity.

## Recommendations

For developers seeking to build influence or visibility on GitHub, focusing on maintaining an active repository portfolio may be more beneficial than just accumulating followers. Ensuring consistent project updates and diverse language usage in repositories can showcase developer versatility.

## Instructions for Running the Script

To run the script:
1. Clone the repository and navigate to the folder containing the script.
2. Add your personal GitHub API token for authentication.
3. Run the script using Python 3 to fetch the data, which will automatically generate `users.csv` and `repositories.csv`.
4. Analyze the data using any tool of your choice (e.g., Excel, Pandas).

## Future Work

Additional analysis can be performed to explore patterns between user activity and repository languages, license types, or stargazer counts. Further filtering could also focus on more specific user categories, such as company affiliations or top open-source contributors.
