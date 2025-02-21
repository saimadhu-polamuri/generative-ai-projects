# 🚀 Financial AI Agent – Powered by Agno & Groq 💰📈

This project explores **Agno AI** and **Groq's Llama 3.2 models** to build a **Finance AI Agent** that:
- 📊 **Analyzes stock market data**
- 📑 **Summarizes analyst recommendations**
- 📰 **Fetches real-time financial news**
- 🔍 **Performs web-based financial research**

Inspired by **Krish Naik's video** on Phidata Agents, this implementation is updated to work seamlessly with **Agno AI** instead.

---

## 🛠️ Tech Stack & Dependencies

This demo utilizes:
- **[Agno AI](https://github.com/agnolabs/agno)** – A lightweight, modular AI framework for agent-based applications.
- **[Groq](https://groq.com/)** – Llama 3.2-powered AI models optimized for speed.
- **[DuckDuckGo Tools](https://github.com/agnolabs/agno)** – Enables real-time web search capabilities.
- **[YFinance Tools](https://github.com/agnolabs/agno)** – Fetches stock prices, analyst recommendations, and company fundamentals.

---

## 📌 Features
✅ **Walkthrough of Agno AI & Groq setup**  
✅ **How to access APIs & documentation**  
✅ **Code implementation (Updated from Phidata to Agno)**  
✅ **Live Execution of the Finance AI Agent**  

---

## 🚀 Installation & Setup

### 1️⃣ Clone the Repository
```bash
    git clone https://github.com/saimadhu-polamuri/generative-ai-projects.git
    cd generative-ai-projects/financial-agent
```


### 2️⃣ Create a Virtual Environment (Recommended)
```bash
    python -m venv venv
    source venv/bin/activate  # On macOS/Linux
    venv\Scripts\activate     # On Windows
```


### 3️⃣ Install Dependencies
```bash
    pip install -r requirements.txt
```


## 📝 Code Overview
## 🔍 Web Search Agent
Uses DuckDuckGo to search for relevant information with source verification.


```python
web_search_agent = Agent(
    name="Web Search Agent",
    role="Search the web for financial information",
    model=Groq(id="llama-3.2-3b-preview"),
    tools=[DuckDuckGoTools()],
    instructions=["Always include sources"],
    show_tool_calls=True,
    markdown=True
)
```

## 💰 Finance AI Agent
Fetches stock prices, analyst ratings, and company news from Yahoo Finance.


```python
finance_agent = Agent(
    name="Finance AI Agent",
    role="Analyze the given stock",
    model=Groq(id="llama-3.2-11b-vision-preview"),
    tools=[
        YFinanceTools(
            stock_price=True,
            analyst_recommendations=True,
            stock_fundamentals=True,
            company_news=True
        )
    ],
    instructions=["Use tables to display the data"],
    show_tool_calls=True,
    markdown=True,
)
```

# 🧠 Multi-Agent System
Combines web search and finance analysis for a comprehensive AI-driven financial research system.



```python
multi_ai_agent = Agent(
    team=[web_search_agent, finance_agent],
    instructions=["Always include sources", "Use tables to display the data"],
    show_tool_calls=True,
    markdown=True,
)

multi_ai_agent.print_response(
    "Summarize analyst recommendation and share the latest news for Apple",
    stream=True
)
```

## ▶️ Running the AI Agent
Run the Finance AI Agent script:
```bash
python finance_agent.py
```


You should see real-time financial insights displayed, including:

- Stock Market Data
- Analyst Recommendations
- Latest Financial News


## 📌 Future Enhancements
- ✅ Add multi-modal AI capabilities 📷
- ✅ Implement financial trend predictions 📈
- ⏳ Enhance RAG-based summarization 🧠
- ⏳  Explore AutoGPT integrations 🤖

# 📢 Connect with Me

<a href="https://www.linkedin.com/in/saimadhu/" target="_blank"> <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"> </a> <a href="https://dataaspirant.com/" target="_blank"> <img src="https://img.shields.io/badge/Blog-21759B?style=for-the-badge&logo=wordpress&logoColor=white" alt="Blog"> </a> <a href="mailto:saimadhu@dataaspirant.com"> <img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"> </a>  </a> <a href="https://www.youtube.com/@dataaspirant" target="_blank"> <img src="https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="YouTube"> </a>


## ⭐ If you found this project useful, don’t forget to star this repo! ⭐
🚀 Keep innovating, keep experimenting! 💡
