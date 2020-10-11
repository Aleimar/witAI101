# WIT.AI101
Wit.ai 101: Basics of Natural Language Processing through [Wit.ai](https://wit.ai)

> This tutorial is learning basic concepts of Natural Language Processing and its implementation through Wit.ai.

# Introduction
**Natural Language Processing (NLP)** is the science of extracting the intention of text and relevant information from text. One of the common applications of NLP is Conversational AI or Chatbots. Alexa, Siri and other [businesses](https://www.businessinsider.com/business-chatbot-examples) like [Sephora](https://web.facebook.com/sephora) uses bots and virtual assistants to aid our daily tasks/reminders/business processes using human language (natural language).

In this tutorial, we will discuss the essential concepts in NLP, applying these concepts by creating an NLP application using Wit.ai, and training and testing our intelligent application.

<p align="center">
<img src="https://aleimar.github.io/witAI101/images/intro_image.png" width="600" height="400"> 
 </p>

## Utterance
Utterance is input from the user that we need to interpret to deliver the correct response.
Basically, anything the user says: 

* *What day is it?* 
* *Thank you!* 
* *I'd like to order sandwich.* 

Whether a question, an expression or a command, **the whole statement is called an *utterance***. 

## Intents
An intent represents a task or action the user wants to perform. It is a purpose or goal expressed in a user's utterance. 

Intent | Utterance
------------ | -------------
Check_Weather | How's the weather today? <br> What's the weather forecast tomorrow? <br> How's the weather like in New York?
 Greetings | Good morning! <br> Hello!
 Travel_Booking | Book me a flight to the Philippines this Friday. <br> I'd like to travel in Singapore this December 25. <br> I need a plane ticket for my trip next week to Bangkok, Thailand.
 
The table above shows user's intentions based on sample utterances like asking *"How's the weather today?"* means that the user want's to check the weather and we label this intent into *Check_Weather*

## Entities
