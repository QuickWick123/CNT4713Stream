Welcome to CNT4713 Project

The technologies used in this project are as follows: 
Python/Flask, HTML/CSS, Google OAuth, OpenCV, Heroku and Ngrok, Github 

I would like to thank Jose Hernandez for his constant assistance which led to the deployment of this project.

How to get this beauty going:

Download and Install Python. Download and install Git for Windows https://gitforwindows.org/ or any other Github application that allows github commnds.

Once you have the source code downloaded, run these commands:

open cmd
cd YOURPROJECTDIRECTORY
py -m venv .\venv
.\venv\Scripts\activate
pip install -r requirements.txt

Note that if you get a red error, run the requirement command again
Note that we will run command “python app.py” later


Next we should create a Google OAuth by going here: https://console.cloud.google.com/apis/dashboard
Go to Credentials > Create credentials > OAuth client ID > Select Web Application
Under URI you should add:
http://127.0.0.1:5000/login/google/authorized
https://MYHEROKUNAME.herokuapp.com/login/google/authorized

Note that “MYHEROKUNAME” will be for later, after creation of your Heroku domain, do not add it yet

Next in your PROJECTDIRECTORY you should create a .env file
Add this in it:
CLIENT_ID=WRITEINHERE
CLIENT_SECRET=WRITEINHERE
RELAX_TOKEN=True

Replace WRITEINHERE with you clientid and your clientsecret as provided by google oauth

Next we should download Ngrok
Go to https://ngrok.com/ and create an account
Download Ngrok: https://ngrok.com/download

Once Ngrok is downloaded, run ngrok.exe
Type in: ngrok authtoken 12345678abcdefghij
Where 12345678abcdefghij is your actual authtoken
Note that if you are on Mac or Unix you need to do ./ngrok authtoken 12345678abcdefghij

Note that we will run this command later “ngrok http 80”
Where 80 is the port you would like to expose, change this to the port you will be using for your camera, in this case it is 8888

It is recommended to purchase a 1 year for $60 and you get 3 custom subdomains, this can be split 3 ways with others.

Next go to http://www.heroku.com/ and create an account
Click on New and select Create New App and give your website a name
Go back to Google OAuth and add the appropriate URI as described previously

Now we have the essentials

Go back to your PROJECTDIRECTORY and type this in:
open cmd
cd YOURPROJECTDIRECTORY
.\venv\Scripts\activate
python app.py

Great our app is running on 127.0.0.1:5000 we can actually type this into our browser

Next
Open another CMD
cd YOURPROJECTDIRECTORY
.\venv\Scripts\activate
python webcamserver.py


Now type in 127.0.0.1:8888/video_feed in your browser to activate the webcam

We verified it’s working, lets close everything

Move over the .gitignore out of your project to your desktop because it will interfere with the heroku upload

Next up we go do this:
Open cmd
cd YOURPROJECTDIRECTORY
.\venv\Scripts\activate
Heroku login
git init
heroku git:remote -a MYHEROKUNAME
git add .
git commit -am “A message here”
git push heroku master

Now all the files should be uploading to Heroku and our website is deployed yei!
Go to your Heroku website https://MYHEROKUNAME.herokuapp.com/
Cool we got a nifty website wow!

What but our webcam isn’t working?

Next run ngrok.exe and run this command: ngrok http 80
Note that in this project we do “ngrok http 8888”
Note that if you paid for Ngrok you can run this command instead: 
ngrok http --region=us --hostname=MYNGROKNAME.ngrok.io 8888

OMG I CAN SEE MYSELF!

Now you can move the .gitignore back into your project for github uploading

Congratulations, these are all the steps it takes to run this application







