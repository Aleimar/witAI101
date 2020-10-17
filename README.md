# WIT.AI101
Wit.ai 101: Basics of Natural Language Processing through [Wit.ai](https://wit.ai)

> This tutorial is learning basic concepts of Natural Language Processing and its implementation through Wit.ai.

# Introduction
**Natural Language Processing (NLP)** is the science of extracting the intention of text and relevant information from text. One of the common applications of NLP is Conversational AI or Chatbots. Alexa, Siri and other [businesses](https://www.businessinsider.com/business-chatbot-examples) like [Sephora](https://web.facebook.com/sephora) uses bots and virtual assistants to aid our daily tasks/reminders/business processes using human language (natural language).

In this tutorial, we will discuss the essential concepts in NLP, applying these concepts by creating an NLP application using Wit.ai, and training and testing our intelligent application.

<p align="center">
<img src="https://aleimar.github.io/witAI101/images/intro_image.png" width="600" height="400"> 
 </p>
 
 The three important concepts in NLP for bots are [**Utterance**](#Utterance), [**Intents**](#Intents), and [**Entities**](#Entities):

## Utterance<a name="Utterance"></a>
Utterance is input from the user that we need to interpret to deliver the correct response.
Basically, anything the user says: 

* *What day is it?* 
* *Thank you!* 
* *I'd like to order sandwich.* 

Whether a question, an expression, or a command, **the whole statement is called an *utterance***. 

## Intents<a name="Intents"></a>
An intent represents a task or action the user wants to perform. It is the purpose or goal expressed in user's utterance. 

Intent | Utterance
------------ | -------------
Check_Weather | How's the weather today? <br> What's the weather forecast tomorrow? <br> How's the weather like in New York?
 Greetings | Good morning! <br> Hello!
 Travel_Booking | Book me a flight to the Philippines this Friday. <br> I'd like to travel in Singapore this December 25. <br> I need a plane ticket for my trip next week to Bangkok, Thailand.
 
The table above shows user's intentions based on sample utterances like asking *"How's the weather today?"* means that the user want's to check the weather and we label this intent into *Check_Weather.*

> 💡 **Trivia** <br> Some practitioners classify intents into two type: <br> (1) **Casual Intent** which refers to small talks, usually to *start and end conversation* ("Hi!", "hello", "bye!"), and *affirmative or negative* intentions ("Yes please.", "No, thank you!", "Okay cool").<br> (2) **Business Intent** are the intents that directly map to business processes. If we have a booking flight bot, utterances like "*Book me a flight to the Philippines this Friday*" will have to search for available flights in the Philippines specifically this Friday, the result might give a list of time available and a whole conversation thread is needed to finish the booking flight business process.

## Entities<a name="Entities"></a>
An **entity represents a unit of data** you want extracted from the utterance, such as names, dates, product names, or any significant group of words. An utterance can include many entities or none at all.

### Intent vs. Entities<a name="vsTable"></a>
An **intent is the intention of the whole utterance** while **entities are pieces of data extracted from the utterance**. Intents are tied to actions and entities are information needed to perform this action. 
> 🖥️ In programming perspective, intent would be a trigger to perform an operation/method while entities would be the parameters passed for this method/operation call.

Utterance | Intent | Entities
------------ | ------------ | ------------
How's the weather today? <br> What's the weather forecast tomorrow? <br> How's the weather like in New York? | Check_Weather | {date: today} <br> {date: tomorrow} <br> {location: New York}
Book me a flight to the Philippines this Friday. <br> I'd like to travel in Singapore this December 25. <br> I need a plane ticket for my trip next week to Bangkok, Thailand. | Travel_Booking | {location: Philippines, time: Friday} <br> {location: Singapore, date: December 25} <br> {date: next week, location: Bangkok, Thailand}  
<br>
Take this utterance for example:

```dif
Book me a flight to the Philippines this Friday.
```

Clearly, the intent would be flight booking, or as we labelled *Travel_Booking*, but the utterance also gave us useful data: *'Philippines'* a location data where its actually the destination of the travel, and *'this Friday'* a date data as the day of flight requested. These two data are called **entities** and would help us decide to give a more accurate response to  the user.
<br>
> 💡 **Trivia** <br> **Intents are required, but entities are optional**. Casual intents doesn't need entities as they are just typically *small talk* and no further data required to understand the whole utterance. An utterance may contain two or more occurrences of an entity with the same data type, but the meaning of each data is based on context within the utterance. <br> ```I want to travel from Philippines to Singapore.``` <br> In the example utterance above, you have two location data, *'Philippines'* and *'Singapore'* and you need to specify each entity by creating sub entities: *origin* and *destination* location 

### Composite Entities
Composite Entities are entities within entities.
```I saw 2 black Mercedes. ```
The *2 black Mercedes* is an entity but can also be divided to three entities: ```{number: 2}, {color: black}, {car: Mercedes}```. Composite entities are optional and depends how you train your bot to treat this utterance.

# Application through Wit.ai
## Prerequisites
To follow this tutorial, you just need:
* An Active Facebook Account
* Prepare Terminal/Command Prompt

### Step 1: Open Wit.ai through Browser
* Open [Wit.ai](https://wit.ai). 
* Click **Continue with Facebook**
* Click **New App**
* Name your App (demoApp) then click **Create**

<p align="center">
<img src="https://aleimar.github.io/witAI101/images/part1.gif"> 
 </p>
 
 Now, you are in the understanding tab of Wit.ai. 

### Step 2: Adding sample Utterances
We will now add sample utterances to train our app.

<p align="center">
<img src="https://aleimar.github.io/witAI101/images/understanding.png"> 
 </p>

* In the utterance bar, type the sample utterance for our app.  
``` Book me a flight to the Philippines this Friday ```


### Step 3: Adding Entities
* Highlight entities: *this Friday* and *Philippines* then search for built-in entity of wit.ai
> See this [link  for list of wit.ai built-in entities](https://wit.ai/docs/built-in-entities/20200513/) 

``` Example: After highlighting Philippines search the word 'location' in entity, then click it once found to assign location entity for Philippines```


<p align="center">
<img src="https://aleimar.github.io/witAI101/images/addentity.png"> 
 </p>
 
 * After you assigned entities, you should see something like this:
 
 <p align="center">
<img src="https://aleimar.github.io/witAI101/images/entity.png"> 
 </p>
 
``` Wrap up of step 2 and 3: ```

<p align="center">
<img src="https://aleimar.github.io/witAI101/images/addingData.gif" > 
 </p>
 
 ### Step 4: Adding Intents
 * To add intent, after typing the utterance, click *Choose or Add Intent*
 * Create new intent (Travel_Book) then click *Create Intent*
 * Click **Train and Validate** to train the app with the sample utterance
 
 <p align="center">
<img src="https://aleimar.github.io/witAI101/images/addingIntent.gif" > 
 </p>
 
> I repeated steps 2 - 4 to create my demoApp using the [sample table of Intents vs. Entities](#vsTable)


### Step 5: Testing the App
* Under **Management** tab and click **Settings**
* Under **HTTP API** enter a test utterance; *'good night'*

 <p align="center">
<img src="https://aleimar.github.io/witAI101/images/test.png"> 
 </p>
 
 * Copy the curl request generated. The paste it in your terminal
 <p align="center">
<img src="https://aleimar.github.io/witAI101/images/request.png"> 
 </p>
 
 
 * Hit enter and a response will be given briefly
 <p align="center">
<img src="https://aleimar.github.io/witAI101/images/response.png"> 
 </p>
 
 > ❗ NOTE: <br> For windows user, copy-paste directly the curl command to your command prompt might result to multiple command so what you can do first is paste it in notepad, delete new lines (enter) and backslahes '\\', so the whole command should be just one line. Also delete the space between colon (:) and **Bearer**, then replace single quotes (') with double quotes(") and your command should look like this: <br> curl -H "Authorization:Bearer ERPO3QGEHBB2QKEMRVPHJWYP22PR36GV" "https://api.wit.ai/message?v=20201013&q=good%20night"
 

 <p align="center">
<img src="https://aleimar.github.io/witAI101/images/part3a.gif" > 
 </p>

* The response is in JSON format. To make it more understandable, highlight the response, copy then go to [JSON Pretty Print Online](https://jsonformatter.org/json-pretty-print) paste it on the left editor, then click **Make Pretty** and see the result in the right side:

 
 <p align="center">
<img src="https://aleimar.github.io/witAI101/images/part3b.gif" > 
 </p>
 
 ### Step 6. Inspecting response
 
> The sample response from *'good night'* test utterance
 
 ```javascript
 {
  "text": "good night",
  "intents": [
    {
      "id": "2396879380619776",
      "name": "Greeting",
      "confidence": 0.701
    }
  ],
  "entities": {},
  "traits": {}
}
 ```
 
The response essentially contains:
* **text** - the user utterance
* **intents** - which contains **name** or the intent detected, and **confidence** as the probability that the intent classification is confidently correct.
* **entities** - which contains the entities extracted in the utterance (in this case, no entity is detected)

By this example, we can conclude that our app is 70% confident that *'good night'* is a *Greeting* intent, then we craft possible response for greetings like this to the users.

``` Doing the same step in 5 and 6, I tried 'Fly me to South Korea on the 30th' ```

We will have a response that looks like this:
```javascript
{
  "text": "Fly me to South Korea on the 30th",
  "intents": [
    {
      "id": "2617649178488304",
      "name": "Travel_Book",
      "confidence": 0.547
    }
  ],
  "entities": {
    "wit$datetime:datetime": [
      {
        "id": "2709435475941805",
        "name": "wit$datetime",
        "role": "datetime",
        "start": 22,
        "end": 33,
        "body": "on the 30th",
        "confidence": 0.9622,
        "entities": [],
        "type": "value",
        "grain": "day",
        "value": "2020-10-30T00:00:00.000-07:00",
        "values": [
          {
            "type": "value",
            "grain": "day",
            "value": "2020-10-30T00:00:00.000-07:00"
          },
          {
            "type": "value",
            "grain": "day",
            "value": "2020-11-30T00:00:00.000-08:00"
          },
          {
            "type": "value",
            "grain": "day",
            "value": "2020-12-30T00:00:00.000-08:00"
          }
        ]
      }
    ],
    "wit$location:location": [
      {
        "id": "3389580727801815",
        "name": "wit$location",
        "role": "location",
        "start": 10,
        "end": 21,
        "body": "South Korea",
        "confidence": 0.8921,
        "entities": [],
        "resolved": {
          "values": [
            {
              "name": "South Korea",
              "domain": "country",
              "coords": {
                "lat": 36.5,
                "long": 127.75
              },
              "timezone": "Asia/Seoul",
              "external": {
                "geonames": "1835841",
                "wikidata": "Q884",
                "wikipedia": "South Korea"
              },
              "attributes": {}
            }
          ]
        },
        "type": "resolved"
      }
    ]
  },
  "traits": {}
}
```

We can see that:

* **text** - Fly me to New York on the 30th
* **intents** 
  * **name** - Travel_Book
  * **confidence** - 0.547
* **entities** 
  * **datetime**  - body: on the 30th
  * **location** - body: South Korea
 
From this example, we see that its only 54% confident that the utterance *'Fly me to South Korea on the 30th'* has a **Travel_Book** intention. This is understandable, since we have limited utterance sample for our app. We have to train it with more sample data for better performance.

> ❗ **NOTE** <br> In our latest example, we see that entities also contains other data like role, coordinates, timezone etc. <br> It all depends on how you will use all other data from the response body, in our demo, we are only interested on what entities are being captured, and the intent that is classified by the test utterance.

# What’s next?
Now that we have an intelligent NLP system, thanks to Wit.ai! We can now connect our chatbots or web apps to process queries by different users and craft appropriate responses to them based on what intent and entities are being extracted/classified by our system.

### When does training for intents and entities stop?
You can never train it enough. Languages and its usage changes from time to time, it would be better to check accuracy of your NLP system and train with new utterances you captured from users to improve it! 

This is why natural language processing is exciting! You get to be updated with current cool languages of people and make your bot keep up with the current trend 😎

### Connect your app to your chatbot
> In the future, I'll create tutorial in setting up basic chatbot for beginners, and how to connect wit.ai.

In the meantime, you can check this [link for creating a messenger bot tutorial](https://github.com/jw84/messenger-bot-tutorial)


# Links and useful references to learn more about key concepts:
* [Chatbot Vocabulary: 10 Chatbot Terms You Need to Know](https://chatbotsmagazine.com/chatbot-vocabulary-10-chatbot-terms-you-need-to-know-3911b1ef31b4)
* [What Is Conversational AI?](https://www.iotforall.com/what-is-conversational-ai)
* [Chat Bots — Designing Intents and Entities for your NLP Models](https://medium.com/@brijrajsingh/chat-bots-designing-intents-and-entities-for-your-nlp-models-35c385b7730d)
* [Built-In Entities and Traits of Wit.ai](https://wit.ai/docs/built-in-entities/20200513/)
