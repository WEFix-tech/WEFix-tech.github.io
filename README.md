# WEFix - Data Presentation Page

WEFix is an automated framework that assesses compliance with the Better Ads Standards and
helps website developers to detect and fix the violations.
AdHere can pinpoint ads on the fly and identify participating ad networks. 
It can also provide fix suggestions for developers and 
assist developers in improving their fix solutions while preserving more ad revenue.

This repository contains the source code of AdHere, 
the script used for the preliminary study, and the dataset.
The Preliminary Study Toolset is used to get the compliance status from Google Ad Experience Report.

## Dependencies
- Node.js




## How to reproduce the experiment result 

Please first download 
the source code [here](https://github.com/adhere-tech/adhere-tech.github.io/tree/master/SourceCode).
#### AdHere
1. Install Python 3 and all dependencies.
2. Based on the OS and Chrome version, 
   download the corresponding version of Chromedriver [here](https://chromedriver.chromium.org/). 
   Unzip the downloaded file and put `chromedriver.exe` in the same folder as `AdHere.py`.
3. Fill Google Chrome's user profile directory after `USRPROFILE = ` in `AdHere.py`.
4. Run `python AdHere.py domain_url` in the command line to run AdHere on the given URL. 
   Leaving `domain_url` blank will perform a self-inspection on google.com. 
   It will scan the website with the headless (no GUI) Google Chrome. After finishing the scan, 
   AdHere will generate `violations.txt` in the same folder as `AdHere.py`. 
   The text file contains violations (i.e., the id, violation type, and XPath) and their fix suggestions.
    
#### Preliminary Study Toolset
1. Install Python 3 and all [dependencies](adhere-tech.github.io#dependencies).
2. Create at least one project using Google Ad Experience Report API in Google Developer Console. 
   Apply for the API key for each project.
3. Fill API key(s) in `API_KEY_LIST` in `google.py`. 
   Adjust `THREAD_COUNT` based on the comments in `google.py`.
4. Run `python google.py` in the terminal to get Google Ad Experience Report's result on the Alexa Top 1 Million Websites. 
   Try to keep the network connection stable.
5. In the generated files,`[R]Alexa_done [XX_XX].csv` is the raw file to be stored in the database. 
   It records the compliance status of the 1 million websites.


## Dataset

#### Web_e2e_repos_Dec_14_2021.xlsx
In the paper, we collected 100,000 top-star JavaScript repositories from GitHub using GitHub Search API. We filtered out 250 repos containing web e2e testing and stored them in this file. This data is collected on December 14th, 2021. Repositories are listed in descending order of star number. We identify e2e testing by searching e2e keywords in the repo's `package.json` file. The matched e2e keywords of each repo are presented in the ''e2e keyword'' column.

<iframe src="https://docs.google.com/spreadsheets/d/e/2PACX-1vS5ZE44hEsM4pQxB8k8Nm6Iz66EsIzes4ZtYjJfNuWKqW32Ku_c_Lk4JY7K0x9nWXK2dpeZqFWtPOCa/pubhtml?gid=0&amp;single=true&amp;widget=true&amp;headers=false" loading allowfullscreen width="100%" height="300"></iframe>

#### Exp_repos.xlsx
This file contains the information of seven web application repositories used in our experiment. We picked them out from 250 repos because they have high star and easy to deploy. The "SHA" column shows the commit version we used.

<iframe src="https://docs.google.com/spreadsheets/d/e/2PACX-1vS5ZE44hEsM4pQxB8k8Nm6Iz66EsIzes4ZtYjJfNuWKqW32Ku_c_Lk4JY7K0x9nWXK2dpeZqFWtPOCa/pubhtml?gid=759038802&amp;single=true&amp;widget=true&amp;headers=false"  loading allowfullscreen width="100%" height="300"></iframe>
