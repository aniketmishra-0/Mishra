# CENTRIX: Product Overview & Feature Guide

**Application:** Centrix (Automated Classroom Lecture Capture & Cloud Delivery)  
**Target:** PhysicsWallah Vidyapeeth & Pathshala Offline Centers (442+ Centers Nationwide)  
**Platform:** Windows 10/11 Desktop Service & Modern Web Dashboard  
**Version:** 1.0.4  

---

## 1. What is Centrix?

Centrix is an autonomous desktop application built specifically for PhysicsWallah offline classrooms. It runs silently in the background on the classroom recording PC and completely automates the lecture delivery process.

Instead of classroom operators manually selecting files, filling in batch codes, and uploading multi-gigabyte videos through a web browser, **Centrix detects when a lecture finishes, matches it with the timetable, and uploads it directly to Google Drive and YouTube automatically.**

---

## 2. How Centrix Works (The Automated Workflow)

```
[Faculty Teaches Class] 
        │
        ▼
[OBS / Recording Software Stops] 
        │
        ▼
[1. Automatic Detection] ── Centrix detects the new video file instantly.
        │
        ▼
[2. Smart Matching] ──── Matches start/end time and classroom with the PW timetable.
        │
        ▼
[3. Direct Upload] ───── Streams chunks directly to Google Drive & YouTube.
        │
        ▼
[4. 1-Tap Review] ────── Center manager verifies the lecture with one click.
```

### Step 1: Automatic Recording Detection
- Centrix monitors the folder where OBS Studio or camera encoders save recordings.
- As soon as the recording stops, Centrix verifies that the file is complete and undamaged.

### Step 2: Smart Schedule & Timetable Matching
- Centrix automatically checks the live timetable for that center and classroom.
- It identifies:
  - **Batch Name & Batch ID**
  - **Subject & Faculty Name**
  - **Classroom Number**
- It tags the recording automatically with over 85% algorithmic confidence.

### Step 3: Resumable Direct Uploading
- Centrix uploads the video directly to PhysicsWallah's Google Drive in structured folders:  
  `Center Name / Classroom / Date / Batch Name / Lecture.mp4`
- If requested, it can also publish an unlisted video directly to YouTube for immediate faculty verification.
- **Network Drop Protection:** If the internet disconnects, Centrix pauses and automatically resumes from the exact same point when the connection returns. It never restarts a file from 0%.

### Step 4: 1-Tap Review Dashboard
- Center managers open the Centrix dashboard on their PC, tablet, or phone.
- They can preview the video, confirm the matched details, and approve it with one tap.

---

## 3. Core Features

### 1. 442 PW Centers Live Auto-Picker
- Integrated with the live PW Center Tracker.
- Center staff simply search for their center name (e.g. *Pune, Kota, Patna, Janakpuri, Lucknow*) from an instant search dropdown.
- Selecting a center automatically loads all its physical classrooms and batch schedules.
- **Zero code changes or configuration file editing needed when shipping to any center.**

### 2. Standalone Single-File Windows Installer
- Distributed as a single file: `Centrix-Setup.exe` (205 MB).
- Self-contained with the .NET runtime included (works out of the box on any Windows PC without installing additional software).
- Automatically installs a background Windows Service (`CentrixAgent`) that starts when the computer boots.

### 3. Clean, Modern Dashboard
- High-contrast, minimal editorial design with dark and light theme options.
- **Unified 32px Header:** Center selector, classroom switcher, notification bell, and sync button are cleanly aligned.
- **Zero-Blink Interface:** Switching classrooms or refreshing updates data smoothly without page jumping or screen flashing.

### 4. Resilient Offline Mode
- If a center loses internet connectivity for hours, recordings remain safely queued in Centrix's local database.
- Once connectivity is restored, all queued lectures upload automatically in the background.

---

## 4. Pros & Considerations

### Advantages
- **100% Automated:** Operators no longer need to manually manage files, write batch codes, or monitor uploads.
- **Fault Tolerant:** Handles weak, intermittent broadband connections without data loss or corruption.
- **Rapid Deployment:** Any center can install and configure the application in under 60 seconds.
- **Strict Data Separation:** Each PC only manages its designated classroom, preventing accidental cross-posting between centers.

### Considerations & Built-in Mitigations
- **PC Must Be Powered On:** Uploads require the host machine to remain running.  
  *Mitigation:* Centrix runs as a Windows background service that starts before user login, so uploads continue whenever the PC is on.
- **Local Hard Drive Space:** Multiple hours of recording can fill hard drive space if the internet is down for several days.  
  *Mitigation:* Centrix includes an auto-cleanup feature that safely removes local video files after they have been confirmed and uploaded to Google Drive.

---

## 5. Future Capabilities (What Can Be Added Next)

1. **On-Device AI Audio Quality Check (Whisper AI):**
   - Transcribe the first 2 minutes of the lecture locally using speech AI.
   - Verify that the teacher's spoken topic matches the scheduled subject (e.g. verifying *"Welcome students, today we start Thermodynamics"*).
   - Detect muted microphones or missing audio before uploading.

2. **Scheduled Off-Peak Uploads:**
   - For centers with slow daytime internet, allow video uploads to automatically run overnight (e.g., between 9:00 PM and 6:00 AM) while keeping timetable matching active during the day.

3. **Direct Student App Integration:**
   - Automatically publish approved video links directly into the student timetable on the PW mobile app and web portal.

4. **Central Operations Telemetry Map:**
   - A single live map for central operations showing the real-time recording and upload status of all 2,000+ classrooms nationwide.

5. **WhatsApp & Telegram Alerts:**
   - Send an immediate message to the center manager if a scheduled class ends but no recording file was found (catching human error within minutes).
