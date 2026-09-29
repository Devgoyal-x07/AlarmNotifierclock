# Project Statement: Python GUI Alarm Clock

## 1. Problem Statement
Managing daily schedules and task reminders requires straightforward, reliable tools. Many system-native or mobile alarms are tied to complex ecosystems or distraction-heavy interfaces. The objective of this project is to develop a lightweight, distraction-free desktop alarm clock application that runs natively on desktop environments, allowing users to configure target wake-up or reminder times via an intuitive Graphical User Interface (GUI).

---

## 2. Project Overview & Scope
This project implements a desktop alarm clock in **Python** using the standard **Tkinter** library for GUI rendering, Python's multi-threading module to prevent UI freezes, and the **Winsound** module for audio playback.

### Key Objectives:
- Provide an intuitive GUI with dropdown selectors for hours (`HH`), minutes (`MM`), and seconds (`SS`).
- Ensure non-blocking background time monitoring via multi-threading.
- Automatically trigger customizable audio alerts upon reaching the designated target time.
- Use native, standard Python libraries requiring zero external third-party package dependencies.

---

## 3. System Architecture & Workflow

1. **User Interface (GUI Layer):**
   - Built with `tkinter`.
   - Uses `OptionMenu` dropdowns populated with ranges for hours (`00`–`23`), minutes (`00`–`59`), and seconds (`00`–`59`).
2. **Background Execution (Threading Layer):**
   - When the user clicks **"Set Alarm"**, a daemon/background thread (`threading.Thread`) is spawned.
   - Decoupling the continuous time-checking loop from the Tkinter main event loop ensures the GUI remains responsive and does not freeze or crash.
3. **Time Verification Loop:**
   - Samples system time every second via `datetime.datetime.now().strftime("%H:%M:%S")`.
   - Compares current time against formatted target time (`HH:MM:SS`).
4. **Notification & Audio Output:**
   - Once the condition matches, the system triggers the alert using `winsound.PlaySound` asynchronously (`SND_ASYNC`).

---

## 4. Technology Stack & Dependencies

- **Language:** Python 3.x
- **GUI Toolkit:** `tkinter` (Built into Python standard library)
- **Audio Engine:** `winsound` (Windows native standard library)
- **Concurrency:** `threading`
- **Time/OS Modules:** `datetime`, `time`, `os`
- **External Dependencies:** None (Runs on vanilla Python on Windows)

---

## 5. Prerequisites & Setup Instructions

### Prerequisites
- Operating System: **Windows 10 / 11** (required for native `winsound` playback)
- Python 3.8+ installed and added to system `PATH`

### Installation & Execution

1. **Clone the repository:**
   ```bash
   git clone [git clone https://github.com/devgoyal-x07/Python-Essentials---Evaluated-Course-Project..git
cd Python-Essentials---Evaluated-Course-Project.
