# 🩺 MediMate AI

<div align="center">
  <img width="80" src="https://raw.githubusercontent.com/microsoft/fluentui-emoji/main/assets/Stethoscope/3D/stethoscope_3d.png" alt="MediMate Logo"/>
  <h3>A professional offline AI health assistant built with Qt 6 & C++17</h3>
  <br>
  
  [![Qt](https://img.shields.io/badge/Qt-6.x-41CD52?style=for-the-badge&logo=qt&logoColor=white)](https://www.qt.io/)
  [![C++](https://img.shields.io/badge/C%2B%2B-17-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)](https://en.cppreference.com/w/cpp/17)
  [![Platform](https://img.shields.io/badge/Platform-Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)](#)
  [![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](#license)
</div>

---

## 🌟 Overview

**MediMate AI** is a professional, fully offline, privacy-focused health assistant desktop application. Engineered from the ground up to operate completely client-side without cloud APIs or external network dependency, MediMate AI guarantees that your sensitive health data never leaves your local machine.

* **Professional offline AI health assistant** desktop application.
* Built using modern **C++17** and the **Qt 6** framework.
* Focuses on absolute **privacy**, **offline execution**, and **intelligent health assistance**.

---

## ✨ Features

### 🤖 Intelligent Health Assistant Engine
* **Context-Aware Chat:** Maintains stateful, multi-turn conversations using a 6-state finite state machine (FSM).
* **Randomized Personality:** Dynamic, natural greetings, wellness tips, and fallback responses drawn from pre-configured pools.
* **Emergency Interrupter:** Continuously scans input for 18+ critical keywords (e.g., *chest pain*, *stroke*, *choking*) to immediately halt normal flow and display critical emergency instructions.

### 🩺 Symptom Analysis System
* **Tokenized Parsing:** Natural language parser identifies symptoms and cross-references them with a built-in local medical knowledge base.
* **Severity Assessment:** Dynamically prompts for pain/severity levels (1–10) using custom UI widgets and renders a structured diagnosis card complete with causes, recommended actions, and red flags.

### 🥗 Diet Planning Module
* **Goal-Adaptive Recommendations:** Generates complete daily 3-meal plans (Breakfast, Lunch, Dinner) tailored to the user's primary health goal (e.g., Weight Loss, Muscle Building, Wellness).
* **Condition Warnings:** Automatically applies critical dietary precautions and warnings for conditions such as diabetes.

### 🏃 Exercise Recommendation System
* **Custom Routines:** Formulates targeted workouts (Strength, Cardio HIIT, or Wellness walks) based on user goals, physical metrics, and preferred session duration.

### 👤 User Profile Management
* **Secure Profile CRUD:** Create, load, and delete user profiles locally.
* **Metric Storage:** Tracks metrics including age, gender, height, weight, health conditions, and fitness preferences to customize health calculations.

### 📊 Session History & Health Tracking
* **Conversation Replay:** Local history storage tags and saves every message under sender roles (`USER`, `BOT`, `EMERGENCY`) for future review.
* **Wellness Dashboard:** Renders a real-time, composite **Health Score** (0–100) calculated from profile completion, daily task checklist status, physical activity levels, and general inputs.
* **Interactive Checklist:** Auto-generates health checklist items from recommendations with direct user checklist tracking.

### 🎨 Modern Qt-Based UI
* **Two-Panel Layout:** A sleek gradient brand welcome panel coupled with a clean, functional workspace panel.
* **Fluid Interaction:** Custom elements including animated suggestion chips, a dynamic severity slider, custom-styled scrollbars, and styled HTML chat bubbles.

---

## 🛠️ Tech Stack

* **Language Standard:** C++17 (utilizing `std::filesystem` and standard library algorithms).
* **UI Framework:** Qt 6 (Widgets module).
* **Styling Engine:** Qt Style Sheets (QSS) for styling and premium theme design.
* **Data Layer:** Standard File I/O + custom serialization for local profile/task storage.
* **Project System:** Qt Project System (`.pro` / `qmake`).

---

## 🧠 Architecture Summary

MediMate AI is designed around a decoupled, modular architecture separation:

```
┌────────────────────────────────────────────────────────────────────────┐
│                        Presentation Layer (UI)                         │
│   [MainWindow (Qt)]  <──>  [ProfileDetailsDialog]  <──>  [QSS Styles]  │
└───────────┬────────────────────────────────────────────────────────────┘
            │ Controls UI interactions, inputs, and widgets
            ▼
┌────────────────────────────────────────────────────────────────────────┐
│                      Business Logic & State Layer                      │
│   [ChatBot FSM]  <───>  [HealthScore Engine]  <───>  [ToDoManager]     │
└───────────┬────────────────────────────────────────────────────────────┘
            │ Evaluates conditions, schedules tasks, rules FSM logic
            ▼
┌────────────────────────────────────────────────────────────────────────┐
│                     Data Persistence & Model Layer                     │
│   [FileManager]  <───>  [ProfileManager]  <───>  [HistoryManager]      │
└────────────────────────────────────────────────────────────────────────┘
```

### Finite State Machine (FSM) Workflow

```
       ┌───────────────────────────────┐
       │             IDLE              │
       └───────────────┬───────────────┘
                       │ symptom detected
                       ▼
       ┌───────────────────────────────┐
       │      SEVERITY_ASSESSMENT      │
       └───────────────┬───────────────┘
                       │ severity inputted
                       ▼
       ┌───────────────────────────────┐
       │       SYMPTOM_GATHERING       │
       └───────────────┬───────────────┘
                       │ follow-ups completed
                       ▼
       ┌───────────────────────────────┐
       │      PROVIDING_DIAGNOSIS      │
       └───────────────────────────────┘
 ───────────────────────────────────────────────
  * EMERGENCY KEYWORD DETECTION interrupts 
    any state instantly to trigger EMERGENCY state.
 ───────────────────────────────────────────────
```

---

## 🚀 How to Build & Run

### Prerequisites

* **Qt SDK:** Qt 6.x (Widgets module required)
* **Compiler:** C++17 compatible compiler (GCC 9+, Clang 10+, MSVC 2019+, or MinGW 11+)
* **IDE:** Qt Creator (recommended) or any C++ environment with `qmake`/CMake integration.

### Method 1: Qt Creator (Recommended)

1. Clone the Repository:
```bash
git clone https://github.com/Amna-tuz-Zahra/MediMate.git
cd MediMate
```

2. Open the Project:
- Launch Qt Creator
- Click File → Open File or Project...
- Navigate to the cloned folder
- Open MediMate.pro

3. Configure Build Kit:
- Select your installed Qt 6 kit (e.g., Desktop Qt 6.x.x MinGW 64-bit)

4. Compile & Execute:
- Press Ctrl + B to build the application
- Press Ctrl + R to run it

---

### Method 2: Command Line (qmake)

1. Clone the Repository:
```bash
git clone https://github.com/Amna-tuz-Zahra/MediMate.git
cd MediMate
```

2. Create Build Directory:
```bash
mkdir build
cd build
```

3. Run qmake and Build:
```bash
qmake ..\MediMate.pro
mingw32-make   # or make / nmake depending on your toolchain
```

4. Run the Application:
```bash
release\MediMate.exe
```
---

## 📌 Project Highlights

* **100% Local Execution:** No data leaves the device; entirely offline system respecting user privacy.
* **Robust Emergency Handlers:** Real-time priority interrupt mechanism bypasses standard FSM queues to prioritize critical warnings.
* **Production-Grade Clean Code:** Written with strict separation of UI components and underlying health models.

---

## ⚠️ Disclaimer

MediMate AI is an **educational software demonstration** and is **not a substitute for professional medical advice, diagnosis, or treatment**. Always consult a qualified healthcare provider with any questions you may have regarding a medical condition. If you are experiencing a medical emergency, call your local emergency services (e.g., 911) immediately.

---

<div align="center">
  <sub>Developed with ❤️ using Qt 6 & C++17</sub>
</div>
