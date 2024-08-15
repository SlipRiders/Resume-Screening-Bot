# Resume Screening RAG Bot
Xiaoyang Chen 002683914 && Swini Rodrigues 002755764              
[Hugging face model](https://huggingface.co/cxyzxc/7375-l6v2-dev1)           
[Streamlit Demo](https://info7374screenbot-bpkdynmhvwvdurqzeywcw8.streamlit.app/)           
[Youtube Link](https://youtu.be/G8PyPWzC-LU)
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

# Setup Instructions

This guide will walk you through setting up the environment and installing the necessary dependencies to run the project.

## 1. Prerequisites

Before you begin, ensure you have the following tools installed:
- [Python 3.8 or higher](https://www.python.org/downloads/)
- [pip](https://pip.pypa.io/en/stable/installation/)
- OpenAI API key

## 2. Create a Virtual Environment

It is recommended to create a virtual environment for the project to manage dependencies and avoid conflicts with other projects.

1. Open a terminal or command prompt.
2. Navigate to your project directory.
3. Create a virtual environment:

    ```sh
    python -m venv venv
    ```

4. Activate the virtual environment:

    - On Windows:

        ```sh
        venv\Scripts\activate
        ```

    - On macOS and Linux:

        ```sh
        source venv/bin/activate
        ```

## 3. Install Dependencies

1. Clone the repository:
    ```bash
    git clone [https://github.com/SlipRiders/INFO7375-RAG-Assignment.git](https://github.com/SlipRiders/Resume-Screening-Bot.git)
    cd Resume-Screening-Bot
    ```
Once the virtual environment is activated, install the project dependencies using the `requirements.txt` file.

2. Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```

3. Set up your API keys:
    - Create a `.env` file in the project root directory.
    - Add your OpenAI API keys to the `.env` file:
      ```bash
      OPENAI_API_KEY=your_openai_api_key
      ```

## 4. Run the Project
With all dependencies installed, you can now run the project.
```sh
cd demo
streamlit run interface.py
```
