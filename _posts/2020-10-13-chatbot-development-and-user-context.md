### Background
One of the important thing which human beings has created ever since the evolution is the Language. Language makes us to understand each other and communicate our thoughts. there are more than 1 million languages around the world. Imagine a person who can speak and write in Japanese only talking with a person who knows only English, this seems a real problem for both of them to communicate with each other. The same is the issue with the computers. We are living in the era of technological advancement where we are able to communicate with the computers in a natural way using the natural language we speak in our day to day life. Ex. Google assistant, amazon Alexa and so many other voice and chat assistants.  Language is not easy and hence making the computers to understand the natural language is really a tough job. There are natural language processing tools and services which helps us to convert voice to text and process the text to understand the intent of what we speak and extract the key information from the text so that computer can make wise decisions to reply in a smarter way using the key information. But this is not enough, sometimes we have to understand much more than this to reply to someone.  

### User Context
We have to get a better context around the conversation to respond. However building context is not as easy as it seems . We have to see a number of factors before building the context. In this blog  I will talk about some of the most important aspects from where we can build the context. There are

1. Getting context from the user itself,
2. Getting context from the environment
3. Getting context from the  history.

Let’s take an example of a shopping assistant app from a shopping mall. This app sends you receipt when you purchase something from a retailer in the mall and helps you to keep your all receipts at one place. This app also sends you receipt once you purchase something from the online website of the retailers in the shopping mall and keeps you updated about the status of your order. This app occasionally sends you interesting offers when the sale is on in the mall.

To deliver you a receipt, and keep you informed about the latest offers in the mall are examples of one way communication. This conversation is initiated from the app and the user is on the other hand on mute mode. But that is not the way the conversation happens the in the real world. An assistant app should understand the communication initiated by the user as well and answer to the user in a natural way.

Let’s the user asks below questions to the assistant app:
1. Where is my order?
2. is my order shipped yet?
3. How can I return this? 
4. I ordered a blue shirt but I received a black one, can you refund? 
5. How many reward points do I have?

When user ask such questions- there is a lot of context already set for the app to answer the question. For example the app will know that the user is a customer who has ordered something in the mall or from online website. The user wants to get some information related to his previous purchases or recent offers.

With this high level context already set, the app knows that the user query is about the order purchased and not about the new offers. However, to best answer the user’s question the app can now build a more specific context around the conversation by using user’s conversation history, user’s location in the mall etc.  Eg. from the history, the app knows the user’s last order info, the reward points user earned, discount etc. The app can also ask more specific question to build this context. However asking the user specific question to get more context may not be always the best option since it will involve further understanding user’s response. To explain it further let’s take an example of a user query: user says- I want to buy shoes. The app understands the user is a shopper who wants to buy shoes. Let’s take the example of the conversation:

User: I want to buy shoes.
Assistants: can you please tell me the colour of the shoes you want to buy? 
User: white
Assistant: What size? 
User: 8
Assistant: What type of shoes do you want to buy?
User: sneakers
Assistant: [gives options of the shoes]

Let’s take another example of the same conversation:

User: I want to buy shoes.
Assistants: can you please tell me the colour of the shoes you want to buy? 
User: black
Assistant: What size? 
User: I want to order pizza.

After this moment in the conversation the assistant gets confused and will not be able to get the size. 

The context comes here to the rescue.

The assistant after getting the first question from the user can build a more detailed context for the user using his shopping history. Let’s suppose user recently bought blue jeans. Using that the assistant can build a context and use this information to ask further question. Let’s take this example:

User: I want to buy shoes.
Assistants: you recently bought the blue pair of jeans. The white casual sneakers would go well with the jeans. Do you want me to show you the casual shoes option?
User: yes
Assistant: [gives options of the shoes]

This is an simple example, but this is very effective. I will talk about creating context in more details in my upcoming blogs. Stay Tuned!!
