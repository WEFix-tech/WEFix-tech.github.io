# WEFix

WEFix is an automated tool that can automatically fix concurrency flakiness in web e2e testing. It inserts analysis code into the original e2e test files, and after collecting runtime mutation information, it can generate appropriate explicit waits after command statements to solve flakiness.

We make our tool available on [NPM](), where Node.js users could easily download and integrate into their web project. And this tool includes a user-friendly UI panel to help developers fix web e2e flaky tests. The tool source code can be found on [GitHub]() under MIT licence.



## Dataset

#### Web_e2e_repos_Dec_14_2021.xlsx
In the paper, we collected 100,000 top-star JavaScript repositories from GitHub using GitHub Search API. We filtered out 250 repos containing web e2e testing and stored them in this file. This data is collected on December 14th, 2021. Repositories are listed in descending order of star number. We identify e2e testing by searching e2e keywords in the repo's `package.json` file. The matched e2e keywords of each repo are presented in the ''e2e keyword'' column.

<iframe src="https://docs.google.com/spreadsheets/d/e/2PACX-1vS5ZE44hEsM4pQxB8k8Nm6Iz66EsIzes4ZtYjJfNuWKqW32Ku_c_Lk4JY7K0x9nWXK2dpeZqFWtPOCa/pubhtml?gid=0&amp;single=true&amp;widget=true&amp;headers=false" loading allowfullscreen width="100%" height="300"></iframe>

#### Exp_repos.xlsx
This file contains the information of seven web application repositories used in our experiment. We picked them out from 250 repos because they have high star and easy to deploy. The "SHA" column shows the commit version we used.

<iframe src="https://docs.google.com/spreadsheets/d/e/2PACX-1vS5ZE44hEsM4pQxB8k8Nm6Iz66EsIzes4ZtYjJfNuWKqW32Ku_c_Lk4JY7K0x9nWXK2dpeZqFWtPOCa/pubhtml?gid=759038802&amp;single=true&amp;widget=true&amp;headers=false"  loading allowfullscreen width="100%" height="300"></iframe>



## How to reproduce the experiment result 

1. Clone the repository from GitHub. Make sure Node.js is installed.
2. Check the `package.json` file.
