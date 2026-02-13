# 🎵 Vibe-Sync Desk Companion

An intelligent context-switching assistant that synchronizes your sonic environment with your cognitive workload.

## 📋 Overview

The Vibe-Sync Desk Companion is an interactive system designed to mitigate context-switching fatigue for students and professionals. By monitoring real-time audio data from Spotify and comparing it against scheduled commitments in Google Calendar, the system ensures that your "sonic environment" matches your cognitive load.

If the system detects a "vibe mismatch"—such as high-energy music playing right before a deep-work study session—it triggers a visual alert on a dashboard to help you transition smoothly between tasks.

## 🎯 Key Features

- **Real-Time Monitoring**: Continuously tracks Spotify playback and upcoming calendar events
- **Intelligent Analysis**: Uses LLM-powered interpretation via Duke AI Gateway to understand music mood and task intent
- **Vibe Detection**: Identifies mismatches between sonic environment and cognitive needs
- **Proactive Alerts**: Provides visual notifications with personalized transition suggestions
- **Context Switching Support**: Helps users smoothly transition between different task types
- **Dashboard Display**: Real-time visualization of current state and recommendations

## 🏗️ System Architecture

### Components

The system consists of four main layers:

1. **Input Layer**
   - Spotify Web API (track metadata, audio features)
   - Google Calendar API (event details, timing)

2. **Processing Layer**
   - Python orchestrator for API polling and data aggregation

3. **Intelligence Layer**
   - Duke AI Gateway (GPT-4) for mood interpretation and compatibility analysis

4. **Output Layer**
   - Web dashboard for visual alerts and state display

### Data Flow

```
Spotify API + Calendar API
          ↓
   Python Orchestrator
          ↓
   Duke AI Gateway (LLM Analysis)
          ↓
  Compatibility Assessment
          ↓
    Dashboard Update
```

## 🔄 How It Works

1. **Data Extraction**: System polls Spotify and Google Calendar APIs every 30 seconds
2. **Context Building**: Combines music metadata (valence, energy, tempo) with upcoming calendar events
3. **AI Interpretation**: Duke AI Gateway analyzes the "vibe" of your music and the "intent" of upcoming tasks
4. **Mismatch Detection**: If compatibility score < 60, system flags a mismatch
5. **User Notification**: Dashboard displays color-coded alerts with transition suggestions

## 🧠 The "Brain": LLM-Driven Intelligence

Rather than using hard-coded rules, Vibe-Sync employs an **LLM-driven enrichment layer** through the Duke AI Gateway:

- **The Tool**: Duke AI Gateway (secure wrapper for GPT-4)
- **The Function**: Acts as an "Interpreter" that synthesizes raw data into actionable insights
- **The Process**: 
  1. Extracts metadata from Spotify and text from Google Calendar
  2. Sends data to Duke AI Gateway for contextual summarization
  3. LLM assesses music mood and task intent
  4. Generates compatibility score and transition suggestions

## 📊 Documentation

Comprehensive system documentation is available in the `/docs` folder:

- **[System Architecture Diagram](docs/vibe_sync_architecture.html)**: Complete overview with functionality, data flow, and pseudocode
- **[Data Flow Diagram](docs/data_flow_diagram.html)**: Detailed 5-step data transformation process
- **[Flowchart with Pseudocode](docs/flowchart_with_pseudocode.html)**: Traditional flowchart paired with implementation pseudocode

## 🛠️ Technology Stack

- **Backend**: Python 3.x
- **APIs**: 
  - Spotify Web API
  - Google Calendar API
  - Duke AI Gateway (GPT-4)
- **Frontend**: HTML/CSS/JavaScript (dashboard)
- **Communication**: WebSocket or REST polling

## 📁 Project Structure

```
vibe-sync-project/
├── docs/                          # System documentation
│   ├── vibe_sync_architecture.html
│   ├── data_flow_diagram.html
│   └── flowchart_with_pseudocode.html
├── src/                           # Source code (to be implemented)
│   ├── main.py
│   ├── spotify_client.py
│   ├── calendar_client.py
│   └── ai_gateway.py
├── assets/                        # Images and resources
└── README.md
```

