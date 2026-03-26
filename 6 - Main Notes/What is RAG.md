
2026-03-25 20:36

Status:

Tags:

# What is RAG

##### Author:


## References
https://www.singlestore.com/blog/a-guide-to-retrieval-augmented-generation-rag/



### Notes

## What is Retrieval Augmented Generation (RAG)?

essentially, RAG is used to make LLM responses be more customized, by feeding it data specific your company, or in the case of my project, for notes

This not only makes sure that the LLM responses are accurate, but so that they are up to date. For most public LLMs, they have a training cutoff date where they no longer have context after a certain window


## Key concepts in RAG

* Retrieval: This component helps you fetch the relevant information from the external knowledge base like a vector database for any given user query. This component is very crucial as this is the first step in curating the meaningful and contextually correct responses.

##### In the case for my project, it would be retrieving notes such as the book notes and general notes.



* Augmentation: This part involved enhancing and adding more relevant context to the retrieved response for the user query.

##### So would this be splitting up the data? Would enhancing mean cleaning the data


* Generation: Finally, a final output is presented to the user with the help of a large language model (LLM). The LLM uses its own knowledge and the provided context and comes up with an apt response to the user’s query.

##### So the LLM will be trained on my note data and provide relevant data. Such as show me notes related to the soul or recommend resources based on the questions that i had.



## Advantages of RAG

* **Scalability:** RAG approach helps you with scale models by simply updating or adding external/custom data to your the external database (vector database).

##### So it seems to me like the LLM will not be bloated with info it doesn't need? But then how can it answer questions like book recommendations if it doesn't have access to that info?


- **Memory Efficiency**: Traditional models like GPT have limits when it comes to pulling fresh and updated information and fails to be memory efficient. RAG leverages external databases like a vector database — allowing it to pull in fresh, updated or detailed information when needed with speed.

##### So what is the main difference between GPT and this? How does this connect to GPT?


Minimize Hallucinations: The training data used in RAG is crucial for fine-tuning the model and improving its performance, addressing issues like bias and model hallucination.


##### This makes sense intuitively, since a big LLM such as GPT probably has so many topics that it is trained on, making it easier to get confused.



**Flexibility**:  By updating or expanding the external knowledge source, you can adapt RAG to build any AI applications with flexibility.


##### This one is the most obvious. The LLM can focus on what I want it to focus on













