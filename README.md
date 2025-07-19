
# 🚀 AI LinkedIn Profile Coach

An interactive, AI-powered chat system designed to help users optimize their LinkedIn profiles, analyze job fit, and receive personalized career guidance. This application leverages a **multi-agent architecture built with LangGraph** to provide a seamless, conversational experience with **persistent memory** across sessions.

---

## ✨ Key Features

- **Interactive Chat Interface**: A user-friendly UI built with **Streamlit** for a natural, conversational flow.
- **Live Profile Scraping**: Utilizes **Apify** to scrape real-time LinkedIn profile data for accurate analysis.
- **Multi-Agent System**: A sophisticated backend where different AI "agents" handle specific tasks:
  - 🧠 **Profile Analysis**: Get a comprehensive critique of your profile's strengths and weaknesses.
  - 🎯 **Job Fit Analysis**: Compare your profile to industry-standard job descriptions with a match score.
  - 📝 **Content Enhancement**: Get AI-generated rewrites for your summary, headline, and other sections.
  - 🎓 **Career Counseling**: Identify skill gaps and receive actionable advice and learning resources.
- **Episodic Memory**: Create and manage multiple chat sessions (e.g., for “Data Scientist” or “Product Manager” roles) with isolated memory for each session.

---

## 🛠️ Getting Started

### 1. Prerequisites

- Python 3.9+
- Virtual environment tool (like `venv`)

### 2. Clone the Repository

```bash
git clone <repo-url>
cd your-repo-name
````

### 3. Set Up the Virtual Environment

```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# Windows
venv\Scripts\activate

# macOS/Linux
source venv/bin/activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Configure API Keys

Create a `.env` file in the root directory and add your API keys:

```env
# OpenAI Key
OPENAI_API_KEY="sk-..."

# Apify Key
APIFY_API_TOKEN="apify_api_..."
```

### 6. LinkedIn Cookie Setup for Scraping

1. Install the [Cookie-Editor](https://chrome.google.com/webstore/detail/cookie-editor) Chrome extension.
2. Log in to [LinkedIn](https://www.linkedin.com/).
3. Click on the Cookie-Editor icon in your toolbar.
4. Click **Export** to copy all cookies.
5. Create a file at `unit_test/cookie.json`.
6. Paste the copied JSON content and save.

> ✅ Note: The scraper script `agents/linkedin_scraper.py` is preconfigured to read from this location.

### 7. Run the Application

```bash
streamlit run app.py
```

Your browser will open with the AI LinkedIn Coach UI.

---

## 🧠 System Architecture

### LangGraph Multi-Agent System

The system uses **LangGraph** to manage conversational flow via a **router and specialist agents**:

### 🔀 Router (The Brain)

It routes incoming user messages to the right AI agent based on intent:

* `analyze_profile`
* `analyze_job_fit`
* `enhance_content`
* `counsel_career`
* `general_question`
* `end_session`

### 🧩 Specialist Agents

* **ProfileAnalyzerAgent**: Performs profile review and improvement suggestions.
* **JobFitAgent**: Compares your profile against generated job descriptions.
* **ContentEnhancerAgent**: Rewrites specific sections using copywriting best practices.
* **CareerCounselorAgent**: Suggests skills, courses, and roadmaps for career goals.

### 🗃️ Memory System

Powered by `LangGraph.SqliteSaver`:

* **Thread IDs**: Each session has a unique `thread_id`.
* **Persistent Context**: Stored in `threads.sqlite`.
* **Seamless Switching**: You can revisit any thread with full chat history intact.

---

## 📁 Repository Info

> **Note**: No official release or topics defined yet.

* **Language**: Python (100%)
* **License**: Not specified

---

## 📣 Contribute / Star / Watch

* ⭐ Give it a star if you find it useful.
* 👀 Watch the repo for updates.
* 🍴 Fork to contribute enhancements.

---

