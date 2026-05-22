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

# 🩺 MediMate AI

## 🌟 Overview

MediMate AI is a professional, fully offline, privacy-focused health assistant desktop application.  
It runs entirely on the local machine without any cloud API or internet dependency.

- Built with **C++17**
- Uses **Qt 6 framework**
- Designed for **offline intelligent health assistance**

---

## ✨ Features

### 🤖 Intelligent Health Assistant Engine
- Context-aware multi-turn conversation using a **6-state FSM**
- Randomized personality responses for natural interaction
- Emergency detection system for critical medical keywords

### 🩺 Symptom Analysis System
- Token-based symptom detection with local knowledge base
- Severity input system (1–10 scale)
- Structured diagnosis output (causes, recommendations, warnings)

### 🥗 Diet Planning Module
- Personalized 3-meal plans (Breakfast, Lunch, Dinner)
- Goal-based adaptation (Weight Loss, Muscle Gain, Wellness)
- Condition-aware dietary warnings (e.g., diabetes support)

### 🏃 Exercise Recommendation System
- Custom workout generation (Strength / Cardio / Wellness)
- Adapted to user health goals and profile

### 👤 User Profile Management
- Create, load, and delete profiles locally
- Stores age, gender, height, weight, and health conditions
- Fully offline persistent data storage

### 📊 Health Tracking System
- Real-time Health Score (0–100)
- Tracks activity level and profile completion
- Interactive checklist system

---

## 🛠️ Tech Stack

- **Language:** C++17  
- **UI Framework:** Qt 6 (Widgets)  
- **Styling:** Qt Style Sheets (QSS)  
- **Architecture:** FSM-based modular system  
- **Storage:** Local file-based persistence  
- **Project System:** Qt `.pro` (qmake)  

---

## 🧠 Architecture Overview

```
Presentation Layer (Qt UI)
        ↓
Business Logic Layer (FSM Engine, Health Score, Task Manager)
        ↓
Data Layer (Profile Manager, File Manager, History Manager)
```

### FSM Flow

```
IDLE → SEVERITY_ASSESSMENT → SYMPTOM_GATHERING → DIAGNOSIS
                 ↑
     EMERGENCY INTERRUPT (global override)
```

---

## 🚀 How to Build & Run

### Method 1: Qt Creator (Recommended)

1. Clone the Repository:
```bash
git clone https://github.com/Amna-tuz-Zahra/MediMate.git
cd MediMate
```

2. Open the Project:
- Launch Qt Creator  
- Click File → Open File or Project...  
- Open `MediMate.pro`

3. Configure Build Kit:
- Select Qt 6 kit (MinGW / MSVC)

4. Build & Run:
- Press Ctrl + B
- Press Ctrl + R

---

### Method 2: Command Line (qmake)

1. Clone Repository:
```bash
git clone https://github.com/Amna-tuz-Zahra/MediMate.git
cd MediMate
```

2. Create Build Folder:
```bash
mkdir build
cd build
```

3. Build Project:
```bash
qmake ..\MediMate.pro
mingw32-make
```

4. Run Application:
```bash
release\MediMate.exe
```

---

## 📌 Project Highlights

- Fully offline AI health assistant
- FSM-driven intelligent conversation system
- Emergency detection mechanism
- Clean modular architecture
- Lightweight and privacy-focused design

---

## ⚠️ Disclaimer

MediMate AI is an educational project and is NOT a medical device.  
It does not provide professional medical diagnosis or treatment.

---

## 👩‍💻 Developer

**Amna Tuz Zahra**  
GitHub: https://github.com/Amna-tuz-Zahra

---
