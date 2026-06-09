

```md
# ⚡ Data Analyst Agent (FastAPI + Gemini + LangChain)

An AI-powered data analysis assistant that can:
- Answer natural language questions on datasets
- Scrape web data from URLs
- Generate Python code automatically via LLM (Google Gemini)
- Produce visualizations (Matplotlib/Seaborn)
- Return structured JSON outputs via API

---

## 🚀 Features

- 🤖 Gemini AI-powered code generation
- 📊 Automatic data analysis (Pandas/Numpy)
- 🌐 Web scraping tool (URL → DataFrame)
- 📈 Plot generation (Base64 images <100KB)
- ⚙️ FastAPI backend
- 🧠 LangChain agent orchestration
- 📂 Supports CSV, Excel, JSON, Parquet
- 🖼 Image input support (optional)

---

## 📁 Project Structure

```

├── app.py
├── index.html
├── requirements.txt
├── .env
└── README.md

````

---

## 🧰 Requirements

- Python 3.10+
- pip
- virtualenv (recommended)
- Linux / WSL / macOS / Windows

---

## 🔑 Setup Instructions

### 1. Clone Repository

```bash
git clone https://github.com/<your-username>/tds-project2.git
cd tds-project2
````

---

### 2. Create Virtual Environment

```bash
python -m venv venv
source venv/bin/activate   # Linux / Mac
# OR
venv\Scripts\activate      # Windows
```

---

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

### 4. Set Environment Variables

Create a `.env` file in the project root:

```env
GEMINI_API_KEY=your_google_gemini_api_key_here
LLM_TIMEOUT_SECONDS=240
```

👉 Get API key from:
[https://aistudio.google.com/app/apikey](https://aistudio.google.com/app/apikey)

---

## ▶️ Run the Server

### Option 1 (Recommended)

```bash
uvicorn app:app --reload
```

### Option 2 (Explicit host)

```bash
uvicorn app:app --host 0.0.0.0 --port 8000 --reload
```

---

## 🌐 Open in Browser

```
http://127.0.0.1:8000/
```

---

## 📡 API Endpoints

### 1. Frontend

```
GET /
```

---

### 2. Analysis API (Main)

```
POST /api
```

### Input:

* `questions_file` → required (.txt file)
* `data_file` → optional dataset file

### Output:

```json
{
  "Question 1": "Answer",
  "Question 2": "Answer"
}
```

---

### 3. Health Check

```
GET /api
```

---

### 4. Diagnostics

```
GET /summary
```

Shows:

* System info
* Network status
* LLM key checks
* Package info

---

## 📂 Supported File Types

### Dataset Upload

* CSV `.csv`
* Excel `.xlsx`, `.xls`
* JSON `.json`
* Parquet `.parquet`
* Images `.png`, `.jpg` (optional)

### Questions File

* Plain text `.txt`

---

## 🧠 How It Works

1. User uploads:

   * dataset (optional)
   * question file (required)

2. LLM (Gemini) generates Python code:

   * Uses Pandas / NumPy
   * Optionally scrapes web data

3. Code executed safely in sandbox

4. Results returned as JSON

---

## 🔐 Environment Variables

| Variable            | Description           |
| ------------------- | --------------------- |
| GEMINI_API_KEY      | Google Gemini API key |
| LLM_TIMEOUT_SECONDS | Execution timeout     |

---

## 🛠 Troubleshooting

### ❌ Port already in use

```bash
lsof -i :8000
kill -9 <PID>
```

---

### ❌ No Gemini API Key error

```bash
export GEMINI_API_KEY="your_key"
```

---

### ❌ App not opening in browser

Use:

```
http://127.0.0.1:8000
```

NOT localhost if WSL/network blocks it.

---

### ❌ Uvicorn keeps stopping

Make sure no old process is running:

```bash
ps aux | grep uvicorn
kill -9 <PID>
```

---

## 📊 Example Questions File

```txt
What is the average value of column A?
Which category has the highest sales?
Plot correlation between X and Y
Find missing values percentage
```

---

## 🎯 Example Dataset Ideas

You can use:

* Titanic dataset
* Sales dataset (CSV)
* Netflix titles dataset
* Weather data
* Any Kaggle dataset

---

## 📜 License

MIT License

---

## 👨‍💻 Author

Built with FastAPI + LangChain + Google Gemini

```
