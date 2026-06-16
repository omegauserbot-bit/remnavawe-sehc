# 🔑 Sub Link Scraper

A Chrome extension for automated generation, verification, and scraping of URLs in the format `https://sub.[domain.name]/[key]`.

## 📋 Description

This extension is designed for:
- **Generating random keys** (16 characters: A-Z, a-z)
- **Checking link availability** on subdomains
- **Importing and verifying** existing links from a file
- **Collecting statistics** and exporting results

## ✨ Features

### 🎯 Link Generator
- Automatic generation of unique keys
- Link checking every **1 second** (configurable)
- Uses a background tab to bypass CORS and bot blocks

### 📥 Link Import
- Load a list of links from a TXT/CSV file
- Sequential verification of each link
- Supports full URLs (https://...)

### 💾 Export Results
- **output_ok.txt** — working links (non-502 responses)
- **output_err.txt** — links with errors (502, Cloudflare, etc.)
- Download with folder selection

### 📊 Real-time Statistics
- Number of checked links
- Number of found working links
- Number of links with errors
- Current working status

## 📦 Installation

### Method 1: Manual Installation (for development)

1. Download or clone the repository with the extension files
2. Open Chrome and navigate to `chrome://extensions/`
3. Enable **"Developer mode"** (toggle in the top right corner)
4. Click **"Load unpacked"**
5. Select the folder containing the extension files

### Method 2: CRX Installation (if available)

1. Download the `.crx` file
2. Drag and drop it onto the `chrome://extensions/` page

## 🚀 Usage

### Generator Mode

1. Open the extension by clicking its icon in the browser toolbar
2. In the **"Domain"** field, enter the domain (e.g., `domain.name`)
3. Click the **"▶ Start"** button
4. The extension will:
   - Generate random keys
   - Open links in a background tab
   - Determine if the link works or fails
   - Save the results

### Import Mode

1. Prepare a `.txt` file with links (one link per line)
2. Click **"Choose file"** and select your file
3. Click **"▶ Check file"**
4. Wait for the verification to complete

### Exporting Results

- Click **"💾 Download OK"** — saves all working links
- Click **"💾 Download ERR"** — saves all links with errors
- The browser will prompt you to choose a save location

### Stopping and Resetting

- **"⏹ Stop"** — stops the current verification
- **"🗑 Reset"** — clears all statistics and lists

## 📁 Project Structure

```text
sub-scraper/
├── manifest.json       # Extension configuration (Manifest V3)
├── popup.html          # Popup interface UI
├── popup.css           # UI styles
├── popup.js            # UI logic
├── background.js       # Background script (core logic)
└── README.md           # Documentation
