# SenseNetatmo [![license](https://img.shields.io/badge/license-GPLv3-brightgreen.svg)](LICENSE)
Implementation of wrapper code to enable reading of measurements from the Netatmo Weatherstation using Amazon Echo (Alexa).

# Keywords 
Amazon, Alexa, Echo, Netatmo, Rest, AWS, Lambda, Alexa Skill Kit, ASK

# Description
 SenseNetatmo is the implementation of an Amazon AWS Lambda function which enables reading of Netatmo weather station data directly using Amazon Echo (Alexa).

 Steps : 
  
 1. Get a free account for Amazon AWS. As long as your skill is not constantly running (you will be billed by the run time and resources used on the AWS Servers with something like 700? free hours each month), you should be good and it will stay free. The skill requires 1-3 seconds to run at a time.

 2. Set up a new lambda function in Amazon Web Services (AWS). This function will execute every time the skill is invoked. Paste the code found in main.js inside the lambda function.
 
 3. Go to netatmo's developer site (https://dev.netatmo.com/) and create a new application. This will be your interface to the sensor data on the Netatmo side. The apllication will have a unique id (i.e: 5653769769f7411515036a0b) and client secret (i.e: T4nHevTcRbs053TZsoLZiH1AFKLZGb83Fmw9q). (No, these numbers do not represent a valid client id and secret, they are only for demonstration purposes)

 4. Fill in the required credentials (netatmo account user and pass, client id and secret) in the code above.

 5. Go to Amazon Apps and Services (https://developer.amazon.com/edw/home.html). In the Menu, select Alexa and then Alexa Skills Kit (click on Get started)

 6. Now you need to create a new Skill. Give your skill a name and invokation. I chose "sense". The name will be used to invoke (or start) the application. In the Endpoint field you need to give in the ARN id of your lambda function created earlier. This number can be found on the webpage displaying your lambda function, on the top right corner. It should be something like : arn:aws:lambda:us-east-1:255569121831:function:[your function name]. Once you completed this step, a green checkmark will appear to the left to indicate progress (progress menu).

 7. The next phase involves setting up the interaction model. It is responsible with mapping of utterences to intents and slots. First, the Intent Schema. Copy-paste the interaction model from the repository (intentSchema.json).
 
 8. Next, fill in the Custom Slot Types from the file customSloTypes.map 
 
 9. For the Sample Utterances, fill in the contents with the information found in sampleUtterances.txt
 
 10. The Test, Description and Publishing information can be left blank, unless you plan to send your skill to amazon so as it can be made publicly available. I left mine blank. :)

 11. Almost there. You just need to enable the new skill. Go to http://alexa.amazon.com/ and in the left menu, select Skills. Find your skill and click enable.

 12. That awesome moment. Say "Alexa, open [your skill name].". By default, the indoor and outdoor temperature should be fetched from the netatmo cloud and read out loud by Alexa. you can also say "Alexa, open [your skill name] and get the temperature in the bedroom.". As you already might have noticed, the part " get the temperature in the [Location]" corresponds to the sample uttereces you filled in earlier.


 
# Usage
I use it like : "Alexa, open sense.". By default, the indoor and outdoor temperature should be fetched from the netatmo cloud and read out loud by Alexa. you can also say "Alexa, open [your skill name] and get the temperature in the bedroom.".
 
# License
This software is freely available under the GNU GPL v3.0 aegis, please consult the LICENSE file for further information
