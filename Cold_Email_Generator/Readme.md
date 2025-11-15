# Cold Email Generator

A **Cold Email Generator** app built with **Streamlit**, **LangChain**, **ChatGroq**, and **Chroma DB**. The app automatically generates personalized cold emails for job applicants based on scraped job descriptions and matching skills from a portfolio dataset.

## Features

* **Job Description Extraction**: Extract job details (e.g., skills, experience) from job posting URLs.
* **Portfolio Skill Matching**: Match job requirements with a student portfolio dataset using Chroma DB.
* **Cold Email Generation**: Automatically generate cold emails for job applicants, referencing relevant portfolio links.

## Technologies

* **Streamlit**: Used for the web interface.
* **LangChain**: A framework for working with language models and document processing.
* **ChatGroq LLM**: For extracting job details and generating emails.
* **Chroma DB**: A vector database for querying student portfolios.
* **Python**: The core language for implementing the app.
* **dotenv**: Used to manage environment variables for API keys.

## Installation

1. **Clone the repository**:

   ```bash
   git clone https://huggingface.co/spaces/Ajay07pandey/Cold_Email_generator
   ```

2. **Install dependencies**:

   ```bash
   pip install -r requirements.txt
   ```

3. **Set up Hugging Face API Key**:

   * Go to your Hugging Face Space → Settings → Secrets.
   * Add a secret named `GROQ_API_KEY` with your **Groq API key**.

4. **Place the student portfolio CSV** in the `Cold_email_generator/resource/` directory.

5. **Run the Streamlit app**:

   ```bash
   streamlit run src/main.py
   ```

## File Structure

* **`src/portfolio.py`**: Defines the `Portfolio` class, which loads student portfolio data and stores it in Chroma DB for skill-based matching.
* **`src/chains.py`**: Contains the `Chain` class for interacting with the **ChatGroq LLM**. It extracts job descriptions and generates cold emails.
* **`src/main.py`**: The main Streamlit application that handles user input, job scraping, portfolio querying, and email generation.
* **`src/utils.py`**: Contains the `clean_text` function that processes and cleans the raw text extracted from job postings.
* **`Cold_email_generator/resource/student_portfolios.csv`**: A CSV file containing student portfolios, their tech stacks, and portfolio links.

## How It Works

1. **User Input**: The user provides a URL for a job posting.
2. **Job Extraction**: The app scrapes the URL for job details using LangChain's `WebBaseLoader` and processes the text.
3. **Skill Matching**: The app queries the portfolio dataset for relevant student profiles based on required job skills.
4. **Cold Email Generation**: The app generates a personalized cold email, referencing the relevant portfolios and skills.

## Contributing

Feel free to fork the repository, open issues, or submit pull requests. Contributions are welcome!

## License

This project is licensed under the MIT License.
