# tds-project1
[Quiz ID: Sydney:100] (https://tools-in-data-science.pages.dev/project1)
Roll No# 22f3003031


# Overview

This project involves gathering user data from the GitHub API for users located in Sydney with over 100 followers. The script then scrapes detailed information about each user's public repositories. The data collected is organized into two CSV files: `users.csv` and `repositories.csv`.

# How I scraped the data?
1. The GitHub API was used to search for users located in Sydney with over 100 followers. This search was paginated to ensure all qualifying users were collected.
2. For each user found, a secondary API call was made to retrieve their detailed information and public repository data.
3. Data on repositories was collected for up to 500 of the most recently pushed repositories per user.

# Few activities I performed after better understanding the project/assignment details - 
1) Assessment 1 - Data access through API's usually have Rate limits established by providers. Does GitHUb has any such restrictions? 
2) So I created a [personal API token](https://github.com/settings/personal-access-tokens/new), given the higher access limit(5000/hr) for authorized users
3) Access whether data is paginated. If not, I'll have to loop through all pages. Github documentation offered detailed insights [here] (https://docs.github.com/en/rest/using-the-rest-api/using-pagination-in-the-rest-api?apiVersion=2022-11-28)

### Interesting and Surprising facts I found after analysing the data?

- The data was scraped using the GitHub API, fetching users in Sydney with over 100 followers, followed by detailed information on each user's public repositories.
- The most surprising fact was how many high-profile users had a very low number of repositories despite a large follower count.
- Developers should focus on building more repositories that showcase their skills, as follower count alone doesn't necessarily reflect active project involvement.
- Through analyzing the data, it was observed that some users with a large follower base had surprisingly few repositories, which may indicate that GitHub followers don’t always correlate to repository activity.

## Data collection insights
1. Over 371 users were scraped, and 32416 associated repositories, based on the provided search criteria ("scrape all GitHub users in the city of Sydney with over 100 followers, and their repositories", "for these users, fetch up to the 500 most recently pushed repositories")
2. I fetched the response in JSON format, which was well structured. GitHub also provided detailed [API guide](https://docs.github.com/en/rest/about-the-rest-api/about-the-rest-api?apiVersion=2022-11-28) on this
3. Missed the ‘pagination’ aspect earlier and later incorporated it, for data completeness
5. Used a free LLM chatbot to improve my code/understanding

## An actionable recommendation for developers based on your analysis

Additional analysis can be performed to explore patterns between user activity and repository languages, license types, or stargazer counts. Further filtering could also focus on more specific user categories, such as company affiliations or top open-source contributors.


### Files Generated:
- **users.csv**: Contains key information about each user such as their GitHub login, name, company, location (city), email, and number of repositories, followers, and followings.
- **repositories.csv**: Contains the public repositories for each user, including details like repository name, creation date, programming language, and license.

