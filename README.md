# Doc2Graph

# Problem Statement:
The primary challenge lies in developing an effective method to convert unstructured PDF documents into structured knowledge representations. This involves parsing textual content, identifying key entities and relationships, and constructing a coherent knowledge graph that encapsulates the semantic essence of the document. Additionally, the system must facilitate efficient summarization, and accurate query answering by parsing the KG.


# Proposed Solution:
Our proposed solution aims to address the challenge of extracting meaningful insights from PDF documents by leveraging a two-step process: parsing the PDF document to extract textual content and constructing a knowledge graph for summarization and querying purposes.

# 1.Parsing PDF Documents:
To begin, we will implement a PDF parsing module capable of extracting textual content from PDF documents. This is implemented using the existing “PyMuPDF” library in python to extract the raw data from the document while still preserving the structural layout. 
# 2.Textual Data Processing: 
Once the textual content is extracted, we will preprocess the text to remove noise.This preprocessing step involves techniques such as tokenization, stop-word removal, and lemmatization to enhance the quality of the extracted text.
# 3.Entities and Relation Identification: 
From the obtained block of processed textual data we will then extract the relations and entities (identified as head, type and tail) using the “REBEL” (RElation Extraction By End-to-end Language generation) model.
# 4. More about REBEL:
REBEL is based on the BART (Bidirectional and Autoregressive Transformers for Pre-training) architecture pre-trained on a massive dataset of text.
It treats relation triplets (subject, relation, object) as a sequence of text and uses the seq2seq model to directly generate these triplets from the input text.
REBEL: Relation Extraction By End-to-end Language generation (aclanthology.org)
# 5.Knowledge Graph Construction: 
With the extracted entities and relations in hand we can generate the RDF triples which helps us to construct the KG in Neo4j Graph DB.
Summarization and Querying: Once the KG is constructed, it can be utilized for summarizing content and answering user queries submitted in natural language.


