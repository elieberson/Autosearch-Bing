# Autosearch-Bing
Automatically log in and search Bing with random strings taken from NYTimes (Regular and Mobile modes). Also clicks on the links on the Bings rewards page for extra points (experimental).

## Purpose
Bing Rewards will reward a user 1 point for every 2 searches done through bing. A maximum of 15 regular points can be rewarded per day. However, there is a separate maximum of 10 points for mobile searches. This program will automatically find strings from the summaries on the front page of nytimes.com and search them on bing, both reglarly and via mobile by changing the chrome browser to mobile mode.

## Requirements
- chrome.exe
- chromedriver.exe
- selenium (Python Library)
- lxml (Python Library)

## Run
1. Have an empty file called "LastTime.txt"
2. Have a "logins.txt" file with every username and password you want to use in the format: `<username> : <password>`. One login per line
3. In terminal/cmd:
  - `BingRewards.py`
    - By default, 31 regular searches and 21 movile searches
  - `BingRewards.py <#RegularSearches>,<#MobileSeaches>,<#ClickPints>`
    - <#RegularSearches> Number of regular to perform
    - <#MobileSearches> Number of mobile to perform
    - <#ClickPoints> Whether or not click links n rewards page. 0=False,1=True
    - This will ignore the "LastTime.txt"

## What it does
1. Checks the "LastTime.txt" to see when the last time the program was ran if number of searches not specified
2. If it has not been run on this day, go to the nytimes site and pull strings of word length 2 to 5 from the the summaries on the frontpage. Get enough strings to fulfill all the required searches
3. Open the chrome browser and login using the credentials in the "logins.txt"
4. Go to bing.com and run all the searches in regular browser mode
5. Clicks on the simple extra rewards on the bings rewards page
6. Go to bing.com and run all the searches in mobile browser mode