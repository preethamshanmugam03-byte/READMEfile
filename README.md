# SOAP Test Launcher - Chrome Extension

## 1. Purpose

The **SOAP Test Launcher** Chrome extension is used to simplify the process of starting SOAP multiset tests through Jenkins.

Instead of manually opening each Multiset Jenkins job and triggering it separately, the extension allows you to:

1. Select the required SOAP test path.
2. Open the corresponding Jenkins Orchestrator.
3. Select the required environment, where applicable.
4. Click **Build**.
5. Let the Jenkins Orchestrator trigger the required Multiset jobs.
6. Automatically open the relevant Multiset Jenkins pages in separate browser tabs.

The extension uses your existing Jenkins browser session. No Jenkins credentials are stored inside the extension.

---

## 2. Prerequisites

Before using the extension, make sure you have:

- Google Chrome installed.
- Access to the required Jenkins/CloudBees CI environment.
- Permission to access the SOAP Multiset Jenkins jobs.
- The SOAP Test Launcher extension files, either:
  - As a ZIP file provided by the team, or
  - From the GitHub repository.

---

## 3. Install the Extension from a ZIP File

If you received the extension as a ZIP file:

### Step 1: Download the ZIP file

Download the ZIP file provided by the team and save it somewhere on your Windows computer.

For example:

```text
C:\Users\<YourUsername>\Downloads\SOAP-Test-Launcher.zip
```

### Step 2: Extract the ZIP file

Right-click the ZIP file and select:

**Extract All...**

Choose a location where you want to keep the extension.

For example:

```text
C:\Users\<YourUsername>\Documents\SOAP-Test-Launcher\
```

After extraction, make sure the folder contains the following files:

```text
Chrome-Extension/
├── manifest.json
├── popup.html
├── popup.js
├── background.js
└── content.js
```

The important point is that these files should be directly inside the folder that you select when loading the extension into Chrome.

---

## 4. Download the Extension from GitHub

The extension is also available in the project's GitHub repository.

Repository:

`<YOUR-GITHUB-REPOSITORY-URL>`

The repository contains the following structure:

```text
SOAP-Test-Automation/
├── Jenkins/
│   ├── Path1/
│   │   └── Jenkinsfile
│   ├── Path2/
│   │   └── Jenkinsfile
│   └── Path3/
│       └── Jenkinsfile
│
└── Chrome-Extension/
    ├── manifest.json
    ├── popup.html
    ├── popup.js
    ├── background.js
    └── content.js
```

### Step 1: Open the repository

Open:

`<YOUR-GITHUB-REPOSITORY-URL>`

### Step 2: Download the repository

Use the GitHub **Code** option and download the repository as a ZIP file.

### Step 3: Extract the ZIP file

Extract the downloaded ZIP file to a location on your Windows computer.

For example:

```text
C:\Users\<YourUsername>\Documents\SOAP-Test-Automation\
```

### Step 4: Locate the extension folder

Inside the extracted repository, open:

```text
SOAP-Test-Automation
    └── Chrome-Extension
```

This is the folder that should be loaded into Chrome.

---

## 5. Verify the Extension Files

Before loading the extension, make sure the `Chrome-Extension` folder contains exactly these required files:

```text
Chrome-Extension/
├── manifest.json
├── popup.html
├── popup.js
├── background.js
└── content.js
```

Do not select an individual file.

You will select the **Chrome-Extension folder** when loading the extension into Chrome.

---

## 6. Add the Extension to Google Chrome

### Step 1: Open Chrome Extensions

In Google Chrome, open:

```text
chrome://extensions
```

### Step 2: Enable Developer Mode

Turn on **Developer mode**.

### Step 3: Load the extension

Click:

**Load unpacked**

### Step 4: Select the extension folder

Navigate to the location where you extracted the files.

Select:

```text
Chrome-Extension
```

Then click **Select Folder**.

Chrome should now load the SOAP Test Launcher extension.

### Step 5: Verify the extension

You should see the extension listed in the Chrome Extensions page.

You can also use the Chrome Extensions toolbar/puzzle icon to access the extension.

---

## 7. First-Time Setup

After installing the extension:

1. Make sure you are logged in to Jenkins/CloudBees CI in Chrome.
2. Make sure you can access the required Jenkins Multiset jobs manually.
3. Open the SOAP Test Launcher extension.
4. You should see three options:

```text
🚀 Path 1 - ST1 / PERF
🚀 Path 2 - ST2
🚀 Path 3 - IA / MO
```

Select the path that you want to execute.

---

## 8. How to Run Path 1

Path 1 supports:

- `ST1`
- `PERF`

### Step 1

Open the SOAP Test Launcher extension.

Click:

**🚀 Path 1 - ST1 / PERF**

The corresponding Jenkins Orchestrator page will open.

Jenkins URL:

`<PATH1-JENKINS-ORCHESTRATOR-URL>`

### Step 2

On the Jenkins **Build with Parameters** page, select the required environment:

```text
ST1
```

or

```text
PERF
```

### Step 3

Click **Build**.

### Step 4

The Jenkins Orchestrator will trigger the required Multiset jobs in parallel.

#### ST1

For `ST1`, all seven Multisets are triggered:

```text
Multiset1
Multiset2
Multiset3
Multiset4
Multiset5
Multiset6
Multiset7
```

#### PERF

For `PERF`, the following Multisets are triggered:

```text
Multiset2
Multiset4
Multiset5
Multiset6
Multiset7
```

`Multiset1` and `Multiset3` are not triggered for `PERF`.

### Step 5

The extension detects the new Orchestrator build and opens the relevant Multiset Jenkins pages in separate tabs.

---

## 9. How to Run Path 2

Path 2 supports:

- `ST2`

### Step 1

Open the SOAP Test Launcher extension.

Click:

**🚀 Path 2 - ST2**

The corresponding Jenkins Orchestrator page will open.

Jenkins URL:

`<PATH2-JENKINS-ORCHESTRATOR-URL>`

### Step 2

Click **Build** on the Jenkins page.

Path 2 does not require you to select an environment because it uses `ST2`.

### Step 3

The Jenkins Orchestrator triggers all seven Multisets in parallel:

```text
Multiset1
Multiset2
Multiset3
Multiset4
Multiset5
Multiset6
Multiset7
```

### Step 4

The extension detects the new Orchestrator build and opens the seven relevant Multiset Jenkins pages in separate tabs.

---

## 10. How to Run Path 3

Path 3 supports:

- `IA`
- `MO`

### Step 1

Open the SOAP Test Launcher extension.

Click:

**🚀 Path 3 - IA / MO**

The corresponding Jenkins Orchestrator page will open.

Jenkins URL:

`<PATH3-JENKINS-ORCHESTRATOR-URL>`

### Step 2

On the Jenkins **Build with Parameters** page, select:

```text
IA
```

or

```text
MO
```

### Step 3

Click **Build**.

### Step 4

The Jenkins Orchestrator triggers the required Multiset jobs in parallel.

#### IA

For `IA`, the following Multisets are triggered:

```text
Multiset2
Multiset3
Multiset4
Multiset5
Multiset6
```

`Multiset1` and `Multiset7` are not triggered for `IA`.

#### MO

For `MO`, all seven Multisets are triggered:

```text
Multiset1
Multiset2
Multiset3
Multiset4
Multiset5
Multiset6
Multiset7
```

### Step 5

The extension detects the new Orchestrator build and opens the relevant Multiset Jenkins pages in separate tabs.

---

## 11. What Happens After Clicking Build

The overall flow is:

```text
Chrome Extension
       |
       v
Select SOAP Test Path
       |
       v
Jenkins Orchestrator
       |
       v
Select Environment
       |
       v
Click Build
       |
       v
Jenkins Orchestrator
       |
       v
Trigger Required Multisets in Parallel
       |
       v
Chrome Extension Detects New Build
       |
       v
Open Required Multiset Jenkins Tabs
```

The extension determines which Multiset tabs to open based on the selected path and environment.

### Important

The extension does **not** wait for every Multiset test to finish.

It only:

1. Detects the new Orchestrator build.
2. Determines which Multisets should run.
3. Opens the corresponding Jenkins pages.

If a Multiset test fails, it can be manually retriggered from its Jenkins page.

---

## 12. Important Usage Rules

### 1. Keep Jenkins logged in

Make sure you are already logged in to the required Jenkins/CloudBees CI environment in Chrome.

### 2. Use the extension to start the Orchestrator

Use the appropriate button in the SOAP Test Launcher instead of manually navigating to the Orchestrator whenever possible.

### 3. Select the correct environment

For paths that provide environment selection, make sure the correct environment is selected before clicking **Build**.

### 4. Do not click Build multiple times unintentionally

Each new Orchestrator build represents a new test execution.

### 5. Allow the extension to open the Multiset tabs

After the Orchestrator build starts, the extension monitors the Jenkins page and opens the relevant Multiset pages when a new build is detected.

### 6. If a test needs to be rerun

You can manually rerun the required Multiset from its Jenkins page.

---

## Quick Reference

| Path | Environment | Multisets Triggered |
|------|-------------|---------------------|
| Path 1 | ST1 | M1, M2, M3, M4, M5, M6, M7 |
| Path 1 | PERF | M2, M4, M5, M6, M7 |
| Path 2 | ST2 | M1, M2, M3, M4, M5, M6, M7 |
| Path 3 | IA | M2, M3, M4, M5, M6 |
| Path 3 | MO | M1, M2, M3, M4, M5, M6, M7 |
