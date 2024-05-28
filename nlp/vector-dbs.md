# Vector DBs

General DBs are for structured data (SQL; Postgres), these data storage solutions excel in solving problems for storing and solving structured data problems.

* Read: Value matching and value similarity
* Write: key-value data
* Exampls: relational, graph…

When we want to work with unstructured data this becomes more complicated. An image database may need semantics captured to give the content some context.



What are Vectors?

• A list/array of numbers that represents data in a format that a ML model can process.&#x20;

• For example, in NLP, words or sentences can be transformed into vectors using techniques like Word2Vec, GloVe, or BERT embeddings.&#x20;

• These vectors capture semantic information, making it possible to measure the similarity between different pieces of text.



Vector DBs:

* Storage mechanism for multidimensional vectors
* Data objects are linked and indexed by a vector encoded format
* Write: Objects with N-dimensional vectors
  * (Usually) after going through an embedding model (we’ve trained) to store context and semantics
* Read: vector similarity, filter/search by secondary indices on other properties



Why are Vector Databases Important?

⚬ Rise of AI and Machine Learning

Vector databases are optimized for AI and ML operations, such as similarity searches and handling high-dimensional data, which traditional databases struggle with.

\
⚬ Efficient Similarity Searches

They use advanced indexing and algorithms to perform similarity searches efficiently, essential for recommendation systems and personalized suggestions.

\
⚬ Handling Unstructured Data

Vector databases store and query unstructured data (text, images, videos) by converting it into high-dimensional vectors, crucial for NLP, image recognition, and video analysis.

\
⚬ Scalability and Performance

Designed to scale horizontally, vector databases handle increasing data volumes efficiently, ensuring responsive applications even as datasets grow.

\
⚬ Enhanced Search Capabilities

They enable powerful searches, like finding visually similar images, by comparing feature-representing vectors, surpassing traditional keyword-based searches.



Popular Vector Databases:

• FAISS: Developed by Facebook AI, FAISS is a library for efficient similarity search and clustering of dense vectors.

• Annoy: Developed by Spotify, Annoy (Approximate Nearest Neighbors Oh Yeah) is designed for fast nearest neighbor search.

• Milvus: An open-source vector database that supports various vector search algorithms and is designed for high-performance and scalability.

• Weaviate: An open-source database that integrates seamlessly with machine learning models to store and query data based on vectors.



Weaviate:

Data structures stored as JSON

* Can have multiple properties - its not just vectors
* Types enforced in different ways, such as collections/Chema in Weaviate

Vector generated using vectoriser&#x20;

* Input: Data object
* Output: Vector representation of object

Object and vector indices kept separately

* Weaviate has index & storage LSM tree for objects and a separate vector index



Writing: Embedding and Vectorisers

* Trained embedding model converts tokenised input into vector representation (e.g. text or image data)
* Text example: Models trained on input tokens are the contexts they appear in to learn semantics
* Different vectorizers can be used depending on the usecase
  * Example: OpenAI has their own vectoriser, Coheres embedding tools



Reading: ANN search (Weaviate)

* Objects can be looked up through LSM index
* Vectors searched though vector distances
  * Different methods include cosine similarity, Euclidean distance, etc.
* Vector indexing approaches needed for search optimisation
* Approximate nearest neighbour (ANN) approach is common (KNN would be too computationally expensive to check everything)
  * Trade-off between accuracy and resources
  * Weaviate uses Hierarchical Navigable Small World (HNSW) to build layers for vector search to rule out large groups.&#x20;
    * Builds indexable data networks (of related data) as data is added (?)
    * A bit of a dimensionality reduction technique
    * Time complexity improvement is: logarithmic improvement - Depending on branches on top layer(?). n + k log k log log n - [source](https://stackoverflow.com/questions/37803181/approximate-nearest-neighbors-time-complexity)



Where are these used today?

* Semantic search
  * Image similarity
  * Text similarity
* Retrieval augmented generation (RAG)
  * Providing context to LLMs to provide new information without retraining the entire model



Deep Dive into Vector Databases by Hand, [Link](https://towardsdatascience.com/deep-dive-into-vector-databases-by-hand-e9ab71f54f80)























