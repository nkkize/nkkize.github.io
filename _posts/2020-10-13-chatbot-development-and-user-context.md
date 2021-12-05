---
layout: post
title: Chatbots and User Context
date: 2020-10-13 13:32:20 +0300
description: chatbots and user context
img: i-chatbots.jpg
fig-caption: # Add figcaption (optional)
tags: [Chatbots, user-context]
---
We are living in the era of technological advancement where we are able to communicate with the computers in a natural way using the natural language we speak. We use voice and chat based assistants, and devices such as Google home, and google Assistant, Amazon Alexa etc. every day. Lets think about how these applications work. The natural language processing tools and services help us to convert the voice to text, and process the converted text to get the intent of what we speak. Based on the intent and other extracted informations from the text, the assistant makes wise decisions to reply back. But this is not enough, sometimes we have to understand much more than this to reply in a smarter way.  

<img src="https://media3.giphy.com/media/Up7LOrG2RI89zDa0tC/200.gif?cid=ecf05e47y5d5drbust7n9zsu2lak3ezjb5v5hs3hbs1aotxj&rid=200.gif&ct=g" width="175px">

### User Context
To reply back to the user in a natural and smart way, we have to get a better context around the conversation. However, building the context is not as easy as it seems. In this post I will talk about some of the important aspects from where we can build the context:

1. Getting context from the user itself.
2. Getting context from the environment.
3. Getting context from the  history.

Let’s take an example of a shopping assistant app from a shopping mall where user can asks below questions to the assistant app:
1. Where is my order?
2. is my order shipped yet?
3. How can I return this item? 
4. I ordered a blue shirt but I received a black one, can you refund? 
5. How many reward points do I have?

When user ask such questions - there is a lot of context already set for the app to answer the question: 
- The app will know that the user is a customer who has ordered something in the mall or from online website.
- The user wants to get some information related to his previous purchases or recent offers.

With this high level context already set, the app knows that the user query is about the order purchased and not about the new offers. However, to best answer the user’s question the app can now build a more specific context around the conversation by using user’s conversation history, user’s location in the mall etc.  Eg. from the history, the app knows the user’s last order info, the reward points user earned, discount etc. The app can also ask more specific question to build this context. However asking the user specific question to get more context may not be always the best option since it will involve further understanding user’s response. 

### Using Contexts to build Response
To explain it further let’s take an example of a user query: user says- I want to buy shoes. The app understands the user is a shopper who wants to buy shoes. Let’s take the example of the conversation:

- User: I want to buy shoes.
- Assistant: can you please tell me the colour of the shoes you want to buy? 
- User: white
- Assistant: What size? 
- User: 8
- Assistant: What type of shoes do you want to buy?
- User: sneakers
- Assistant: [gives options of the shoes]

Let’s take another example of the same conversation:

- User: I want to buy shoes.
- Assistant: can you please tell me the colour of the shoes you want to buy? 
- User: black
- Assistant: What size? 
- User: I want to order pizza.

After this moment in the conversation the assistant gets confused and will not be able to get the size. 

The context comes here to the rescue.

The assistant after getting the first question from the user can build a more detailed context for the user using his shopping history. Let’s suppose user recently bought blue jeans. Using that the assistant can build a context and use this information to ask further question. Let’s take this example:

- User: I want to buy shoes.
- Assistant: you recently bought the blue pair of jeans. The white casual sneakers would go well with the jeans. Do you want me to show you the casual shoes option?
- User: yes
- Assistant: [gives options of the shoes]

### Conclusion
This is an simple example, but this is very effective. I will talk about creating context in more details in my upcoming blogs. Stay Tuned!!
