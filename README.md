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

Whether a question, an expression or a command, **the whole statement is called an *utterance***. 

## Intents<a name="Intents"></a>
An intent represents a task or action the user wants to perform. It is a purpose or goal expressed in a user's utterance. 

Intent | Utterance
------------ | -------------
Check_Weather | How's the weather today? <br> What's the weather forecast tomorrow? <br> How's the weather like in New York?
 Greetings | Good morning! <br> Hello!
 Travel_Booking | Book me a flight to the Philippines this Friday. <br> I'd like to travel in Singapore this December 25. <br> I need a plane ticket for my trip next week to Bangkok, Thailand.
 
The table above shows user's intentions based on sample utterances like asking *"How's the weather today?"* means that the user want's to check the weather and we label this intent into *Check_Weather.*

> :bulb: **Trivia** <br> Some practitioners classify intents into two type: <br> (1) **Casual Intent** which refers to small talks, usually to *start and end conversation* ("Hi!", "hello", "bye!"), and *affirmative or negative* intentions ("Yes please.", "No, thank you!", "Okay cool").<br> (2) **Business Intent** are the intents that directly map to business processes. If we have a booking flight bot, utterances like "*Book me a flight to the Philippines this Friday*" will have to search for available flights in the Philippines specifically this Friday, the result might give a list of time available and a whole conversation thread is needed to finish the booking flight business process.

## Entities<a name="Entities"></a>
An **entity represents a unit of data** you want extracted from the utterance, such as names, dates, product names, or any significant group of words. An utterance can include many entities or none at all.

### Intent vs. Entities
An **intent is the intention of the whole utterance** while **entities are pieces of data extracted from the utterance**. Intents are tied to actions and entities are information needed to perform this action. 
> :computer: In programming perspective, intent would be a trigger to perform an operation/method while entities would be the parameters passed for this method/operation call.

Utterance | Intent | Entities  
------------ | ------------ | -------------
How's the weather today? <br> What's the weather forecast tomorrow? <br> How's the weather like in New York? | Check_Weather | {date: today} <br> {date: tomorrow} <br> {location: New York} 
Book me a flight to the Philippines this Friday. <br> I'd like to travel in Singapore this December 25. <br> I need a plane ticket for my trip next week to Bangkok, Thailand. | Travel_Booking | {location: Philippines, time: Friday} <br> {location: Singapore, date: December 25} <br> {date: next week, location: Bangkok, Thailand}  
<br>
Take this utterance for example:

```dif
Book me a flight to the Philippines this Friday.
```

Clearly, the intent would be flight booking, or as we labelled *Travel_Booking*, but the utterance also gave us useful data: *'Philippines'* a location data where its actually the destination of the travel, and *'this Friday'* a date data as the day of flight requested. These two data are called **entities** and would help us decide to give a more accurate response to  the user.
<br>
> :bulb: **Trivia** <br> **Intents are required, but entities are optional**. Casual intents doesn't need entities as they are just typically *small talk* and no further data required to understand the whole utterance. An utterance may contain two or more occurrences of an entity with the same data type, but the meaning of each data is based on context within the utterance. <br> ```I want to travel from Philippines to Singapore.``` <br> In the example utterance above, you have two location data, *'Philippines'* and *'Singapore'* and you need to specify each entity by creating sub entities: *origin* and *destination* location 

### Composite Entities
Composite Entities are entities within entities.
```I saw 2 black Mercedes. ```
The *2 black Mercedes* is an entity but can also be divided to three entities: {number: 2}, {color: black}, {car: Mercedes}. Composite entities are optional and depends how you train your bot to treat this utterance.

# Application through Wit.ai
## Prerequisites
To follow this tutorial, you just need:
* An Active Facebook Account
* Prepare Terminal/Command Prompt

### Step 1: Open Wit.ai through Browser

# Links and useful references to learn more about key concepts:
* [Chatbot Vocabulary: 10 Chatbot Terms You Need to Know] (https://chatbotsmagazine.com/chatbot-vocabulary-10-chatbot-terms-you-need-to-know-3911b1ef31b4)
* [What Is Conversational AI?] (https://www.iotforall.com/what-is-conversational-ai)
* [Chat Bots — Designing Intents and Entities for your NLP Models] (https://medium.com/@brijrajsingh/chat-bots-designing-intents-and-entities-for-your-nlp-models-35c385b7730d)
* [Built-In Entities and Traits of Wit.ai] (https://wit.ai/docs/built-in-entities/20200513/)
