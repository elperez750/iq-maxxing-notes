
2026-03-25 20:36

Status:

Tags:

# What is RAG

##### Author:


## References
https://www.singlestore.com/blog/a-guide-to-retrieval-augmented-generation-rag/

https://www.datacamp.com/tutorial/building-a-rag-system-with-langchain-and-fastapi



### Notes

## What is Retrieval Augmented Generation (RAG)?

essentially, RAG is used to make LLM responses be more customized, by feeding it data specific your company, or in the case of my project, for notes

This not only makes sure that the LLM responses are accurate, but so that they are up to date. For most public LLMs, they have a training cutoff date where they no longer have context after a certain window


##### After doing more research, it seems that the RAG is built on top of the GPT or any LLM. It uses the data it was trained on and then provides your context (Which in my case is my notes) to the LLM.


## Key concepts in RAG

* Retrieval: This component helps you fetch the relevant information from the external knowledge base like a vector database for any given user query. This component is very crucial as this is the first step in curating the meaningful and contextually correct responses.

##### In the case for my project, it would be retrieving notes such as the book notes and general notes.



* Augmentation: This part involved enhancing and adding more relevant context to the retrieved response for the user query.

##### So would this be splitting up the data? Would enhancing mean cleaning the data?




* Generation: Finally, a final output is presented to the user with the help of a large language model (LLM). The LLM uses its own knowledge and the provided context and comes up with an apt response to the user’s query.

##### So the LLM will be trained on my note data and provide relevant data. Such as show me notes related to the soul or recommend resources based on the questions that i had.

###### Answer: No, the LLM data is not gonna be trained on my note data. Instead, I will hand it my question as well as the context here in order to write a good answer.

## Advantages of RAG

* **Scalability:** RAG approach helps you with scale models by simply updating or adding external/custom data to your the external database (vector database).

##### So it seems to me like the LLM will not be bloated with info it doesn't need? But then how can it answer questions like book recommendations if it doesn't have access to that info?


- **Memory Efficiency**: Traditional models like GPT have limits when it comes to pulling fresh and updated information and fails to be memory efficient. RAG leverages external databases like a vector database — allowing it to pull in fresh, updated or detailed information when needed with speed.

##### So what is the main difference between GPT and this? How does this connect to GPT?


Minimize Hallucinations: The training data used in RAG is crucial for fine-tuning the model and improving its performance, addressing issues like bias and model hallucination.


##### This makes sense intuitively, since a big LLM such as GPT probably has so many topics that it is trained on, making it easier to get confused.



**Flexibility**:  By updating or expanding the external knowledge source, you can adapt RAG to build any AI applications with flexibility.


##### This one is the most obvious. The LLM can focus on what I want it to focus on



![[923544850d12d8312c8367187c49214b 1.avif]]




## Essential steps in a RAG system

- Document Loaders:These tools pull in data from various sources (text files, PDFs, databases…) They convert that info into a format the system can actually use. Basically, they make sure all the important data is ready and in the right shape for the next steps.

##### Essentially this will be the logic that takes in the markdown files. What does it mean by right shape though?


###### Answer: the right shape usually means a unified format such as string with metadata, a reasonable chunk size, and clean enough that noise such as HTML junk does not dominate


- Text Splitting: Once the data is loaded, it gets chopped into smaller chunks. This is super important because smaller pieces are easier to search through, and language models work better with bite-sized bits of info due to their processing limits.


##### I'm still confused on how the text splitting is done. Will this be done randomly?


###### Answer: Usually it is not random. We could split into fixed size chunks by character size with overlap. The overlap is needed so that we don't skip over information that could be relevant to a chunk




- Indexing: After splitting, you need to organize the data. Indexing turns those text chunks into vector representations. This setup makes it easy and fast for the system to search through all that data and find what’s most relevant to a user’s query.

##### So indexing is what makes it easier to search for things. Does it organize based on the words?


###### Answer: The indexing is basically just turning the chunks into vectors, making it easy to search for in the vector database.



- Vector Stores: These are databases designed to handle those vector representations of the [text chunks](https://www.datacamp.com/blog/chunking-strategies). They make searching super efficient by using a method called vector similarity search, which compares the query to the stored vectors and pulls the best matches.


##### So this is where all my text will be stored.


- Retrievers: These components do the actual searching. They take the user’s query, convert it into a vector, and then search the vector store to find the most relevant data. Once they grab that info, it’s passed along to the next step: generation.

##### One thing I would be interested in learning is how each word is represented as a vector, meaning what is the process for representing each character. Are they represented by ascii values? Are they random, meaning that the character "a" will always be represented in the same way?


###### Answer: No it is not ascii lol. Instead it is set to random when first trained. Over training, the vectors for words that are similar end up near each other whereas ideas completely unrelated end up farther apart.









