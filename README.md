# 🚀 XLSX-Progress-Tracker

**XLSX-Progress-Tracker** is a **lightweight Node.js server** built with **Express** that allows users to upload, manage, and track the reading progress of Excel files (XLSX). It provides a simple API to handle file uploads, retrieve file data, and maintain persistent reading states with row-specific comments.

---

## ✨ Key Features

* **File Uploads** – Users can upload XLSX files, which are securely stored in the dedicated `uploads` folder.
* **Persistent Progress Tracking** – Track which rows of an XLSX file have been read. Progress data and comments are stored in a persistent JSON file (`read-progress.json`) without requiring a database.
* **Row-Level Annotations** – Users can attach **comments** to specific rows of the uploaded Excel file.
* **Simple & Extensible API** – Built with **Express** and configured with **CORS** for seamless cross-origin support, utilizing **Multer** for robust file upload handling.
* **Zero Database Dependency** – File uploads and read progress data are stored directly in server directories (`uploads` and `data`), making setup quick and simple.

---

## 🛠️ Tech Stack

* **Backend:** Node.js, Express.js
* **File Handling:** Multer (for robust file uploads)
* **Utility:** CORS (for cross-origin support), File system (`fs`) for persistent data storage

---

## 🎯 Use Case

This solution is **ideal** for applications where multiple users need to review, annotate, or collaboratively track progress on Excel files. Examples include:

* Internal team dashboards for data review.
* Educational tools requiring line-by-line file annotation.
* Simple data-driven collaboration platforms.

---

## 💻 Getting Started (Local Development)

### 1. Installation

1.  **Clone the repository:**
    ```bash
    git clone <repository-url>
    cd XLSX-Progress-Tracker
    ```
2.  **Install dependencies:**
    ```bash
    npm install
    ```

### 2. Running the Server

* **Start the server:**
    ```bash
    node index.js
    ```
* **Access the API:** The server will be accessible at: `http://localhost:3000`

---

## 📦 Standalone Executable Version

This project can be packaged as a standalone executable using the [`pkg`](https://www.npmjs.com/package/pkg) utility, eliminating the need to have Node.js installed on the host machine.

The build process generates platform-specific files:

* `index-linux` – Linux executable
* `index-win.exe` – Windows executable
* `index-macos` – macOS executable

**To run the executable:**

```bash
# For Linux
./index-linux
# For macOS
./index-macos
# For Windows
index-win.exe
```


## 🌐 API Endpoints
The base URL for all endpoints is http://localhost:3000.

Method,Endpoint,Description
POST,/upload,Upload a new XLSX file to the server.
GET,/files,Retrieve a list of all uploaded files.
GET,/file/:filename,Serve a specific file for frontend processing.
GET,/read-state/:filename,Get the current reading progress and associated comments for a file.
POST,/read-state/:filename,"Update the reading progress (e.g., mark a row as read) for a file."
POST,/comment/:filename/:rowId,Add or update a comment for a specific row ID.
