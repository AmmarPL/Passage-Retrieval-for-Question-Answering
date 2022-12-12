# Passage-Retrieval-for-Question-Answering

The passage_retrieval.ipynb file contains three different passage retrieval methods:
1) BM25 (Sparse Vectors)
2) Dense Passagae Retrieval (DPR)
3) DPR with cross encoder reranking

### BM25
BM25 (Best Match 25) is a function that calculates the relevance of a document to a given text query. It is a refinement of the TFIDF score. In TFIDF, a term frequency function is multiplied by an inverse document frequency function. In other words, it rewards the term occurring more frequently in the document and penalizes if the term occurs in a large number of documents. BM25 improves TFIDF by considering the length of the document and adding a saturation rate control parameter.

### Dense Passage Retrieval
Refer the work by Karpukhin et al for more details, https://arxiv.org/abs/2004.04906.
Previous methods for passage retrieval have used techniques like TFIDF and BM25. These methods query the documents using inverted indices to choose the documents with the highest score based on the number of matching terms. They can be considered to be sparse vector representations of the questions and answers. These methods fail in retrieving documents that have relevant text but in a paraphrased form of our query text. This paper focuses on creating dense representations of questions and answers so we can use similarity between vectors to choose passages.

### DPR with cross encoder reranking
Cross encoders can give a score indicating the relevance between a passsage and query. This makes them ideal for reranking passages that have been retrieved using passage retrieval method like DPR or BM25. Here, I have reranked passages retrieved using DPR.

## Question Answering
Passage retrieval can be used to improve question answering, by giving both the question and a retrieved passage as input to the summarization model.
