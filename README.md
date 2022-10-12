# StockSMS
An automation tool which sends SMS stock price changes along with relevant news headlines and their URLs.

StockSMS calculates daily percentage changes in a specific stock of the users choice. If this daily change exceeds the users chosen percentage, the program will trigger the delivery of an SMS message to the users mobile number. This message will include the name of the stock, the percentage change, and relevant news articles (including the articles heading and URL).
StockSMS uses the AlphaVantage stock API to receive up to date stock prices.
StockSMS uses the NewsAPI to scrape relevant news articles.

Technologies used:
AlphaVantage was the stock API of choice due to its good reviews and thorough, elegant documentation.
NewsAPI was chosen due to its simplicity and the ability to search more than 30,000 news outlets from around the world. Additionally, it is free for non-commercial use. Nevertheless there are a number of APIs which are of the same high standard.
Twilio was used as the communication API for SMS as it provides a free trial and a simple entry point for users.
In order to automate this program I used 'Python Anywhere' (by Anaconda) to run the program at a set time every 24 hours. I used this web dashboard as it is easy to get started and is free to automate one task every 24 hours.

User Guide:
To get started, go to https://www.twilio.com and sign up to get a free SID and Authentication Token and insert them into the TWILIO_SID TWILIO_AUTH_TOKEN variables in main.py. Additionally, you can use the Twilio from_ phone number they provide you with and insert it into the TWILIO_PHONE_NUMBER variable. This will be the number you receive your SMS from. Enter your phone number you used to recieve your SID and AUTH TOKEN into the USER_PHONE_NUMBER variable .
At the top of the file you can edit the stock symbol that the program retrieves data for, and the name of the company you want the NewsAPI to scrape for. Finally, the variable NEWS_ARTICLES_RECEIVED can be set to the amount of articles you want to be texted along with your stock update SMS.
That's Everthing!

Testing:
When testing, set the MINIMUM_CHANGE variable to 1 or even 0.1. This is to ensure that if the volatility of the stock you are tracking is low, it will still trigger an SMS delivery. For example if MINIMUM_CHANGE is set to 3, any daily change less than 3% will not trigger the if statement.

Critical Analysis:
Whilst this project is fit for current purpose, the method undertook is undermined by lack of scalability. Many of these issues could be fixed with the use of paid technologies as opposed to the ones used in this project. 
Furthermore, this StockSMS project is very simple as it only checks for daily percentage fluctuations. To improve this, other parameters could be included such as consumer sentiment, or analyst buy/sell signalling. Despite this being a flaw, this leaves room for much improvement. All viewers are welcome to request commits to add some of these features.
