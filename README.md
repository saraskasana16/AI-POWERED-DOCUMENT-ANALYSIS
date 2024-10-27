PDF Processing and Summarization Assignment

  ##Overview
  
In this project, I worked on extracting text from a bunch of PDFs, creating summaries, and pulling out important keywords. All of this information, including the summaries and keywords, gets saved in MongoDB. The goal was to handle a lot of PDFs quickly and efficiently.

Steps I Followed
1. PDF Extraction:

First, I used Python’s PyPDF2 to read each PDF and pull out the text.
I saved the extracted data, which includes the file name, file size, path, and the full text, into MongoDB for each PDF.

2. Parallel Processing:

To make things faster, I processed all PDFs at the same time using Python's ThreadPoolExecutor, which helped reduce the time it took to extract data.

3. Text Summarization:

I used a custom approach to summarize the text:
Cleaned the text by removing numbers, special characters, and stopwords.
Ranked sentences based on how often words appeared and their positions in the text.
Boosted the scores of sentences that mentioned important names, places, and organizations using Named Entity Recognition (NER).
Used TextRank to create a more detailed ranking, making sure the summaries were as relevant as possible.

4. Keyword Extraction:

Extracted keywords with TfidfVectorizer, focusing on picking the most relevant words for each document.

5. MongoDB Update:

Once the summaries and keywords were ready, I updated each document in MongoDB to include these new fields.

6. Error Handling:

Built-in error handling skips any problematic PDFs
Technology Used

Python Libraries:
-- PyPDF2 for pulling text from PDFs.
-- NLTK for breaking down the text and handling stopwords.
-- spaCy for finding important names and places with NER.
-- Scikit-learn for TfidfVectorizer and cosine similarity.
-- pymongo for saving and updating documents in MongoDB.

Concurrency:
Used ThreadPoolExecutor to process all PDFs at the same time, making things way faster.

Database:
MongoDB for storing and updating the extracted text, summaries, and keywords.
