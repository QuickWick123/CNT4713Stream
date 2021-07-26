Welcome to CNT4713 Project<br>

The technologies used in this project are as follows: <br>
Python/Flask, HTML/CSS, Google OAuth, OpenCV, Heroku and Ngrok, Github <br>

I would like to thank Jose Hernandez for his constant assistance which led to the deployment of this project.<br>

How to get this beauty going:<br>

Download and Install Python. Download and install Git for Windows https://gitforwindows.org/ or any other Github application that allows github commnds.<br>

Once you have the source code downloaded, run these commands:<br>

open cmd<br>
cd YOURPROJECTDIRECTORY<br>
py -m venv .\venv<br>
.\venv\Scripts\activate<br>
pip install -r requirements.txt<br>

Note that if you get a red error, run the requirement command again<br>
Note that we will run command “python app.py” later<br>


Next we should create a Google OAuth by going here: https://console.cloud.google.com/apis/dashboard<br>
Go to Credentials > Create credentials > OAuth client ID > Select Web Application<br>
Under URI you should add:<br>
http://127.0.0.1:5000/login/google/authorized<br>
https://MYHEROKUNAME.herokuapp.com/login/google/authorized<br>

Note that “MYHEROKUNAME” will be for later, after creation of your Heroku domain, do not add it yet<br>

Next in your PROJECTDIRECTORY you should create a .env file<br>
Add this in it:<br>
CLIENT_ID=WRITEINHERE<br>
CLIENT_SECRET=WRITEINHERE<br>
RELAX_TOKEN=True<br>

Replace WRITEINHERE with you clientid and your clientsecret as provided by google oauth<br>

Next we should download Ngrok<br>
Go to https://ngrok.com/ and create an account<br>
Download Ngrok: https://ngrok.com/download<br>

Once Ngrok is downloaded, run ngrok.exe<br>
Type in: ngrok authtoken 12345678abcdefghij<br>
Where 12345678abcdefghij is your actual authtoken<br>
Note that if you are on Mac or Unix you need to do ./ngrok authtoken 12345678abcdefghij<br>

Note that we will run this command later “ngrok http 80”<br>
Where 80 is the port you would like to expose, change this to the port you will be using for your camera, in this case it is 8888<br>

It is recommended to purchase a 1 year for $60 and you get 3 custom subdomains, this can be split 3 ways with others.<br>

Next go to http://www.heroku.com/ and create an account<br>
Click on New and select Create New App and give your website a name<br>
Go back to Google OAuth and add the appropriate URI as described previously<br>

Now we have the essentials<br>

Go back to your PROJECTDIRECTORY and type this in:<br>
open cmd<br>
cd YOURPROJECTDIRECTORY<br>
.\venv\Scripts\activate<br>
python app.py<br>

Great our app is running on 127.0.0.1:5000 we can actually type this into our browser<br>

Next<br>
Open another CMD<br>
cd YOURPROJECTDIRECTORY<br>
.\venv\Scripts\activate<br>
python webcamserver.py<br>


Now type in 127.0.0.1:8888/video_feed in your browser to activate the webcam<br>

We verified it’s working, lets close everything<br>

Move over the .gitignore out of your project to your desktop because it will interfere with the heroku upload<br>

Next up we go do this:<br>
Open cmd<br>
cd YOURPROJECTDIRECTORY<br>
.\venv\Scripts\activate<br>
Heroku login<br>
git init<br>
heroku git:remote -a MYHEROKUNAME<br>
git add .<br>
git commit -am “A message here”<br>
git push heroku master<br>

Now all the files should be uploading to Heroku and our website is deployed yei!<br>
Go to your Heroku website https://MYHEROKUNAME.herokuapp.com/<br>
Cool we got a nifty website wow!<br>

What but our webcam isn’t working?<br>

Next run ngrok.exe and run this command: ngrok http 80<br>
Note that in this project we do “ngrok http 8888”<br>
Note that if you paid for Ngrok you can run this command instead: <br>
ngrok http --region=us --hostname=MYNGROKNAME.ngrok.io 8888<br>

OMG I CAN SEE MYSELF!<br>

Now you can move the .gitignore back into your project for github uploading<br>

Congratulations, these are all the steps it takes to run this application<br>







