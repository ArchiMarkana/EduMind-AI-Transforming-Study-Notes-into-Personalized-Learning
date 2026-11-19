# EduMind AI

EduMind AI is an AI-powered learning assistant that transforms uploaded study
material into useful revision resources. Students can upload notes, generate
summaries, create flashcards and quizzes, and ask questions about their
documents through an AI chat interface.

## Features

- Upload study material in PDF, DOCX, or PPTX format
- Extract text from uploaded documents
- Generate concise, document-grounded summaries
- Generate AI flashcards for active recall
- Generate multiple-choice quizzes with four options
- Ask questions about uploaded study material
- View learning activity and quiz performance through analytics
- Cache generated content to reduce repeated AI requests

## Technology Stack

### Frontend

- HTML
- CSS
- JavaScript
- Chart.js

### Backend

- Python
- Flask
- Flask-CORS

### AI and Document Processing

- Google Gemini API
- PyPDF2
- python-docx
- python-pptx

## Project Structure

```text
internship/
├── backend/
│   ├── app.py
│   ├── test_gemini.py
│   ├── utils/
│   │   ├── gemini_helper.py
│   │   ├── text_extractor.py
│   │   └── upload_handler.py
│   ├── uploads/
│   ├── extracted_text/
│   └── ai_cache/
├── frontend/
│   ├── index.html
│   ├── dashboard.html
│   ├── upload.html
│   ├── summary.html
│   ├── flashcards.html
│   ├── quiz.html
│   ├── chat.html
│   ├── analytics.html
│   └── assets/
├── requirements.txt
└── README.md
```

## Requirements

- Python 3.10 or later
- A Google Gemini API key
- A modern web browser

## Installation

1. Clone or download this repository.

2. Open a terminal in the project directory.

3. Create and activate a virtual environment:

   **Windows PowerShell**

   ```powershell
   python -m venv venv
   .\venv\Scripts\Activate.ps1
   ```

   **macOS/Linux**

   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```

4. Install the Python dependencies:

   ```bash
   pip install -r requirements.txt
   ```

5. Create a file named `.env` inside the `backend` folder:

   ```env
   GEMINI_API_KEY=your_gemini_api_key_here
   ```

   Replace the placeholder with your own Gemini API key. Do not upload the
   `.env` file or expose the API key publicly.

## Running the Application

### Start the backend

Open a terminal in the `backend` folder and run:

```powershell
python app.py
```

The Flask API will run at:

```text
http://127.0.0.1:5000
```

### Start the frontend

Open a second terminal in the `frontend` folder and run:

```powershell
python -m http.server 5500
```

Then open the following address in a browser:

```text
http://127.0.0.1:5500
```

The frontend JavaScript files are configured to communicate with the backend
at `http://127.0.0.1:5000`.

## Application Workflow

1. Open the EduMind AI landing page.
2. Navigate to the upload page.
3. Upload a study document.
4. Wait while the backend extracts the document text.
5. Generate a summary, flashcards, or quiz.
6. Use AI Chat to ask questions about the uploaded document.
7. Review quiz scores and learning activity in Analytics.

## API Endpoints

| Method | Endpoint | Purpose |
|---|---|---|
| GET | `/` | Check whether the backend is running |
| POST | `/upload` | Upload and extract a study document |
| POST | `/process` | Generate a summary |
| POST | `/flashcards` | Generate flashcards |
| POST | `/quiz` | Generate a quiz |
| POST | `/chat` | Ask a question about a document |
| DELETE | `/clear-cache/<text_file>` | Clear cached AI content |

## Important Notes

- Uploaded files are limited to 50 MB by the backend.
- The AI features require a valid `GEMINI_API_KEY`.
- Generated content is stored in the backend cache folders for reuse.
- The current frontend uses local development URLs for the Flask API.
- Do not commit API keys, private documents, or generated personal data to
  GitHub.

## Testing the Gemini Integration

The sample integration test can be run from the `backend` folder:

```powershell
python test_gemini.py
```

This requires a valid Gemini API key in the backend `.env` file.

## Future Enhancements

- Database-backed user accounts
- OCR support for scanned documents
- Spaced-repetition flashcards
- Personalized study recommendations
- Multi-language learning support
- Mobile application support

## License

This project was created as an educational/internship project. Add a license
before redistributing the project publicly.
