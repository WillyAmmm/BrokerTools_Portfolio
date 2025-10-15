### 🚀 Overview

**Quote Logger** is a Chrome/Edge extension that captures quote rows directly from a customer spot portal you have open, normalizes the data (origin/destination, equipment, miles, stops, dates, rate, status), and syncs it to a centralized Quote Log via an API endpoint.  
It also includes a dedicated **Recents** page to quickly review your latest quotes, search historical ones, and inline-edit status, rate, and notes—while showing total and last-30-day win rates.

---

### 🧩 Problem

Sales teams often bounce across portals to submit quotes and later can’t easily find what was bid, how it’s trending, or whether win rates are improving.  
Manually keeping a spreadsheet updated is error-prone, duplicative, and slow—especially when dozens of bids happen per day.

---

### ⚙️ Solution

- **Capture directly from the active portal tab.** Click *Capture Quotes* in the popup and the extension scrapes the visible table of accepted/submitted bids in the current page context.  
- **Normalize and dedupe.** Each row is parsed into clean fields (date, city/state pairs, equipment class, miles, stops, weight, rate, status) and deduped by Load ID.  
- **Sync to your Quote Log.** The extension POSTs a concise JSON payload (one object per quote) to your endpoint.  
- **Workflows on the Recents page.** Open *Recents* to view your 10 most recent quotes, search historical quotes, and inline-edit *Status*, *Rate*, and *Notes*. One click saves patches back to the log.  
- **Visibility.** The footer shows your **Total** and **Last 30 Days** win-rate snapshots so screenshots tell the right story without exposing sensitive data.

---

### 🔍 How It Works (Under the Hood)

1. **Popup initiation.** From the popup, *Capture Quotes* runs a small scraper inside the active tab’s frames using `chrome.scripting.executeScript`. It targets the live table and extracts structured values (Load ID, timestamps, origin/destination, equipment, miles, stops, weight, rate, status).  
2. **Parsing & mapping.** Utilities normalize text, numbers, and dates; equipment types are mapped to a consistent set; and status strings are mapped to Pending/Won/Lost/Ended. Results are deduped by Load ID.  
3. **Sync.** The popup sends an array of rows to your Apps Script endpoint as JSON. The response can include counts of added rows, status updates, and rate changes; a desktop notification summarizes the outcome.  
4. **Recents window.** Clicking *View Recent Quotes* opens `recent.html` in a popup window. It loads the latest 10 records for the selected team/employee and renders editable rows (status, rate, notes). Saving sends only changed fields (patches) back to the endpoint.  
5. **Search & win-rates.** The Recents view can fetch the full dataset in the background to power filters (Customer, Origin State, Destination State, Equipment). It computes overall and last-30-days win-rate from the filtered set and displays both.  

> **Teams & Theme:** A segmented control slider switches between teams or employees. Theme toggles (☀️/🌙) persist across popup and Recents.

---

### 📄 Data Model (examples)

Each captured quote is normalized into fields like:

- `Date`, `Timestamp`, `Team`, `Customer`  
- `LoadID` (unique key for de-dupe)  
- `Origin City`, `Origin State`, `Destination City`, `Destination State`  
- `Equipment Type`, `Stops`, `Miles`, `Weight`  
- `Pickup Date`, `Delivery Date`  
- `Rate`, `Status` (Pending/Won/Lost/Ended), `Notes`

The popup POSTs full rows on capture; the Recents UI POSTs minimal “patches” (only fields that changed).

---

### 🖥️ UI Highlights

- **Popup:** Team/employee segmented control, one-click *Capture Quotes*, quick link to *View Recent Quotes*, live status, and theme toggle.  
- **Recents:** Grid of latest quotes with inline editors; expandable search panel for historical querying; sticky footer with win-rates and Save button; loading overlay for clarity on long fetches.

---

### 🧠 Impact

- **Single source of truth** for quotes across portals  
- **Faster updates** (inline edit status/rate/notes, no spreadsheet wrangling)  
- **Immediate visibility** into win-rates for both all-time and last-30-days  

---

### 🧰 Tech & Tools

**Languages & APIs:** JavaScript (MV3), Chrome Extensions API (`storage`, `scripting`, `activeTab`, `windows`, `notifications`)  
**Architecture:** Popup (capture/launch), Recents window (search/edit), content injection for scraping, JSON POST/GET to endpoint  
**UI:** HTML/CSS with light/dark themes, segmented controls, accessible controls and loading states  
**Permissions/Hosts:** Extension storage; host access for your quoting portal and API endpoint (configured in `manifest.json`)  
**Version:** 1.0.3 (2025)

---

### ⚠️ Disclaimer

All tools and code shown here were independently developed and are the sole property of the author.  
No proprietary or confidential data from any employer is included.
