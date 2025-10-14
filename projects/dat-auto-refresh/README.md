\# DAT Auto Refresh – BrokerTools Extension



!\[DAT Auto Refresh Screenshot](../../assets/dat-auto-refresh-ui.png)

!\[Demo GIF](../../assets/dat-auto-refresh-demo.gif)



\[▶️ Watch high-def demo (MP4)](../../assets/dat-auto-refresh-demo.mp4)



---



\### 🚀 Overview

\*\*DAT Auto Refresh\*\* is a Chrome/Edge extension built to eliminate manual refresh tasks on the DAT Loadboard.  

It automatically detects when load posts are nearing expiration and triggers API-based refreshes behind the scenes — keeping brokers’ loads visible and current without them having to touch a thing.



---



\### 🧩 Problem

Before this extension, brokers manually refreshed their DAT postings every 15 minutes to stay visible in search results.  

That repetitive task wasted time each day and created inconsistency — if someone got busy or forgot, their posts went stale and visibility tanked.



---



\### ⚙️ Solution

The extension monitors the live DAT grid inside the browser and automatically performs refreshes based on post timers.  

It hooks into DAT’s own `queueToRefresh` API (via a local script bridge) and smartly adjusts its schedule so refreshes always happen at the optimal time.



It also features:

\- \*\*Smart timing logic\*\* – waits for the longest active timer before refreshing, plus buffer time.  

\- \*\*Retry \& error recovery\*\* – handles API hiccups gracefully with short retry loops.  

\- \*\*Visual status panel\*\* – in the popup, users can toggle Auto Refresh, view next refresh time, and track total refresh count.  

\- \*\*Dark mode support\*\* – clean, modern popup UI with a sun/moon toggle that persists your theme.  

\- \*\*Silent operation\*\* – can refresh even when the DAT tab is minimized or backgrounded.



---



\### 🔍 How It Works (Under the Hood)

1\. \*\*`content.js`\*\* injects an invisible script (`pageBridge.js`) into DAT’s SPA. This script safely captures the authentication token used by DAT’s internal API.  

2\. When triggered, the background service worker (`background.js`) tells the content script to call DAT’s `queueToRefresh` endpoint directly, passing active post IDs.

3\. After a successful API response, the extension quietly repaints the grid using Angular’s internal selectors — no page reload needed.

4\. The cycle repeats every ~15 minutes, or sooner if the UI signals posts have aged early.

5\. State (like dark mode, count, delay timers) is synced through `chrome.storage.local`, so everything stays consistent across sessions.



This entire system works \*without touching\* the user’s credentials, DOM manually, or requiring the DAT tab to stay in focus.



---



\### 🧠 Impact

\- \*\*Eliminated\*\* the need for manual loadboard refreshes.  

\- \*\*Improved visibility\*\* and posting uptime on DAT, helping maintain top-of-board positioning.  

\- \*\*Reduced fatigue\*\* and user errors caused by repetitive refresh habits.  

\- \*\*Allowed brokers to keep their boards fresh without being tied to a computer\*\*, ensuring consistent visibility even while multitasking or away from the desk.



---



\### 🧰 Tech \& Tools

\*\*Languages \& APIs:\*\* JavaScript (MV3), Chrome Extensions API, async messaging, `chrome.alarms`, `chrome.tabs`, and `chrome.runtime` messaging.  

\*\*UI:\*\* HTML/CSS with light/dark themes, custom switches, and sun/moon toggle.  

\*\*Architecture:\*\* Background service worker + content script + injected bridge.  

\*\*Version:\*\* 3.4.2 (2025):contentReference\[oaicite:0]{index=0}  



---



\### ⚠️ Disclaimer

All tools and code shown here were independently developed and are the sole property of the author.  

No proprietary or confidential data from any employer is included.



