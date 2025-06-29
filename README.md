# InsureAI Assistant 🤖

An intelligent AI-powered insurance assistant that helps users understand their insurance policies by analyzing uploaded PDF documents and answering questions in real-time.

## ✨ Features

- **📄 PDF Document Analysis**: Upload and extract text from insurance policy PDFs
- **🤖 AI-Powered Q&A**: Get intelligent answers about your insurance policy using Groq's Llama3-70B model
- **💬 Interactive Chat Interface**: Modern, responsive web interface for seamless interaction
- **🔒 Secure File Handling**: Safe file upload and processing with proper validation
- **📱 Mobile-Friendly**: Responsive design that works on all devices
- **⚡ Real-time Responses**: Fast, accurate answers to insurance-related questions

## 🚀 Quick Start

### Prerequisites

- Python 3.8 or higher
- Groq API key (or OpenAI API key)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/anubhavsingh2004/InsureAI_Assistant.git
   cd InsureAI_Assistant
   ```

2. **Create and activate virtual environment**
   ```bash
   python -m venv venv
   
   # On Windows
   venv\Scripts\activate
   
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables**
   
   Create a `.env` file in the root directory:
   ```env
   GROQ_API_KEY=your_groq_api_key_here
   
   ```

5. **Run the application**
   ```bash
   python app.py
   ```

6. **Access the application**
   
   Open your browser and navigate to `http://localhost:5000`

## 📖 Usage Guide

### 1. Upload Insurance Policy
- Click the "Choose File" button in the chat interface
- Select your insurance policy PDF document
- The system will automatically extract and process the text

### 2. Ask Questions
- Type your insurance-related questions in the chat input
- Examples:
  - "What is my deductible?"
  - "What does my policy cover?"
  - "What are the exclusions?"
  - "How do I file a claim?"

### 3. Get Intelligent Answers
- The AI will analyze your policy document and provide accurate, contextual answers
- Responses are formatted with clear headings, bullet points, and emojis for easy reading

## 🏗️ Project Structure

```
InsureAI_Assistant/
├── agent/
│   ├── doc_parser.py      # PDF text extraction
│   └── support_bot.py     # AI response generation
├── data/
│   ├── faqs.json          # FAQ data
│   └── sample_insurance_policy.pdf
├── static/
│   ├── script.js          # Frontend JavaScript
│   └── style.css          # Styling
├── templates/
│   └── index.html         # Main web interface
├── app.py                 # Flask application
├── wsgi.py               # WSGI entry point
├── requirements.txt      # Python dependencies
└── README.md            # This file
```

## 🔧 Configuration

### API Configuration

The application supports both Groq and OpenAI APIs:

**For Groq (Recommended):**
```python
# In agent/support_bot.py
API_KEY = os.getenv("GROQ_API_KEY")
# Model: llama3-70b-8192
```

### Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `GROQ_API_KEY` | Your Groq API key | Yes (if using Groq) |
| `PORT` | Server port (default: 5000) | No |

## 🌐 API Endpoints

### POST `/upload`
Upload and process an insurance policy PDF.

**Request:**
- Content-Type: `multipart/form-data`
- Body: PDF file

**Response:**
```json
{
  "status": "success",
  "message": "filename.pdf uploaded and processed successfully."
}
```

### POST `/ask`
Ask a question about the uploaded insurance policy.

**Request:**
```json
{
  "query": "What is my deductible?"
}
```

**Response:**
```json
{
  "response": "Based on your policy, your deductible is..."
}
```

## 🚀 Deployment

### Local Development
```bash
python app.py
```

## 🛠️ Dependencies

- **Flask** (3.1.1) - Web framework
- **PyMuPDF** (1.24.3) - PDF text extraction
- **requests** (2.32.4) - HTTP client
- **python-dotenv** (1.1.1) - Environment variable management

