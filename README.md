# Twitter Auto Tweet (Scheduler not working)
 Automatically tweet daily using Python Selenium and Heroku.

 **Disclaimer**: This documentation will not guide you on how to code. You need to do it yourself or just copy paste or clone from main.py or whatevs whatevs.

 **Take note**: For some reason which I dont know yet, the bot will run at random time.
If you know how to fix this, please let me know.

## Steps to create this bot
<br>

### 1. Install Selenium to Python

Type the command in terminal

>$ pip install selenium

<br>

### 1. Setup Heroku
 1. Create Heroku account/log in existing account.
 1. Create new application.
 1. Go to ```Settings``` tab and do the following:
     
      
      1. Add buildpacks
            ![buildpacks](https://user-images.githubusercontent.com/64152220/90945771-a33b0d80-e459-11ea-951b-b7a1cd6f1eec.png)
          - Python
          - https://github.com/heroku/heroku-buildpack-google-chrome 
          -  https://github.com/heroku/heroku-buildpack-chromedriver

       1. Setup config vars  
            ![configvars](https://user-images.githubusercontent.com/64152220/90945783-b057fc80-e459-11ea-8961-3df239b7e3a8.jpg)
        
            KEY | VALUE
            ------------ | -------------
            CHROMEDRIVER_PATH | /app/.chromedriver/bin/chromedriver
            GOOGLE_CHROME_BIN| /app/.apt/usr/bin/google-chrome
            EMAIL | \<YOUR-TWITTER-EMAIL>
            PASSWORD | \<YOUR-TWITTER-PASSWORD>
            PHONE_NUMBER | \<YOUR-TWITTER-PHONE-NUMBER>
            TWEET_STRING | \<WHAT-YOU-WANT-THE-BOT-TO-TWEET>

<br/>

### 2. Create procfile and requirements.txt
1. Create new file named Procfile (or just copy from the source code) and type in: <br>
    >web: python main.py
1. In the project directory terminal, run the following command:
    >$ pip freeze > requirements.txt    

<br/>

### 3. Deploy the script to Heroku

1. Install [Git](https://git-scm.com/downloads) and [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli)
1. In Heroku dashboard, go to ```Deploy``` tab.
1. Go to deployment method and click on Heroku Git.

    ![deploy](https://user-images.githubusercontent.com/64152220/90945793-bea61880-e459-11ea-926a-2a5985643d3d.png)
1. Follow the guides displayed there. <br>
**Note** : The guide attached on the image might be different with what displayed to you on the website. It's because you will need to initialize git first.
        
<br/>

### 4. Run the script
In the project directory terminal, run command:
> $ heroku run python main.py

<br/>

### 5. Set schedule to automate the tweet
1. Enable billing on your Heroku account (Don't worry, it's still free).
1. In the project directory terminal, run command:
    > $ heroku addons:create scheduler:standard
1. In the Heroku dasboard, go to ```Resources``` tab
1. Navigate the ```Heroku Scheduler``` and click ```Add Job```.
1. Insert as following

    ![scheduler](https://user-images.githubusercontent.com/64152220/90945804-cd8ccb00-e459-11ea-8b84-334e271da4b2.png)

    - In the ```Run Command```, Insert
        > heroku run python main.py

    - You can set the time interval as you like.



<br/><br/>
#### Credit to https://www.youtube.com/watch?v=rfdNIOYGYVI by Ready Dev
