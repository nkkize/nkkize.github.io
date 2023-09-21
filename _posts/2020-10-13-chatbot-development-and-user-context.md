---
layout: post
title: The Power of Context in Conversational AI
date: 2020-10-13 13:32:20 +0300
description: The Power of Context in Conversational AI
img: i-chatbots.png
fig-caption: # Add figcaption (optional)
tags: [Chatbots, user-context]
---

## The Power of Context in Conversational AI
In our technologically advanced era, we find ourselves engaging with computers using the most natural form of communication—our spoken and written language. Everyday devices like Google Home, Google Assistant, Amazon Alexa, and voice and chat-based assistants have become integral parts of our lives. But have you ever wondered how these applications work their magic? The answer lies in the realm of Natural Language Processing (NLP).

NLP tools and services play a pivotal role in these applications. They effortlessly convert our spoken words into text and decipher the intent behind them. Once the intent is established, these assistants make intelligent decisions on how to respond effectively. However, the journey from understanding the intent to crafting a meaningful and context-aware reply is a multifaceted one.  

<img src="https://media3.giphy.com/media/Up7LOrG2RI89zDa0tC/200.gif?cid=ecf05e47y5d5drbust7n9zsu2lak3ezjb5v5hs3hbs1aotxj&rid=200.gif&ct=g" width="175px">

### The Missing Link: User Context
To provide responses that feel natural and intelligent, it's crucial to establish a robust context around the conversation. However, building context isn't as straightforward as it might seem. In this post, we'll explore key aspects of context building:

1. User's Historical Context: Harnessing information from the user's conversation history.
2. Environmental Context: Leveraging information about the user's environment.
3. User-Supplied Context: Utilizing context explicitly provided by the user.


Let's consider an example of a shopping assistant application. Users can ask a range of questions, such as:
1. Where is my order?
2. is my order shipped yet?
3. How can I return this item? 
4. I ordered a blue shirt but I received a black one, can you refund? 
5. How many reward points do I have?
6. ...

When users pose these questions, a substantial context is already established:
- The application will know that the user is a customer who has ordered something.
- The user seeks information related to their past purchases or ongoing offers.

With this high-level context in place, the application knows the user's query revolves around previous orders, not new offers. However, for the application to craft the most suitable response, it must build a more specific context around the conversation. For example, the application can leverage the user's history to access details of the user's last order, accumulated reward points, applied discounts, and more. Armed with this information, the application can respond intelligently, making the conversation feel seamless and natural.

### Using Context to Craft Responses
Let's delve deeper by considering the following scenarios:

- User: I want to buy shoes.
- Assistant: can you please tell me the color of the shoes you want to buy? 
- User: white
- Assistant: got it. What size are you looking for? 
- User: 8
- Assistant: got it. What type of shoes do you want to buy?
- User: sneakers
- Assistant: [gives options of the white sneakers of size 8]

Let’s take another example of the same conversation:

- User: I want to buy shoes.
- Assistant: can you please tell me the color of the shoes you want to buy? 
- User: black
- Assistant: What size? 
- User: I want to order pizza.
- Assistant - ... [gets confused here]

In Scenario 2, the application gets confused after the abrupt shift from shoes to pizza. The context is key in handling such transitions more gracefully. Imagine a more context-aware approach:

The application can proactively build a detailed user profile based on previous shopping history. Let's assume the user recently purchased sports shoes in size 8. Using this information, the application establishes context and enhances the conversation: 

- User: I want to buy shoes.
- Assistant: Got it. You recently bought sports shoe of size 8. is 8 the right size? [gives options of yes or no]
- User: yes [user selects yes]
- Assistant: Great. Plesse select the color of the shoes you looking for? [gives options of the color for user to select]
- User: white [select white]
- Assistant: great choice. [gives options of the shoes]

### Conclusion
This example simplifies a complex process, but it effectively illustrates the power of context. We'll explore context creation in more detail in upcoming posts. Stay tuned to discover how harnessing context can elevate the conversational AI experience to new heights.
