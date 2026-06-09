Here’s a clean, production-ready README.md for your project. You can directly paste this into your repo.

⚡ Data Analyst Agent (TDS Project 2)

An AI-powered data analysis system using FastAPI + LangChain + Google Gemini that can:

Analyze datasets (CSV, Excel, JSON, Parquet)
Scrape web data automatically
Generate Python-based insights
Produce charts (returned as base64 images)
Answer multiple analytical questions in one request
🚀 Features
🤖 AI-powered data analysis using Google Gemini
📊 Automatic EDA (correlations, trends, summaries)
🌐 Web scraping fallback when dataset is not provided
📈 Visualization support (Matplotlib + Seaborn)
⚡ FastAPI backend with async processing
🧠 LangChain tool-calling agent
🖼 Base64 image generation for plots (<100KB optimized)
📂 Project Structure
app.py              # Main FastAPI backend
index.html          # Frontend UI
requirements.txt    # Python dependencies
.env                # API keys (NOT committed)
⚙️ Installation Guide
1️⃣ Clone the repository
git clone https://github.com/22f1001281/tds-project2.git
cd tds-project2
2️⃣ Create virtual environment
python3 -m venv venv
source venv/bin/activate   # Linux / WSL
venv\Scripts\activate      # Windows
3️⃣ Install dependencies
pip install -r requirements.txt
4️⃣ Setup environment variables

Create a .env file in the root directory:

GEMINI_API_KEY=your_google_gemini_api_key
LLM_TIMEOUT_SECONDS=240
5️⃣ Run the server
python -m uvicorn app:app --host 0.0.0.0 --port 8000 --reload
6️⃣ Open in browser
http://127.0.0.1:8000
📥 API Endpoints
🟢 GET /
Loads frontend UI
🟡 POST /api

Upload dataset + questions file

Form Data:

questions_file → required (.txt)
data_file → optional (csv/xlsx/json/parquet)

Response:

{
  "Question 1": "Answer",
  "Question 2": "Answer"
}
🔵 GET /summary

System diagnostics (LLM, network, system health)

📊 Supported File Formats
Type	Extensions
CSV	.csv
Excel	.xlsx, .xls
JSON	.json
Parquet	.parquet
Text	.txt
🧠 How It Works
User uploads dataset + questions
FastAPI receives request
LangChain agent:
Decides whether to use dataset or web scraping
Python code is generated dynamically
Code is executed in sandbox
Results returned as JSON
🌐 Web Scraping Mode

If no dataset is provided:

Agent automatically calls scrape_url_to_dataframe()
Extracts tables or text from web pages
Converts into DataFrame for analysis
📈 Visualization System

All plots:

Generated using Matplotlib/Seaborn
Converted to Base64 images
Automatically compressed to <100KB
🔐 Security Notes
API keys stored in .env
No external storage of uploaded files
Execution happens locally
Temporary files auto-deleted
🧪 Example Questions
What is the correlation between Sales and Profit?
Which region has highest revenue?
Plot sales distribution
Find missing values in dataset
Show trend over time
🛠 Tech Stack
FastAPI ⚡
LangChain 🧠
Google Gemini 🤖
Pandas / NumPy 📊
Matplotlib / Seaborn 🎨
Python 3.10+
🚀 Run Troubleshooting
❌ Port already in use
pkill -f uvicorn
❌ No API key error
export GEMINI_API_KEY="your_key"
❌ Module not found
pip install -r requirements.txt
📜 License

MIT License © 2026

👨‍💻 Author

Built for TDS Project 2
