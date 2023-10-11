# Child Protection Bot - Powered by OpenAI GPT-3.5 and LangChain

## Overview

This project is an AI-powered chatbot designed to protect children by engaging with potential child sexual predators online. It utilizes the OpenAI GPT-3.5 model to simulate a child's conversational style and extract information from potential predators to safeguard children online.

## Features

- **Simulated Child Conversation**: The chatbot simulates the conversation style of a child aged between 9 to 13. It uses a tone that is childish, unaware, and may include inaccurate American English with incorrect punctuation.

- **Engagement with Predators**: The bot engages with potential child predators online, attempting to extract information such as their name, address, and other useful data. It does this by responding in short and childlike messages, keeping the predator engaged in the conversation.

- **Conversation Templates**: Two conversation templates are provided to engage with potential predators:
  1. `prompt_template`: In this template, the bot initiates the conversation and sets the stage for interaction.
  2. `prompt_template_02`: In this template, the bot assumes the role of the child and continues the conversation initiated by the predator.

- **Data Extraction**: The bot uses Langchain's ConversationChain for chaining models, ConversationBufferMemory to store historical data within a request, and PromptTemplate for formatting templates according to the chain's context.

- **Data Parsing**: The bot employs Langchain output parsers to extract insights from the conversation, such as the name of the predator, any addresses mentioned, and the predator's readiness to meet the child.

## Example Conversation

A sample conversation between the predator and the AI bot:

1. Predator: Hi, my name is Jack
   - Kid: Hi Jack! My name is Timmy. What are you doing today?
2. Predator: Hey, I noticed we have a lot in common, and I really enjoy chatting with you. You're so mature for your age
   - Kid: Thank you, Jack! I like talking to you too. What do you like to do for fun? I like playing video games and riding my bike. Do you have any hobbies?
3. Predator: What is 1+1?
   - Kid: Hmm, I think 1+1 is 2. Is that right, Jack? What's your favorite subject in school? Mine is recess, haha.
4. Predator: You're incredibly smart and talented. I've never met anyone like you before
   - Kid: Aww, thank you Jack! You're so nice. What do you like to do for fun? Maybe we can play a game together sometime.
5. Predator: What is my name?
   - Kid: Hmm, I don't remember. Can you tell me again, Jack?
6. Predator: I can buy you that game you've been wanting. Just tell me where you live, and I'll send it to you as a surprise
   - Kid: Wow, that's so nice of you, Jack! But I don't think my parents would like me giving out our address. Maybe we can just keep talking and playing games online together?

## Data Extraction

The bot extracts the following data from the conversation:

- **Name**: The name of the predator.
- **Address**: Any addresses mentioned by the predator. If no address information is found, it outputs None.
- **Readiness**: Indicates whether the predator is ready to meet, with values 0 (not ready) or 1 (ready).

Data Example:
```json
{
	"name": "Jack",
	"address": null,
	"readiness": 0
}
```

## Possible Usage

This bot can be deployed on various AWS services such as Lambda or ECS, and it can act as bait to potential predators in online communities. The bot's role is to engage with these individuals, extract meaningful data, and, when certain features are triggered, invoke an event bridge to take appropriate actions to protect children and report suspicious activity.

Please note that this project's intent is to protect children and report potential threats to the appropriate authorities. It should be used with the utmost care and in compliance with all legal and ethical standards.
