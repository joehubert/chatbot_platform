# Chatbot Platform Requirements


* Will be reusable (with appropriate modifications) by different organizations.
* Will be launched as a website chatbot (javascript widgit?).
* Will utilize RAG in order to support company product information, etc.
* Will support multiple layers of logic and processing including:
    * Rate limiting using Redis for token bucket approach
    * Relevance filtering
    * Searching cache for similar questions
    * Prompt handling for appropriate node/model
        * Difficulty of prompt?
        * Type of question
        * Requires RAG?
    * Decision node to see if question has been answered, progressive enhancement if not
    * Will utilize an authentication node if necessary (asking question about person's account)
        * Chatbot will send one-time token to mobile number or email address on file; authenticate user if they enter the correct number
* Will use state management and conversation management appropriately
* Models will be pluggable based, configured in .env file
* Will leverage LangGraph to direct the logic flow
* Will record the metrics related to each question in a standard database
    * Summary of propmt
    * Summary of resolution response
    * Number of attempts
    * Complexity of question
* Can use LangSmith for detailed auditing and tracing
* Will use a pluggable vector database for RAG, etc.
* Components will be deployed in separate docker containers as appropriate (Redis, Relational database, vector database, etc)
