# UniMate: Automated Campus Lab Scheduler & Bot 🤖

A full-stack automation ecosystem designed for the **ALCHE** campus network. This project enables students to securely configure their portal credentials through a localized web dashboard and leverages an automated browser engine to bypass manual scheduling delays, instantly securing high-demand study rooms and laboratory slots.

## 🚀 Key Features & Engineering Pillars

* **Full-Stack Control Panel:** Built a responsive local web interface using HTML, CSS, and a Flask backend, completely eliminating the need for users to modify raw source code to adjust settings.
* **Dynamic Form Synchronization:** Implemented real-time form handling that securely pipes user inputs (Student Name, ID, Date, Time, and Target Facility) into a local database and clears interface fields upon saving to protect session caching.
* **Object-Oriented Automation Engine:** Structured the core selenium bot within a Python class architecture (`CampusBookingBot`) to cleanly manage state and isolate browser process variables.
* **Network & Timeout Resilience:** Replaced rigid, blind sleep cycles with Selenium `WebDriverWait` and `Expected Conditions` (EC) to handle campus network delays and portal timeouts dynamically.
* **Decoupled Security Protocol:** Separated sensitive student authentication credentials from the runtime logic, storing profiling configurations locally inside an independent JSON structure to allow for safe public deployment.
* **System-Level Deployment Optimization:** Developed an absolute-path-mapped Bash script (`deploy.sh`) to seamlessly configure system background chron-timers on headless Linux environments.

## 📂 System Architecture

```text
.
├── UniMate/              # Main project codebase application container
│   ├── templates/
│   │   └── index.html   # Responsive web dashboard UI & asynchronous fetch forms
│   ├── app.py           # Flask backend API routing and local database handling
│   ├── booking_bot.py   # Object-oriented Selenium browser automation engine
│   ├── config.json      # Local profile storage and historical reservation ledger
│   └── deploy.sh        # Absolute-path-mapped Linux environment scheduler script
└── README.md             # Project documentation index homepage
```

## 🛠️ Local Installation & Execution

To run and audit this full-stack architecture locally on your machine, follow these configurations:

### 1. Environment Setup
Ensure you have Python installed, clone this repository directory, and install the structural project dependencies using your terminal:
```bash
pip install flask selenium
```

### 2. Launch the Flask Web Server
Navigate your terminal prompt inside the nested `UniMate` application folder and execute the backend engine:
```bash
cd UniMate
python app.py
```
Once initialized, open your web browser and navigate to the local hosting node:
`http://127.0.0.1:5000`

### 3. Execution Dry-Run Verification
Input your profiling preferences into the dashboard grid, hit **Save Profile**, and click **Force Booking Test Run** to programmatically trigger the background automation thread.

