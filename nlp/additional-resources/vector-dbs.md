# Vector DBs

General DBs are for structured data (SQL; Postgres), these data storage solutions excel in solving problems for storing and solving structured data problems.

* Read: Value matching and value similarity
* Write: key-value data
* Exampls: relational, graph…

When we want to work with unstructured data this becomes more complicated. An image database may need semantics captured to give the content some context.



Vector DBs:

* Storage mechanism for multidimensional vectors
* Data objects are linked and indexed by a vector encoded format
* Write: Objects with N-dimensional vectors
  * (Usually) after going through an embedding model (we’ve trained) to store context and semantics
* Read: vector similarity, filter/search by secondary indices on other properties

ChromeDB, mongoDB(?), …



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
    * Time complexity improvement is: logarithmic improvement - log n? Depending on branches on top layer. N + k log k log n - LINK]

Where are these used today?

* Semantic search
  * Image similarity
  * Text similarity
* Retrieval augmented generation (RAG)
  * Providing context to LLMs to provide new information without retraining the entire model























