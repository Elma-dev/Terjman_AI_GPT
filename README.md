# TARJMAN_AI
<img src="https://github.com/Dembelinho/Terjman_AI/assets/110602716/40121ee9-27a6-4240-b938-18366125608c" alt="Terjmanlogo" width="212" height="212">

This a Hackathon project's Repo

# Getting Started
## 📚Prerequisite
![Docker](https://img.shields.io/badge/Docker-2496ED.svg?style=for-the-badge&logo=Docker&logoColor=white)
![Postgres SGBD](https://img.shields.io/badge/PostgreSQL-4169E1.svg?style=for-the-badge&logo=PostgreSQL&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB.svg?style=for-the-badge&logo=Python&logoColor=white)
![Google-Colab](https://img.shields.io/badge/Google%20Colab-F9AB00.svg?style=for-the-badge&logo=Google-Colab&logoColor=white)

```
* Ollama
* GPT - OPENAI
* Langchain / llama-index
* HuggingFace

```

# Project: Context & Limitations
The project will be a multilingual question-answering (Q/A) system that specifically handles queries in "Darija" (Moroccan Local Arabic).
## Context: Seed Idea
- In the current time many LLMs can do some great tasks with a big knowledge of different fields but the problem for "Moroccan people" is the query should be in French, English, etc... languages (The most Popular Languages around the world)
- So we got the idea to develop a comprehensive multilingual question-answering (Q/A) platform that allows Moroccan users to interact with advanced Large Language Models (LLMs) using their native languages, such as Darija (Moroccan Arabic), ensuring accessibility and inclusivity in leveraging cutting-edge AI technologies for various informational needs.
- And also the possibility of uploading some documents to extract knowledge from them.
## Use Cases

This can be applied in various scenarios where Moroccan users need accessible and accurate information in their native dialect. Potential application areas include:

- Healthcare: Providing health-related information and advice.
- Education: Answering questions related to studies and learning resources.
- Daily Life: Offering practical advice on everyday matters, such as cooking, home remedies, and local customs.
- Customer Service: Assisting users with inquiries about products, services, or support in their preferred language, etc...

## Limitations of our Solution
- But the limitations of our solution are reflected in expressions with a metaphorical meaning such as proverbs.
- For more clarity, I will give some examples :
  1. "Ta7 l7ok wssab ghtah"
  2. "F9ih li ntsenaw barakto dkhal jame3 b baleghto"
  3. "Drebni w bka, sbe9ni w chka" ,etc....
- In the health field the problem has a 'low probability' of generating false instructions

# Use-cases examples

## 1. CHRE7LIA_AI

<img src="https://github.com/Dembelinho/Terjman_AI/assets/110602716/7f8e3ff1-0971-42c9-b471-b78a0df56442" alt="IS3AFAT_AI">

### Workflow:

This schema illustrates the use case of a conversational AI system called CHRE7LIA_AI.
A user initiates a educational query **(darija-query)** to the system, which processes the query and provides a response **(Jawab)** back to the user in a conversational manner.

### The key components are:

- User: The entity interacting with the system by providing queries.
- Darija-query: The query or input provided by the user, likely in the **Darija** language or dialect.
- CHRE7LIA_AI: The conversational AI system that processes the user's query and generates an appropriate response.
- Jawab: The response or output generated by the system, which is a sentence or answer to the user's query.

### Demonstration
- Screen:

<img src="https://github.com/Dembelinho/Terjman_AI/assets/110602716/0fa23bab-4f56-4c29-9dbe-7549093c71f7" width="600" height="700">

- Gif:

![Q-A GIF](https://github.com/Dembelinho/Terjman_AI/assets/110602716/16329ee0-2fcb-4619-aafb-540318e3e4ea)

## 2. Image generator
From a "DARIJA" query we can generate an image.

- Screen:

<img src="https://github.com/Dembelinho/Terjman_AI/assets/110602716/eb0d83b0-aba9-410b-b4cc-a97673a13123" width="600" height="700">

- Gif:

![GIF image generator](https://github.com/Dembelinho/Terjman_AI/assets/110602716/63d3ee37-227c-4a8c-b82a-4eaf4ccc6518)

## 3. Enterprise Edition
<img src="https://github.com/Dembelinho/Terjman_AI/assets/110602716/d01d690d-3411-45f0-a522-afbc57f7c4ae" alt="Entrep schema">

- Our solution can be used by enterprises in this way:
  
  1- We give them the possibility to create their own Darija_Assistance (**X_DARIJA_AI**) with their documents (RAG parts) in specific fields, via an UI that contains several fields for more flexibility
  
  2- They have the choice between using their local LLM model or our LLMs models.

This is the UI for SMEs

![Entreprise UI](https://github.com/Dembelinho/Terjman_AI/assets/110602716/7a18337b-1bec-4a76-979e-34965cb1aaf2)

# Project Global Schema

<img src="https://github.com/Dembelinho/Terjman_AI/assets/110602716/102c14fb-e89a-4c1d-8e1d-3b63116afe55" alt="Terjman Schema" width="500" height="500">

   This schema outlines a system for processing queries in **"Darija"** (Moroccan Arabic) and converting them into English for further processing by an LLM (Large Language Model). Then translating back the response into Darija. 

   Here’s a detailed explanation of each component and the workflow:

1. **User Interaction (Streamlit)**
   - **User**: The final user interacts with the system through a user interface (UI) built with Streamlit.
   - **Darija Query**: The user submits a query in Darija through the Streamlit interface.

2. **Translation and Embedding**
   - **tarjam_darija_english**: This component translates the Darija query into English. It likely uses a fine-tuned machine translation model "Helsinki-NLP/opus-mt-ar-en", that has    been trained to convert Darija to English.
   - **English Query**: The translated English query is generated from the Darija query.

3. **Processing with LangChain**
   - **LangChain**: A framework used for prompt engineering and managing interactions with LLMs. It is used to create a structured prompt from the English query.
   - **Prompt Engineering**: This step involves creating an appropriate prompt for the LLM to process based on the English query. It involves formatting and structuring the query to get the best possible response from the LLM.

4. **LLM Interaction**
   - **API LLM**: An external API-based large language model (like OpenAI's GPT) is used to process the structured prompt.
   - **Open Sources LLM**: Alternatively, a public LLM model can be used for processing the query. This might be an in-house model or one hosted on any server.
   - **Response Generation**: The LLM processes the prompt and generates a response in English.

5. **Translation Back to Darija**
   - **tarjam_english_darija**: This component translates the English response back into Darija using **" lachkarsalim/Helsinki-translation-English_Moroccan-Arabic "** model from HuggingFace.
   - **Darija Response**: The translated response in Darija is generated from the English response.

6. **Returning the Response**
   - **Postgres**: The queries and responses are stored in a Postgres database for record-keeping, analytics, or further processing.
   - **Streamlit Interface**: The final response in Darija is displayed to the user through the Streamlit interface.

**Workflow Summary**:
1. The user submits a Darija query via Streamlit UI.
2. The Darija query is translated into English using the `tarjam_darija_english` component.
3. The English query is processed using LangChain for prompt engineering.
4. The structured prompt is sent to either an API-based LLM or a public LLM.
5. The LLM generates a response in English.
6. The English response is translated back into Darija using the `tarjam_english_darija` component.
7. The Darija response is stored in a Postgres database and displayed to the user through Streamlit.

This setup effectively handles queries in Darija, leveraging advanced language models for processing and translating responses back to the user's native language.

# Enterprise usage

<img src="https://github.com/Dembelinho/Terjman_AI/assets/110602716/68afc235-a8e9-4867-ae1a-7659f019ecf5" alt="Glob Entr Schema">

## The key components are:

1. Enterprise: The entity that can benefit from 'input/output' queries in **Darija** (Moroccan Arabic dialect).
2. Tarjman_dr_en: A module that translates the Darija query into English.
3. RAG (Retrieval Augmented Generation): This module takes the English query, retrieves relevant information from a document source, and generates a response in English.
4. Tarjman_en_dr: A module that translates the English response back into Darija.
5. UI: The company can create their own Darija_Assistances with their documents(RAG parts) in specific fields, by a UI that contains several fields for more flexibility by:
- 6. OpenSource-llm: These are language models used for various tasks, such as translation and generation... They are deployed on our servers
- 7. Company LLM Server and Private LLM(API LLM): These represent the language models provided by the company or developed internally and the models that offer APIs like (GPT-Cohere...).
8. The enterprise provides the agents/assistance to their clients/employees for chatting with "Darija" (Queries/Responses)

The process flow is as follows:
- The user provides a Darija query.
- The Tarjman_dr_en module translates it to English.
- The RAG module & LLM generates an English response by retrieving relevant information and generating text.
- The Tarjman_en_dr module translates the English response back to Darija.

As summary, the schema depicts a "Darija" language processing pipeline that allows users to interact in their native Moroccan language while leveraging language models and information retrieval techniques to generate relevant responses. 

# RAG Schema
<img src="https://github.com/Dembelinho/Terjman_AI/assets/110602716/367b441d-a9da-47d8-8323-df98a4182170" alt="RAG Schema" width="400" height="500">

This schema illustrates a workflow involving various components for a document retrieval and processing system using LlamaIndex /or Langchain. Here’s an explanation:

1. **Upload Docs**
   - **Document(s) Upload**: We upload a document(s) in a specific field (For example in health -like first aid instruction-).

2. **Local Processing**
   - **Document Handling**: The uploaded document(s) is processed using Advanced RAG (Retrieval-Augmented Generation) Retrieval Strategies.
   - **LlamaIndex / Langchain**: 
     - The document is divided into chunks for efficient processing depending on a chunk's size.
     - These chunks are then embedded and vectorized using an embedding model.
     - The embeddings are stored in a searchable vector database (like Postgres in this case).

3. **Vector Database (Postgres)**
   - **Storage and Retrieval**:
     - The embedded document(s) chunks are saved in Postgres.
     - When a query is received, the system searches through these embeddings to find relevant chunks.
   - **Prompt Template**: A template that helps in forming the retrieval document(s) context to create prompts for further processing.

4. **Remote Processing (Colab Machine)**
   - **ngrok**: Used for establishing secure tunnels to the local environment, allowing remote interaction.
   - **CO (Colab Machine)**: Represents a remote machine (e.g., Google Colab) where additional processing can take place.
   - **LLM (Large Language Model)**: The system leverages a large language model from providers like Mistral AI, Gemma, or Llama for natural language processing tasks.
   - The LLM processes the prompt created using the retrieved document(s) chunks and sends the response back.

5. **Response Handling**
   - The response from the LLM is sent back to the local environment for traduction into 'Darija'.
   - **Streamlit Interface**: The final response is displayed to the user through the Streamlit interface.

**Workflow Summary**:
1. We upload a document(s).
2. The document is chunked, embedded, and stored in Postgres using LlamaIndex Or Langchain.
3. A query is processed by searching the vectorized chunks in Postgres.
4. Relevant chunks are used to form a prompt, which is sent to a remote LLM (via ngrok and CO).
5. The LLM processes the prompt and returns a response.
6. The generated response needs to be translated to 'Darija' and it is displayed to the user through Streamlit.

This setup allows for efficient document retrieval and processing by combining local and remote computational resources and advanced machine-learning models.

## Fine-tuning 

To bypass the limitations of our solution, we tried to finetune an existing model
1. **The model**
   - **facebook/nllb-200-distilled-600M**: This model can accept as a source language: 'DARIJA' and translate it into a target language: 'English'.
2. **The purpose**: This model needs to be fine-tuned so it can translate more words and sentences.
3. **The dataset** : For fine_tune the model we will use the ''' atlasia/darija_english ''' datasets
4. **Dev Environment**: HuggingFace Space
5. **Result**:
   - We initially fine-tuned a smaller version of the model from "facebook/nllb-200-distilled-600M". However, we didn't achieve better results due to issues with the data or hyperparameters.
   - Consequently, we switched to a larger version of the model and attempted to fine-tune it. Unfortunately, we fall in gpu problems.
   - Due to time constraints, we decided to use the larger model directly, as it already provided good translation results.
6. **Benchmark**

- The tested Query : ![query test](https://github.com/Dembelinho/Terjman_AI/assets/110602716/99ac7504-c490-445b-94e4-182c4bd88f90)
  
- Benchmark table
<table align="center">
    <tr>
        <th>Fine-Tuned Model Response</th>
        <th>3.3B-Facebook Model Resp</th>
    </tr>
    <tr>
        <td><img src="https://github.com/Dembelinho/Terjman_AI/assets/110602716/1754ea67-df1b-44c4-a0d0-85ca7d4aabec"/></td>
        <td><img src="https://github.com/Dembelinho/Terjman_AI/assets/110602716/ee225424-abd4-45cc-8a42-acf8088af34f"/></td>
    </tr>
</table>

## Prompt Engineering Techniques

Enhance the usability and relevance of Large Language Models (LLMs) for Moroccan users by adapting the models and their outputs using prompt engineering techniques. This will ensure that the responses are contextually appropriate, culturally relevant, and linguistically accurate.

By using prompt engineering techniques tailored to Moroccan culture, language, and specific domains like healthcare and education, we can significantly enhance the relevance and usability of LLMs for Moroccan users. This approach ensures that the responses are not only accurate but also culturally resonant and practically useful, bridging the gap between advanced AI capabilities and the unique needs of Moroccan communities.

For example, we will compare two results of one query:**"كيفاش نصاوب اتاي"**, before and after using this prompt:
![this make a difference](https://github.com/Dembelinho/Terjman_AI/assets/110602716/02451fe6-e037-41a6-8769-281df7e2ffd0)

## Benchmark table

<table align="center">
    <tr>
        <th>Before Moroccan Prompt</th>
        <th>After Moroccan Prompt</th>
    </tr>
    <tr>
        <td><img src="https://github.com/Dembelinho/Terjman_AI/assets/110602716/34ac669a-a686-40a1-8b88-eb5b3d5cb4c9"/></td>
        <td><img src="https://github.com/Dembelinho/Terjman_AI/assets/110602716/b389259f-3b9f-4480-bf1d-c487642ac3a0"/></td>
    </tr>
</table>

# How to test our app
```
pip install -r requirements.txt
```
