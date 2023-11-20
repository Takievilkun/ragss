# RAGs

RAGs is a Streamlit app that lets you create a RAG pipeline from a data source using natural language.

You get to do the following:
1. Describe your task (e.g. "load this web page") and the parameters you want from your RAG systems (e.g. "i want to retrieve X number of docs")
2. Go into the config view and view/alter generated parameters (top-k, summarization, etc.) as needed.
3. Query the RAG agent over data with your questions.

This project is inspired by [GPTs](https://openai.com/blog/introducing-gpts), launched by OpenAI.

## Installation and Setup 

Clone this project, go into the `rags` project folder.

```
pip install -r requirements.txt
```

Then run the app from the "home page" file.

```

streamlit run 1_🏠_Home.py

```

## Detailed Overview

The app contains the following sections, corresponding to the steps listed above.

### 1. 🏠 Home Page
This is the section where you build a RAG pipeline by instructing the "builder agent". Typically to setup a RAG pipeline you need the following components:
1. Describe the dataset. Currently we support either **a single local file** or a **web page**. We're open to suggestions here! 
2. Describe the task. Concretely this description will be used to initialize the "system prompt" of the LLM powering the RAG pipeline.
3. Define the typical parameters for a RAG setup. See the below section for the list of parameters.

### 2. ⚙️ RAG Config

This section contains the RAG parameters, generated by the "builder agent" in the previous section. In this section, you have a UI showcasing the generated parameters and have full freedom to manually edit/change them as necessary.

Currently the set of parameters is as follows:
- System Prompt
- Include Summarization: whether to also add a summarization tool (instead of only doing top-k retrieval.)
- Top-K
- Chunk Size
- Embed Model
- LLM 

If you manually change parameters, you can press the "Update Agent" button in order to update the agent.

```{tip}
If you don't see the `Update Agent` button, that's because you haven't created the agent yet. Please go to the previous "Home" page and complete the setup process.
```

We can always add more parameters to make this more "advanced" 🛠️, but thought this would be a good place to start.

### 3. Generated RAG Agent

Once your RAG agent is created, you have access to this page.

This is a standard chatbot interface where you can query the RAG agent and it will answer questions over your data.

It will be able to pick the right RAG tools (either top-k vector search or optionally summarization) in order to fulfill the query.


## Issues / Contributions

Running into issues? Please file a Github issue or join our [Discord](https://discord.gg/dGcwcsnxhU).