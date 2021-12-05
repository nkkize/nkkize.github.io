---
layout: post
title: Chatbots and User Context
date: 2020-10-13 13:32:20 +0300
description: chatbots and user context
img: i-chatbots.png
fig-caption: # Add figcaption (optional)
tags: [Chatbots, user-context]
---
We are living in the era of technological advancement where we are able to communicate with the computers in a natural way using the natural language we speak. We use voice and chat based assistants, and devices such as Google home, and google Assistant, Amazon Alexa etc. every day. Lets think about how these applications work. The natural language processing tools and services help us to convert the voice to text, and process the converted text to get the intent of what we speak. Based on the intent and other extracted informations from the text, the assistant makes wise decisions to reply back. But this is not enough, sometimes we have to understand much more than this to reply in a smarter way.  

<img src="https://media3.giphy.com/media/Up7LOrG2RI89zDa0tC/200.gif?cid=ecf05e47y5d5drbust7n9zsu2lak3ezjb5v5hs3hbs1aotxj&rid=200.gif&ct=g" width="175px">

### User Context
To reply back to the user in a natural and smart way, we have to get a better context around the conversation. However, building the context is not as easy as it seems. In this post I will talk about some of the important aspects from where we can build the context:


1. Getting context from the user's history.
2. Getting context from the environment.
3. Getting context from the user itself.

Let’s take an example of a assistant app from a shopping application where user can asks below questions to the assistant app:
1. Where is my order?
2. is my order shipped yet?
3. How can I return this item? 
4. I ordered a blue shirt but I received a black one, can you refund? 
5. How many reward points do I have?
6. ...

When user asks such questions - there is a lot of context already set for the application to answer the question: 
- The application will know that the user is a customer who has ordered something.
- The user wants to get some information related to his previous purchases or recent offers.

With this high level context already set, the application knows that the user query is about the order purchased and not about the new offers. However, to best answer the user’s question the application can now build a more specific context around the conversation Eg. from the history, the application knows the user’s last order info, the reward points user earned, any discounts taken etc. The application can build a context using this information and answer user in a way that it seems meaningful, smart and natural at the same time.  
The applicaton can also ask more specific question to build this context. Such as out of all the user's pending orders, which order the query is for. However, asking the user specific questions to get more context may not be always the best option since it will involve further understanding user’s response. The application should handle the scenario more gracefully when the user switches his intent and the flow is broken. 

### Using Contexts to build Response
To explain it further let’s take the example of a conversation and different scenarios the application could respond:

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

After this moment in the conversation, the application gets confused and will not be able to get the size. The context comes here to the rescue. Lets handle this scenario in a better way:  

The application after getting the first question from the user can build a more detailed context for the user using his shopping history. Let’s asssume user recently bought some product. The application can create the size, color, brands etc. preferences of the user from history; and using this information the application can build a context. Let’s take the example of same scenaio as above:  

- User: I want to buy shoes.
- Assistant: Got it. You recently bought sports shoe of size 8. is 8 the right size? [gives options of yes or no]
- User: yes [user selects yes]
- Assistant: Great. Plesse select the color of the shoes you looking for? [gives options of the color for user to select]
- User: white [select white]
- Assistant: great choice. [gives options of the shoes]

### Conclusion
This is a simple example, but this is very effective. I will talk about creating context in more details in my upcoming posts. Stay Tuned!!
