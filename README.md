# Semantic Text Search with Sentence Embeddings and FAISS

## 🧠 Vector Search Summary
Vector search is a method for retrieving information based on **semantic meaning** instead of exact keyword matching. Text is first converted into high-dimensional numerical vectors (called **embeddings**) using a model like `all-MiniLM-L6-v2`. These embeddings capture the meaning of the text.

To find similar text, we compare these vectors using a distance metric (like cosine or Euclidean distance). FAISS is a library that efficiently indexes and searches through these embeddings, allowing fast retrieval of the most relevant results. This approach is commonly used in semantic search, question-answering, and recommendation systems.

## 💻 Google Colab Notebook
You can view and run the full notebook on Google Colab here:  
👉 [Click to open in Colab](https://colab.research.google.com/drive/1T6E8e8IvdVs26tHCRtM2T6Yc64yTNWvJ?usp=sharing)

## 👥 Team Information
- **Team Name**: Neural Nets
- **Collaborators**:
  - Shrushti (shrushti.narayanaswamy@stud.uni-bamberg.de)
  - Huzaifa (huzaifa.aneel@stud.uni-bamberg.de)
  - Sharjeel (muhammad-sharjeel-iqbal.joyia@stud.uni-bamberg.de)

## FAISS Search Results: Observations

In this experiment, I used FAISS to perform similarity search over a set of text chunks using three different versions of the same query about the Eiffel Tower.

### What I Observed:
- All three queries returned the same most relevant chunk:  
  **"The Eiffel Tower is located in Paris, France."**
- The top result had a **very low distance** (meaning high similarity), even though the query wording changed.
- Sometimes the 2nd or 3rd ranked results included loosely related topics (like other landmarks or cities), showing how FAISS also finds **semantically nearby concepts**.

### Why This Happened:
The sentence-transformers model captures **semantic meaning**, not just keywords. So, even when the wording changed, the query embedding still pointed to the same idea — "Eiffel Tower's location."

FAISS efficiently searched the index using vector distances, and returned the most semantically similar chunks, making it ideal for applications like question-answering or FAQ search.
