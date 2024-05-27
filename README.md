# langgraph-with-crewai

This repository contains detailed introduction to Langgraph, a new Langchain library. You will learn about langgraph and also create a miniproject using crewai and langgraph

[**Read the Blog!**](https://www.ionio.ai/blog/a-comprehensive-guide-about-langgraph-code-included)

## 🤔 How it works?

**1. Get information from user and categorize it**

Agent will take the user input and then categorize it based on the user query

**2. Decides where to go using conditinal edge of langgraph**

Agent uses langgraph to use the node based on the category of user query

**3. Uses Langgraph nodes to integrate different workflows**

Each workflow can be used as a subgraph or node which makes it easy to visualize and create any complex workflow which makes it multi-purpose agent.

## ⚒️ Architecture

Let’s take a look at the workflow of our agent!

![](https://assets-global.website-files.com/62528d398a42420e66390ef9/6641f8896dd1ef4f1d90e806_image7.png)

We will first add the user input in our entry node where the user input will be categorized into 3 categories:

- **email_query:** If user want to generate an email response to given email
- **weather_query:** If user want weather information about any location
- **other:** If user want any other information

Now based on the categories, we will redirect the query to right node. 🔂

We will use CrewAI to create a crew which can categorize the email and then based on the category it will write a response. We will also create an separate agent for weather where we will provide the openweather function as a tool and it will automatically format the final weather information response. For all other queries, we will just make a simple OpenAI call.

## Prerequisites

Here are the things you will need to create this project

- [OpenAI API key](https://openai.com/)
- [Openweather API key](https://openweathermap.org/api)
- A basic knowledge about CrewAI (If you don’t know about CrewAI then I suggest you to [take a look at my blog about CrewAI](https://www.ionio.ai/blog/how-to-build-llm-agent-to-automate-your-code-review-workflow-using-crewai))

## How to run?

- Clone the repository
- Setup your environment variables

```py
import os
os.environ['OPENAI_API_KEY'] = openai_secret
os.environ["OPENWEATHERMAP_API_KEY"] = openweather_secret
```

- Open any jupyter notebook from repository
- Select your existing python environment or create one using anaconda
- Run the code
