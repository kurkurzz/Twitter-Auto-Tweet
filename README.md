# Twitter Auto Tweet 
 Automatically tweet daily using Python and Selenium without using Twitter API.

**Take Note** : 
- The steps below is to run the bot in linux environment. If you know how to do the same in Windows environment can make a pull request.
- The driver in ```drivers``` folder is only for linux, for windows, download from https://sites.google.com/a/chromium.org/chromedriver/downloads
 ## Steps to create this bot
 <br>

### 1. Install required packages to python
<br>
Type the command in terminal

>$ sudo pip3 install selenium schedule 
 <br>

 ### 2. Clone this repository
<br>

### 3. Create ```credentials.py``` file
Insert code below
    
    credential = {
        'EMAIL' : 'twitter-email',
        'PASSWORD' : 'twitter-password',
        'PHONE_NUMBER' : 'twitter-phone-number'
    }

 ### 4. Run the script
 <br>

- In the project directory terminal, run command
    >$ sudo python3 main.py

- To enable script running in the background even after closed terminal, in the project directory terminal, run command
    >$ nohup python3 -u main.py &

    - To kill the process, run command
         >$ ps ax | grep main.py

        Then, get the process id, example 2031 and run command
        >$ kill -9 2031
    - To see the log file, run command
        >$ tail -f nohup.out


