# ML Resume Screening System

This project is a web-based application that uses Natural Language Processing (NLP) and Machine Learning to automate the resume screening process. It helps recruiters and hiring managers to quickly analyze resumes, categorize them into predefined job roles, and get suitable job recommendations based on the candidate's skills and experience. The system can extract key information such as name, email, phone number, skills, and education from an uploaded resume.

## 🚀 Key Features

-   **Intelligent Resume Parsing:** Automatically extracts text from both **PDF** and **TXT** file formats using `pdfplumber`.
-   **Information Extraction:** Utilizes `spaCy` for Named Entity Recognition (NER) to identify and extract:
    -   Candidate Name
    -   Email Address
    -   Phone Number
    -   Skills
    -   Education
-   **AI-Powered Categorization:** Employs a pre-trained **Random Forest Classifier** to classify resumes into one of 25 distinct job categories (e.g., "Data Science," "HR," "Web Designing").
-   **Job Recommendation:** Suggests the most suitable job role for the candidate using a second, specialized Random Forest model.
-   **User-Friendly Interface:** A clean and modern web interface built with Flask for easy resume uploading and clear visualization of the analysis results.

## 🛠️ Technology Stack

-   **Backend:** **Python** with **Flask** Framework
-   **Machine Learning:** **Scikit-learn**, **Pandas**
-   **NLP Libraries:** **NLTK**, **Spacy** (`en_core_web_sm`)
-   **PDF Processing:** **pdfplumber**
-   **Frontend:** **HTML**, **CSS**, **JavaScript**
-   **ML Models:**
    -   TF-IDF Vectorizer for natural language feature extraction.
    -   Random Forest Classifier for classification tasks.


## 📦 Getting Started

Follow these instructions to set up and run the project on your local machine.

### Prerequisites

Make sure you have the following installed:
-   Python 3.8+
-   `pip` (Python package installer)

### Installation & Setup

1.  **Clone the Repository**
    ```bash
    git clone [https://github.com/your-username/your-repository-name.git](https://github.com/your-username/your-repository-name.git)
    cd your-repository-name
    ```

2.  **Create and Activate a Virtual Environment**
    -   **Windows:**
        ```bash
        python -m venv venv
        .\venv\Scripts\activate
        ```
    -   **macOS / Linux:**
        ```bash
        python3 -m venv venv
        source venv/bin/activate
        ```

3.  **Install Required Dependencies**
    All the necessary packages are listed in `requirements.txt`. Install them using pip:
    ```bash
    pip install -r requirements.txt
    ```

4.  **Download Spacy English Model**
    The project uses a Spacy model for entity recognition which needs to be downloaded.
    ```bash
    python -m spacy download en_core_web_sm
    ```

### Running the Application

1.  **Start the Flask Server**
    Once the setup is complete, run the following command in your terminal:
    ```bash
    python app.py
    ```

2.  **Access the Application**
    Open your web browser and navigate to:
    ```
    [http://122.0.0.1:5000/](http://122.0.0.1:5000/)
    ```

## Usage

1.  Navigate to the homepage of the application.
2.  Click on the **"Click or drag your file here"** area to select a resume file (`.pdf` or `.txt`) from your computer.
3.  Once the file is selected, its name will appear in the upload box.
4.  Click the **"Analyze Resume"** button to submit it for processing.
5.  The application will process the resume and display the following results directly on the page:
    -   Predicted Job Category
    -   Recommended Job Role
    -   Extracted information like Name, Phone, Email, Skills, and Education.

## 📁 Project File Structure

├── app.py                            # Main Flask application logic
├── requirements.txt                  # Python dependencies for pip
├── templates/
│   └── resume.html                   # HTML template for the user interface
├── rf_classifier_categorization.pkl  # Trained model for resume categorization
├── tfidf_vectorizer_categorization.pkl # TF-IDF vectorizer for categorization
├── rf_classifier_job_recommendation.pkl # Trained model for job recommendation
├── tfidf_vectorizer_job_recommendation.pkl # TF-IDF vectorizer for recommendation
└── README.md       
.
