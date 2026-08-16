# 🤖 LangGraph Agentic AI: News Summarizer & Smart Chatbot

An advanced, stateful **Agentic AI application** built using **LangGraph, LangChain, Groq, Tavily, and Streamlit**.

This project demonstrates how Large Language Models (LLMs) can be orchestrated into multiple intelligent workflows, including conversational AI, real-time web research, and automated AI news summarization.

---

# ✨ Features

## 💬 Basic Chatbot

A fast conversational AI assistant powered by Groq LLMs.

- Direct interaction with the LLM
- Fast response generation
- Stateful conversation workflow

---

## 🌐 Chatbot with Web Search

An agentic chatbot capable of retrieving real-time information from the web using Tavily.

- Searches the web for current information
- Uses external search results as context
- Generates grounded responses
- Useful for recent events, news, and factual queries

---

## 📰 AI News Summarizer

An automated AI news aggregation and summarization pipeline.

The system can:

- Fetch the latest AI and technology news
- Support Daily, Weekly, and Monthly timeframes
- Summarize multiple articles
- Generate clean Markdown summaries
- Save summaries locally for future reference

---

# 🏗️ Architecture

The application uses a modular and stateful **LangGraph architecture**.

```text
                         ┌─────────────────────┐
                         │   Streamlit UI      │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │   Application       │
                         │   Entry Point       │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │    LangGraph        │
                         │   StateGraph        │
                         └──────────┬──────────┘
                                    │
              ┌─────────────────────┼─────────────────────┐
              │                     │                     │
              ▼                     ▼                     ▼
      ┌──────────────┐     ┌────────────────┐    ┌────────────────┐
      │ Basic Chatbot│     │ Chatbot + Web  │    │ AI News Agent  │
      └──────────────┘     └───────┬────────┘    └───────┬────────┘
                                   │                     │
                                   ▼                     ▼
                            ┌──────────────┐      ┌──────────────┐
                            │ Tavily Search│      │ Web Search   │
                            └──────────────┘      └──────┬───────┘
                                                         │
                                                         ▼
                                                  ┌──────────────┐
                                                  │ LLM Summary  │
                                                  └──────────────┘
```

---

# 🛠️ Tech Stack

| Category | Technology |
|----------|------------|
| Programming Language | Python 3.x |
| AI Orchestration | LangGraph |
| LLM Framework | LangChain |
| LLM Provider | Groq |
| Search API | Tavily |
| Frontend | Streamlit |
| State Management | LangGraph State |
| Output Format | Markdown |

---

# 📂 Project Structure

```text
AI NEWS/
│
├── AINews/
│   ├── daily_summary.md
│   ├── weekly_summary.md
│   └── monthly_summary.md
│
├── src/
│   └── langgraphagenticai/
│       ├── main.py
│       │
│       ├── graph/
│       │   └── graph_builder.py
│       │
│       ├── LLMS/
│       │   └── groqllm.py
│       │
│       ├── nodes/
│       │   ├── ai_news_node.py
│       │   ├── basic_chatbot_node.py
│       │   └── chatbot_with_Tool_node.py
│       │
│       ├── state/
│       │   └── state.py
│       │
│       ├── tools/
│       │   └── search_tool.py
│       │
│       └── ui/
│           ├── streamlitui/
│           │   ├── display_result.py
│           │   └── loadui.py
│           │
│           ├── uiconfigfile.ini
│           └── uiconfig.py
│
├── app.py
├── requirements.txt
├── README.md
└── .gitignore
```

---

# 🚀 Installation & Setup

## 1️⃣ Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git
cd YOUR_REPOSITORY_NAME
```

---

## 2️⃣ Create a Virtual Environment

### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

### macOS / Linux

```bash
python3 -m venv venv
source venv/bin/activate
```

---

## 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

The project uses packages including:

- langchain
- langgraph
- langchain-community
- langchain-core
- langchain-groq
- streamlit
- tavily-python

---

# 🔑 API Key Configuration

This application requires API keys for **Groq** and **Tavily**.

## Groq API

Used for LLM inference and AI-powered responses.

## Tavily API

Used for real-time web search.

Create a `.env` file in the project root:

```env
GROQ_API_KEY=your_groq_api_key
TAVILY_API_KEY=your_tavily_api_key
```

> ⚠️ Never commit your `.env` file or API keys to GitHub.

---

# 💻 Usage

Start the Streamlit application:

```bash
streamlit run app.py
```

The application will be available at:

```text
http://localhost:8501
```

---

# 🧭 How to Use the Application

## 💬 Basic Chatbot

1. Select **Basic Chatbot**
2. Enter your message
3. Receive an AI-generated response powered by Groq

```text
User Input
    │
    ▼
Basic Chatbot Node
    │
    ▼
Groq LLM
    │
    ▼
AI Response
```

---

## 🌐 Chatbot with Web Search

Useful for current events and real-time information.

```text
User Query
    │
    ▼
Tavily Web Search
    │
    ▼
Search Results
    │
    ▼
Groq LLM
    │
    ▼
Grounded Response
```

The chatbot:

- Receives the user's question
- Searches the web using Tavily
- Retrieves relevant information
- Passes search results to the LLM
- Generates a grounded response

---

## 📰 AI News Summarizer

The AI News workflow automatically searches and summarizes the latest AI news.

### Supported Timeframes

- Daily
- Weekly
- Monthly

### Workflow

```text
Select Timeframe
       │
       ▼
Search Latest AI News
       │
       ▼
Collect Articles
       │
       ▼
Summarize Content
       │
       ▼
Generate Markdown
       │
       ▼
Save to AINews/
```

Generated summaries are saved as:

```text
AINews/
│
├── daily_summary.md
├── weekly_summary.md
└── monthly_summary.md
```

---

# 🧠 LangGraph Workflows

## Basic Chatbot Workflow

```text
User Input
    │
    ▼
Chatbot Node
    │
    ▼
LLM
    │
    ▼
Response
```

---

## Web-Enabled Chatbot Workflow

```text
User Question
      │
      ▼
Search Tool
      │
      ▼
Tavily API
      │
      ▼
Web Results
      │
      ▼
Groq LLM
      │
      ▼
Final Answer
```

---

## AI News Summarization Workflow

```text
Timeframe Selection
        │
        ▼
Web Search
        │
        ▼
Article Collection
        │
        ▼
AI Summarization
        │
        ▼
Markdown Generation
        │
        ▼
Local File Storage
```

---

# ✨ Key Highlights

- 🤖 Multi-use-case Agentic AI application
- 🧠 Stateful LangGraph architecture
- 💬 Conversational AI chatbot
- 🌐 Real-time web-enabled research
- 📰 Automated AI news summarization
- 🔍 Tavily-powered web search
- ⚡ Fast Groq LLM inference
- 🎨 Interactive Streamlit UI
- 📄 Markdown-based news storage
- 🧩 Modular and scalable project architecture

---

# 🚧 Future Enhancements

Potential improvements include:

- 📚 Support for additional news categories
- 🗄️ Database storage for news history
- 🔍 Duplicate article detection
- 📊 News trend analytics
- 🧠 Improved source ranking
- 📧 Automated email delivery
- ⏰ Scheduled news generation
- 🚀 Docker deployment
- ☁️ Cloud deployment
- 🔐 User authentication

---

# 🤝 Contributing

Contributions, issues, and feature requests are welcome.

To contribute:

1. Fork the repository
2. Create a new branch
3. Make your changes
4. Commit your changes
5. Open a Pull Request

---

# 👨‍💻 Author

**Arshan Sayyadahamad Attar**

AI Engineer focused on:

- Generative AI
- Agentic AI
- LangChain
- LangGraph
- Python
- LLM Applications
- Backend Development
- Computer Vision

---

# ⭐ Support

If you found this project useful, please consider **starring ⭐ the repository** and sharing it with others.

Happy Coding! 🚀
