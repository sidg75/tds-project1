# tds-project1
[Quiz ID: Sydney:100](https://tools-in-data-science.pages.dev/project1)
Roll No# 22f3003031


## Overview

This project involves gathering user data from the GitHub API for users located in Sydney with over 100 followers. The script then scrapes detailed information about each user's public repositories. The data collected is organized into two CSV files: `users.csv` and `repositories.csv`.



## How I scraped the data?
1. Created a Collab notebook(python) to scrape GitHub data via APIs. GitHub has detailed [API guide](https://docs.github.com/en/rest/about-the-rest-api/about-the-rest-api?apiVersion=2022-11-28) on this which helped understand the structure and parameters
2. JSON data format was used for response
3. First, the [Search API](https://docs.github.com/en/rest/search/search?apiVersion=2022-11-28) was used to search for users located in Sydney with over 100 followers(_location:Sydney followers:>100_). As the API response was paginated, we introduced necessary code changes (_per_page=100 and page parameter_) to ensure all qualifying users were fetched. To validate my results and the API fetch count, I reconfirmed it via searching directly on the [website](https://github.com/search?q=location%3ASydney%20followers%3A%3E100&type=users)
4. Seondly, for each user found, we iterated and invoked a secondary API to retrieve their detailed information and public repository data
5. Given the assignment instructions, data on repositories was collected for up to 500 of the most recently pushed repositories per user. This was acheived by looping through repo List object and ensuring we are below 500
6. On completion, over 371 users were scraped, and 32416 associated repositories

## Few activities I performed after better understanding the project/assignment details - 
1) Assessment 1 - Data access through API's usually have Rate limits established by providers. Does GitHUb has any such restrictions? 
2) So I created a [personal API token](https://github.com/settings/personal-access-tokens/new), given the higher access limit(5000/hr) for authorized users
3) Access whether data is paginated. If not, I'll have to loop through all pages. Github documentation offered detailed insights [here] (https://docs.github.com/en/rest/using-the-rest-api/using-pagination-in-the-rest-api?apiVersion=2022-11-28)

## Interesting and Surprising facts I found after analysing the data?

- The data was scraped using the GitHub API, fetching users in Sydney with over 100 followers, followed by detailed information on each user's public repositories.
- The most surprising fact was how many high-profile users had a very low number of repositories despite a large follower count.
- Developers should focus on building more repositories that showcase their skills, as follower count alone doesn't necessarily reflect active project involvement.
- Through analyzing the data, it was observed that some users with a large follower base had surprisingly few repositories, which may indicate that GitHub followers don’t always correlate to repository activity.

## An actionable recommendation for developers based on your analysis

Additional analysis can be performed to explore patterns between user activity and repository languages, license types, or stargazer counts. Further filtering could also focus on more specific user categories, such as company affiliations or top open-source contributors.

### Data collection insights


3. Missed the ‘pagination’ aspect earlier and later incorporated it, for data completeness
5. Used a free LLM chatbot to improve my code/understanding

### Files Generated:
- **users.csv**: Contains key information about each user such as their GitHub login, name, company, location (city), email, and number of repositories, followers, and followings.
- **repositories.csv**: Contains the public repositories for each user, including details like repository name, creation date, programming language, and license.
