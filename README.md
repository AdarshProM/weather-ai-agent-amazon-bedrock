# 🌤️ Weather AI Agent — Amazon Bedrock + Claude 4.5 Sonnet

![Python](https://img.shields.io/badge/Python-3.8+-blue)
![AWS](https://img.shields.io/badge/AWS-Amazon%20Bedrock-orange)
![Claude](https://img.shields.io/badge/AI-Claude%204.5%20Sonnet-purple)
![Streamlit](https://img.shields.io/badge/UI-Streamlit-red)

## 📌 Project Overview

An **Agentic AI weather forecasting application** built using **Claude 4.5 Sonnet on Amazon Bedrock** that autonomously plans API calls, fetches real-time weather data, and generates human-readable forecasts.

Available in two interfaces:
- 🖥️ **CLI version** — Command-line agent
- 🌐 **Web version** — Streamlit interactive UI

---

## 🤖 What Makes This "Agentic"?

| Agent Capability | Implementation |
|-----------------|----------------|
| 🧠 **Reasoning** | Claude analyzes natural language location inputs |
| 📋 **Planning** | AI generates correct NWS API URLs autonomously |
| 🔧 **Action** | Agent executes real HTTP API calls |
| 📊 **Processing** | Claude converts raw JSON to readable forecasts |
| 🔄 **Adaptation** | Handles city names, ZIP codes, descriptions |

---

## 🏗️ Architecture

```
User Input (Location)
       ↓
🧠 Claude 4.5 Sonnet (Amazon Bedrock)
   → Determines coordinates
   → Generates NWS Points API URL
       ↓
🔗 NWS Points API Call
   → Returns forecast office + grid data
       ↓
📍 Extract Forecast URL from response
       ↓
🌦️ NWS Forecast API Call
   → Returns raw 7-day forecast JSON
       ↓
📊 Claude 4.5 Sonnet (Amazon Bedrock)
   → Processes raw JSON
   → Generates human-readable summary
       ↓
💬 Display to User (CLI or Streamlit)
```

---

## 🛠️ Tech Stack

| Technology | Purpose |
|-----------|---------|
| Amazon Bedrock | AWS managed AI service |
| Claude 4.5 Sonnet | AI reasoning + data processing |
| National Weather Service API | Free real-time weather data |
| boto3 | AWS Python SDK |
| Streamlit | Interactive web interface |
| Python 3.8+ | Core language |

---

## ⚙️ How to Run

### Step 1: Clone Repository
```bash
git clone https://github.com/YOUR_USERNAME/weather-ai-agent-amazon-bedrock.git
cd weather-ai-agent-amazon-bedrock
```

### Step 2: Create Virtual Environment
```bash
python -m venv .venv
source .venv/bin/activate   # Mac/Linux
.venv\Scripts\activate      # Windows
```

### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 4: Configure AWS Credentials
```bash
aws configure
# Enter your AWS Access Key, Secret Key, Region (us-west-2)
```

### Step 5A: Run CLI Version
```bash
python weather_agent_cli.py
```

### Step 5B: Run Web Version
```bash
streamlit run weather_agent_web.py
```

---

## 🌍 Supported Location Formats

| Input Type | Example |
|-----------|---------|
| City name | `Seattle` |
| City + State | `Miami, FL` |
| ZIP code | `90210` |
| Multi-word city | `New York City` |
| Descriptive query | `National park near Homestead in Florida` |
| Knowledge-based | `Largest city in California` |

---

## 📊 Sample Output

**Input:** `Seattle`

**Agent Process:**
```
Step 1: 🧠 AI Planning → https://api.weather.gov/points/47.6062,-122.3321
Step 2: 🔗 Points API → Location grid data received
Step 3: 📍 Forecast URL extracted
Step 4: 🌦️ Forecast API → 14,000+ chars of weather data
Step 5: 📊 Claude processes → Human-readable summary
```

**Output:** 3-day weather forecast with temperatures, precipitation, and activity recommendations

---

## 🔑 Key AWS Concepts Demonstrated

- **Amazon Bedrock** — Managed AI service for accessing foundation models
- **Claude 4.5 Sonnet** — Latest Anthropic model via Bedrock API
- **Bedrock Converse API** — Standardized interface for AI model interaction
- **boto3 SDK** — AWS Python SDK for Bedrock client creation
- **IAM Permissions** — AWS credential management for Bedrock access
- **Agentic AI Pattern** — Plan → Act → Process → Respond loop

---

## 🚀 Future Enhancements

- [ ] Deploy on AWS Lambda for serverless execution
- [ ] Add AWS CloudWatch logging and monitoring
- [ ] Integrate with Amazon S3 for forecast history storage
- [ ] Add multi-location comparison feature
- [ ] Deploy Streamlit app on AWS EC2/ECS
- [ ] Add Amazon SNS for weather alerts/notifications

---

## 👨‍💻 Author

**Adarsh Singh** — Google Associate Cloud Engineer | AWS Certified | Azure Solutions Architect Expert
- LinkedIn: [linkedin.com/in/narayanadarsh](https://linkedin.com/in/narayanadarsh)
- GitHub: [github.com/YOUR_USERNAME](https://github.com/AdarshProM)
- Email: adarsh.narayan.official@outlook.com

---

*Built as part of AWS cloud engineering portfolio — demonstrating Agentic AI, Amazon Bedrock integration, and real-world API orchestration*
