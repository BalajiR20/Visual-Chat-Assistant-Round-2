
# 🎥 AI-Powered Video Summarizer & Chat Assistant

An intelligent video understanding tool that combines multimodal AI with a clean, interactive Streamlit interface.
Upload a video, get an AI-generated detailed summary, and ask context-aware questions in real time — powered by Google’s Gemini 2.5 Pro model.
___
![Alt text](https://github.com/BalajiR20/Visual-Chat-Assistant-Round-2/blob/main/assests/Screenshot%202025-08-13%20231223.png)

## 🧠 Project Summary

Modern content consumption often demands quick comprehension of long videos without watching them in full. This project bridges that gap by:

* 📜 Summarizing entire videos with context-aware AI.

* 💬 Allowing conversational QnA using both video frames and summary text.

* 💾 Persisting summaries & chat history in a local SQLite database.

* 🎨 Offering a modern UI with gradient headers, card-style sections, and animated components for better UX.

## 🏗 Architecture Diagram
```plaintext

+------------------+
|  User Uploads    |
|      Video       |
+--------+---------+
         |
         v
+--------+---------------+
| Gemini 2.0 flash exp   |
|  Multimodal LLM        |
+--------+---------------+
         |
         v
+--------+---------+          +-----------------------------+
|  Summary          |          |                             |
|  Generation       +--------->+  SQLite Database            |
|                   |   Save   | (Summary + Chat Logs)       |
+--------+----------+          |                             |
         |                     +-------------+---------------+
         v                                   ^
+--------+----------+                       |
| Streamlit Frontend|<----------------------+
|  (Video + Chat)   |
+--------+----------+
         |
         v
+-------------------+
| Contextual QnA    |
+-------------------+
```
---
## ⚙ Tech Stack & Reasoning
* Component	Technology / Tool	Why Chosen?
* Frontend	Streamlit	Rapid development of interactive UIs with Python.
* AI Model	Gemini 2.0 flash exp (Google)	Handles text + image inputs, supports long-context reasoning, and excels at semantic understanding.
* Video Frames	OpenCV, PIL	Extract frames from uploaded videos for AI ingestion.
* Database	SQLite	Lightweight, file-based DB for local persistence of summaries & chats.
* Chat System	Streamlit Chat API	Simple, persistent conversational UI.
* Agent Control	AutoGen (Microsoft)	For structured multi-role AI agent orchestration.
---
## 🛠 Installation & Setup
#### 🔧 Requirements
* Python 3.9+
* Google Gemini API key (from Google AI Studio)

#### 📦 Steps
1️⃣ Clone the Repository
```bash

git clone https://github.com/BalajiR20/Visual-Understanding-Chat-Assistant.git
cd Visual-Understanding-Chat-Assistant
```
2️⃣ Install Dependencies
```bash

pip install -r requirements.txt
```
3️⃣ Configure Environment Variables
Create a .env file in the project root:
```
GEMINI_API_KEY=your_gemini_api_key
```
4️⃣ Run the App
```bash

streamlit run main.py
```
---
## 🚀 How to Use:

1. Upload a Video
Supported formats: .mp4, .avi, .mov

Upload in the left panel of the app.

2. Generate Summary
The AI processes frames & context to generate a detailed, human-readable summary.

3. Chat with AI
Ask any question about the video’s content.

AI responds with contextual awareness using both summary + extracted visual details.

#### Example Prompts:

*  "What happened after the crash?"

* "Describe the background setting."

* "Who was the speaker in the first scene?"

4. Persist Conversations
All summaries and chats are saved in the SQLite database for future retrieval.
---
## 🧪 Example Queries & Answers:

🌐User Query	AI Response
* Who won the race?	The Renault car crossed the finish line first.   
* Were there people visible?	Yes, several spectators were in the stands.  
* Where was the camera placed?	Positioned at trackside near a fence.  
 
---

## 📊 Performance Benchmarks
#### Test Metric	Result
- Max. Context Length	2M+ tokens (Gemini)
- Video Upload Limit	~200MB (Streamlit default, configurable)
- Response Latency	~3s per chat turn
---
## 🎯 Future Improvements
- 🌎 Multi-language video summarization.
- 🗣 Speaker identification with voice embeddings.

⏱ Timeline-based clickable summaries.
---
📂 Sample Demo Video
🎥 Drive Link: [Download Sample Video](https://drive.google.com/file/d/1Vkdegjef2AYfk8qNAQ8jthZH_aITVrte/view?usp=sharing)


