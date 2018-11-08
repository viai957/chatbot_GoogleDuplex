Her's a chat bot built using nodejs,ngrock, dilogflow , pythonanyware,nodejs,mongodb

To try chatbot : visit https://vignesh27.weebly.com or call +1 240-233-8532 to experince google duplex


USEFULL LINKS
Facebook chatbot platform: https://developers.facebook.com/blog/post/2016/04/12/bots-for-messenger/

Node.js: https://nodejs.org/en/

ngrok: https://ngrok.com/

Node.js on a Raspberry Pi: https://learn.adafruit.com/node-embedded-development/installing-node-dot-js

Install mongodb on a raspberry pi: http://andyfelong.com/2016/01/mongodb-3-0-9-binaries-for-raspberry-pi-2-jessie/

Mongodb: https://www.mongodb.com/

Install mongdb: https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/

Getting started with mongoose: https://scotch.io/tutorials/using-mongoosejs-in-node-js-and-mongodb-applications

lets start with creating digiflow account and then enter the intents 
to get more detailed info on intents and actions reffer to the documents page and understand the full intent of using every essential tools and the create an agent 
By using create aget in the path file you can confront with the steps 

Click “Save” then test it by using “Try it now…” in the upper right.

We now have a simple chat-bot.

To call it from our code we’ll need its “Client access token”. To see this information, click on the gear to the right of ‘MyAgent’ in the upper-left.



The next step is to run a WebApp (our ‘webHook) using Python and Flask on pythonanywhere. This will be the back-end to our chat-bot.

Add a new WebApp.


Provide a prefix for your WebApp: some-name.pythonanywhere.com

Select ‘Flask’ for a framework, on Python 3.5


You should see a default flask_app.py in your WebApp files directory. Click to edit it.

Here’s our 60 lines of code to handle the flow between FB messenger and api.ai:


use your FB and api.ai credentials
You will need to pip install packages (eg. apiai) in your pythonanywhere Bash console, as follows:


installing apiai in Bash console
Also remember to restart your pythonanywhere web app anytime you alter the code. Click on the circular button in the upper-right, as shown below:


pythonanywhere shortcuts
If everything is in place you should be able to ping your new Flask app:


be sure to use your URL prefix instead of ‘gk.’

Now we can setup a FB page and messenger setup.

This will take 5 quick steps.

Step 1: create a new FB page
(click on the link above to create a new page) Give it a name, like ‘BuildBot10mins’, or something less idiotic.


Step 2: create a FB App
Click “Skip and Create App ID” at the top right. Then create a new Facebook App for your bot and give your app a name, category and contact email.

Step 3: create a new access token
Create a new token (for the FB page created in step 1):


Copy this new Access Token and Paste it in your pythonanywhere code (line 4: under # FB messenger credentials)

Step 4: create our WebHook, click “Setup Webhooks”

Provide your Callback URL (be sure to use https://)

Use the same verify token specified in your pythonanywhere code.


be sure to specify https:// for the Callback URL
Step 5: subscribe to our WebHook
Select your newly created FB page and click ‘Subscribe’, this connects our FB Page with the FB Messenger App we just setup.


don’t forget this last step
What did we just do? Let’s review our steps:

1 (handling responses)
In the first step we created a really simple chat-bot on api.ai, it has some basic conversational abilities, and knows the meaning of life. You can use whatever chat-bot framework you like.

2 (the back-end)
In the second step we built a Python Flask app on pythonanywhere, this allows us to host a WebApp without building a server. You can use other serverless platforms such as Amazon Lambda.

3 (the front-end)
Our third step was setting up FB Messenger and connecting a WebHook between it and our WebApp. You can also build the same bot using SMS.

The WebApp is the broker between incoming messages, the chat-bot interface and outgoing responses.