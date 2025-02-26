# TEXT-SUMMARIZATION-TOOL

*COMPANY* : CODTECH IT SOLUTIONS

*NAME* : SOUMIK BHUNIA

*INTERN ID* :CT6WWQB

*DOMAIN* : ARTIFICIAL INTELLIGENCE

*DURATION* : 6 WEEKS

*MENTOR* : NEELA SANTOH

* CODE DESCRIPTION*

This Python script performs extractive text summarization using natural language processing (NLP) techniques, primarily leveraging cosine similarity and the PageRank algorithm. The script reads a text file, processes it to extract meaningful sentences, computes similarity between sentences, and ranks them to generate a concise summary.

The script begins by importing necessary libraries, including the Natural Language Toolkit (NLTK) for text processing, NumPy for numerical computations, and NetworkX for graph-based algorithms. The NLTK library is used to handle stopwords and sentence tokenization, while the cosine distance function helps measure the similarity between two sentences. NetworkX is utilized to implement the PageRank algorithm, which plays a crucial role in determining the most important sentences for the summary.

To process the text, the function read_article(file_name) is defined, which takes a text file as input and extracts sentences from it. The function reads the file, splits it into sentences using the ". " delimiter, and further splits each sentence into words while removing non-alphabetic characters. The result is a list where each element represents a sentence as a list of words. This function ensures that the text is properly formatted before similarity calculations are performed.

The script then defines the sentence_similarity(sent1, sent2, stopwords=None) function, which calculates the similarity between two sentences based on cosine similarity. It first converts both sentences to lowercase for uniformity, then creates a list of unique words from both sentences. Using this unique word set, it constructs word frequency vectors for each sentence and calculates the cosine similarity score. This score represents how similar two sentences are, which is later used to build the similarity matrix.

Once the sentence similarity function is established, the script defines gen_sim_matrix(sentences, stop_words), which generates an N x N similarity matrix, where N is the number of sentences in the input text. This matrix stores the similarity scores between every pair of sentences. The function initializes the matrix with zeros and iterates through each sentence pair, calling sentence_similarity() to populate the matrix with similarity values. This matrix serves as the foundation for ranking sentences based on their relevance.

To generate the summary, the script implements the generate_summary(file_name, top_n=5) function. This function begins by retrieving a list of English stopwords to filter out commonly used words that do not contribute much meaning. It then reads the text file using read_article(), extracts the sentences, and constructs the similarity matrix using gen_sim_matrix(). The script then creates a graph where each sentence represents a node, and the edges between nodes correspond to the similarity scores from the matrix. By applying the PageRank algorithm to this graph, the script ranks sentences based on their importance within the text.

After computing PageRank scores, the function sorts the sentences in descending order of importance and selects the top N sentences to form the final summary. These sentences are then joined together and printed as the output. The summary consists of the most relevant and informative sentences extracted from the original text, providing a concise and meaningful representation of the document.

For example, if the input text file contains information about Microsoft, such as its history, products, and recent investments, the summarization function might generate an output that highlights key points like "Microsoft is a leading technology company" and "Microsoft is investing in AI and cloud computing." This extractive approach ensures that the summary is composed of actual sentences from the original document rather than a rephrased or generated summary.

This script is particularly useful for summarizing large documents, news articles, and research papers. By automating the summarization process, it helps save time and effort when analyzing lengthy texts. The approach is unsupervised, meaning it does not require labeled training data, making it applicable to a wide range of text summarization tasks. The use of cosine similarity ensures that only semantically relevant sentences are considered, while PageRank provides a robust method for ranking the most important information.

In real-world applications, this method can be used for summarizing news articles, research papers, and legal documents. Businesses can leverage it to extract key insights from reports, while students and researchers can use it to quickly grasp the main ideas of lengthy academic papers. The combination of NLP and graph-based ranking techniques makes this summarization approach both efficient and effective.

Overall, the script provides a straightforward yet powerful implementation of text summarization using NLP and graph algorithms. By utilizing sentence similarity, a similarity matrix, and PageRank, it effectively extracts the most informative sentences from a document and presents them in a concise manner. This makes it a valuable tool for anyone dealing with large amounts of textual data, offering a way to quickly understand and summarize content without losing important details.
