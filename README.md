# Whisper Transcription, RAG, and QA System

This project demonstrates a transcription and question-answering system using OpenAI's Whisper model for audio transcription and a Retrieval-Augmented Generation (RAG) model for providing answers to user queries. The system integrates various technologies such as text splitting, embeddings, similarity search, and audio transcription to enhance the user experience.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Technologies Used](#technologies-used)
- [Project Structure](#project-structure)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## Features

- **PDF Download and Processing:** Downloads a PDF from a specified URL and saves it locally if it doesn't already exist.
- **Text Cleaning and Splitting:** Cleans the extracted text, splits it into sentences, and organizes it into sections.
- **Embedding Generation:** Creates embeddings of text chunks using Sentence-Transformers.
- **Similarity Search:** Performs fast similarity searches using FAISS.
- **Question-Answering Interface:** Provides a user-friendly interface with Gradio for asking questions.
- **Audio Transcription:** Transcribes audio inputs to text using the Whisper model and answers queries based on the transcription.

## Installation

To run this project locally, follow these steps:

### Requirements

- Python 3.7 or higher
- CUDA-enabled GPU (optional but recommended for faster processing)

### Steps

1. **Clone the Repository**

    ```bash
    git clone https://github.com/your_username/whisper-qa-system.git
    cd whisper-qa-system
    ```

2. **Create a Virtual Environment**

    It's recommended to use a virtual environment to manage dependencies.

    ```bash
    python -m venv venv
    source venv/bin/activate  # Linux/Mac
    venv\Scripts\activate     # Windows
    ```

3. **Install Required Packages**

    Install the necessary Python packages using `pip`:

    ```bash
    pip install -r requirements.txt
    ```

    *Note:* If you encounter issues with the `requirements.txt`, you can manually install the packages:

    ```bash
    pip install requests sentence-transformers transformers gradio whisper spacy faiss-cpu torch bitsandbytes tqdm pymupdf
    ```

4. **Download the SpaCy Model**

    ```bash
    python -m spacy download en_core_web_sm
    ```

## Usage

Follow these steps to run the project:

1. **Download and Process the PDF**

    The script downloads the specified PDF from a URL and processes it by reading each page and extracting the text.

    ```bash
    python download_and_process_pdf.py
    ```

2. **Start the Question-Answering Interface**

    Launch the Gradio interface to interact with the system.

    ```bash
    python app.py
    ```

    This command will start a local web server and open the interface in your browser. You can record audio or input text to receive answers to your queries.

## Technologies Used

- **Python:** Programming language.
- **Requests:** Making HTTP requests.
- **SpaCy:** Natural Language Processing.
- **Sentence-Transformers:** Generating text embeddings.
- **FAISS:** Performing similarity searches.
- **Torch:** Deep learning library.
- **Transformers:** Hugging Face models.
- **Gradio:** Building user interfaces.
- **Whisper:** Audio transcription.
- **BitsAndBytes:** Model quantization.
- **FitZ (PyMuPDF):** PDF processing.

## Troubleshooting

- **Whisper Model Not Loading:**
  - Ensure you have a stable internet connection to download the model.
  - Verify that the `whisper` library is correctly installed.

- **CUDA Errors:**
  - Make sure your GPU drivers are up to date.
  - Check if PyTorch is installed with CUDA support: `torch.cuda.is_available()`

- **Missing Dependencies:**
  - Re-run `pip install -r requirements.txt` to install any missing packages.

## Contributing

If you'd like to contribute to this project, please follow these steps:

1. **Fork** this repository on GitHub.
2. **Create a Branch** for your feature: `git checkout -b new-feature`.
3. **Commit** your changes: `git commit -m 'Add new feature'`.
4. **Push** the branch to your fork: `git push origin new-feature`.
5. **Open a Pull Request** on GitHub.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

---

*This project is developed for learning and research purposes in the fields of natural language processing and machine learning.*

## Future Improvements

- **Multilingual Support:** Extend the system to handle multiple languages for transcription and QA.
- **Enhanced UI/UX:** Improve the Gradio interface with more interactive elements and better design.
- **Advanced Query Processing:** Implement more sophisticated query understanding and context management.
- **Scalability:** Optimize the system to handle larger PDFs and more concurrent users.
- 
