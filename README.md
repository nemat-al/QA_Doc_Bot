# QA_Doc_Bot
Bot in Huggingface space: https://huggingface.co/spaces/nemat-al/QA_bot
The repository is a QA Bot RAG created using LangChain and LLM to answer questions from loaded document.
Step by step:
1. Document loader `PyPDFLoader` from langchain to load the document.
2. Text Splitter `RecursiveCharacterTextSplitter` from langchain to return splitted chuncks of the document.
3. Embedding `hugging_face_embedding` to get the numerical representation of the texts to be stored in a vector store.
4. Vector database `Chroma` to save the chuncks and their embeddings and to retrive relevant content.
5. LLM `google/flan-t5-base` to be used for the Rag bot.
6. QA chain, accepts LLM and retriever object. The retriever is based on the vectore store, which needed embedding model and chuncks generated from text splitter. The text splitter needed raw text that was loaded using loader.
