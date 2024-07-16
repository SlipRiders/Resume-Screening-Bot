# Resume Screening RAG Bot

## Introduction

The research aims to present a POC of an LLM chatbot that can assist hiring managers in the resume screening process. The assistant is a cost-efficient, user-friendly, and more effective alternative to the conventional keyword-based screening methods. Powered by state-of-the-art LLMs, it can handle unstructured and complex natural language data in job descriptions/resumes while performing high-level tasks as effectively as a human recruiter.  

The core design of the assistant involves the use of hybrid retrieval methods to augment the LLM agent with suitable resumes as context:

1. Adaptive Retrieval:
   - Similarity-based retrieval: When a job description is provided, the retriever utilizes RAG/RAG Fusion to search for similar resumes to narrow the pool of applicants to the most relevant profiles.
   - Keyword-based retrieval: When applicant information is provided (IDs), the retriever can also retrieve additional information about specified candidates.
3. Generation: The retrieved resumes are then used to augment the LLM generator so it is conditioned on the data of the retrieved applicants. The generator can then be used for further downstream tasks like cross-comparisons, analysis, summarization, or decision-making.

#### Why resume screening?

Despite the increasingly large volume of applicants each year, there are limited tools that can assist the screening process effectively and reliably. Existing methods often revolve around keyword-based approaches, which cannot accurately handle the complexity of natural language in human-written documents. Because of this, there is a clear opportunity to integrate LLM-based methods into this domain, which the project aims to address. 

#### Why RAG/RAG Fusion? 

RAG-like frameworks are great tools to enhance the reliability of chatbots. Overall, RAG aims to provide an external knowledge base for LLM agents, allowing them to receive additional context relevant to user queries. This increases the relevance and accuracy of the generated answers, which is especially important in data-intensive environments such as the recruitment domain.

On the other hand, RAG Fusion is effective in addressing complex and ambiguous human-written prompts. While the LLM generator can handle this problem effectively, the retriever may struggle to find relevant documents when presented with multifaceted queries. Therefore, this technique can be used to improve resume retrieval quality when the system receives complex job descriptions (which are quite common in hiring).
