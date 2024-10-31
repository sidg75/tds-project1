# TDS-Project[1]:  GitHub User and Repository Analysis
- Objective: To scrape and analyse GitHub's users in Sydney and their repositories data
- [Quiz ID: Sydney:100](https://tools-in-data-science.pages.dev/project1)

## 1. How did I scrape the data?
Colab(python) script was created to perform 3 major steps - 
- fetch the data - via invocation of multiple GitHub APIs, like 'GET /search/users' 'GET /users/{userId}/repos'
- process the data - like stripping whitespaces, removing leading '@' symbols etc, and
- store the data - into two separate CSV files for further analysis

## 2. Interesting and Surprising facts I found after analysing the data
- **COVID-19 impact?**: In the last 16 years of GitHub's history, year 2021 was a breakout year (refer graph below). It saw huge spike in creation of new repos and followers. It may be due to COVID-19 pandemic leading more developers to be working remotely and engaging in personal or open-source projects. Also, it coincides with the increased adoption of [GitHub Copilot(AI) that year](https://trends.google.com/trends/explore?date=today%205-y&q=github%20copilot&hl=en)
- **JavaScript dominance?**: With 167,565 stars, JavaScript rules Sydney's GitHub languages. This points to strong web-development uptake, especially since users from web company Atlassian and Canva are top contributors
- **Quality over quantity?**: Many top users have a very low number of repositories despite a large follower count
- **Weak correlation**: between the number of followers and stargazers on repositories (0.067), indicating that having more followers doesn't strongly predict the popularity of a user's repositories

## 3. An actionable recommendation for developers based on analysis
- developers should focus on improving quality of their repos (and not quantity). This can be acheived via better code, clear guidelines on usage and collaboration, regular updates etc. This may lead to improved uptake on followers and community visibility
- since there's a weak negative regression slope of -9.72 between developer's bio and number of followers, it is suggested to keep bios shorter 
- developers must consider adopting MIT licenses for their repos. This has greatest adoption in Sydney region (may be since it's a very permissive license that allows users to do almost anything they want with your code, including using it in commercial products)
![alt text](https://github.com/sidg75/tds-project1/blob/main/users_trend_by_years.png)

## Extra optional read (for reference only)
### Details and related steps
1. Created a Collab notebook(python) to scrape GitHub data via APIs. GitHub has detailed [API guide](https://docs.github.com/en/rest/about-the-rest-api/about-the-rest-api?apiVersion=2022-11-28) on this which helped understand the structure and parameters involved. Since GitHub has restrictive Rate limits, I created a [personal API token](https://github.com/settings/personal-access-tokens/new), to help with higher requests limit(5000/hr), for the authorised users
2. First, the [Search API](https://docs.github.com/en/rest/search/search?apiVersion=2022-11-28) was used to search for users located in Sydney with over 100 followers(_location:Sydney followers:>100_). As the API response was [paginated](https://docs.github.com/en/rest/using-the-rest-api/using-pagination-in-the-rest-api?apiVersion=2022-11-28), I introduced necessary code changes (_per_page=100 and page parameter_) to ensure all qualifying users were fetched. To validate my results and the API fetch count, I reconfirmed it via searching directly on the [website](https://github.com/search?q=location%3ASydney%20followers%3A%3E100&type=users). This data was written to _users.csv_ file
3. Secondly, for each user found, we iterated and invoked a secondary API to retrieve their detailed information and public repository data
4. Given the assignment instructions, data on repositories was collected for up to 500 of the most recently pushed repositories per user. This was achieved by looping through the repo List object and ensuring we are below 500. This data was written to _repositories.csv_ file
5. On completion, over 371 users were scraped, and 32415 associated repositories
6. I later uploaded these CSV files to Google Sheets for data analysis

### Files Generated:
- **users.csv**: Contains key information about each user such as their GitHub login, name, company, location (city), email, and number of repositories, followers, and followings
- **repositories.csv**: Contains the public repositories for each user, including details like repository name, creation date, programming language, and license

