# BrokerTools Portfolio

I build automation and analytics tools that make brokerages more efficient and less chaotic.

Everything here started as a real-world problem on the floor — slow quoting, stale load posts, replying to hundreds of carrier emails — and turned into working solutions I coded myself.

This repo showcases those projects with short summaries, screenshots, and demos, plus deeper breakdowns for anyone who wants to see what’s happening behind the scenes.

## 🚛 DAT Auto Refresh (BrokerTools)

![Screenshot](assets/dat-auto-refresh-ui.png)

![Demo GIF](assets/dat-auto-refresh-demo-gif.gif)

[▶️ Watch high-def demo (MP4)](assets/dat-auto-refresh-demo.mp4)

**Problem:** Brokers manually refreshed DAT Loadboard posts every 15 minutes, wasting time if loads weren't refreshed or tanking visibility.  
**Solution:** Built a Chrome/Edge extension that detects aging posts and auto-refreshes them using DAT’s own API.  
**Impact:** Kept brokers’ loads visible and competitive by automatically refreshing posts before they expired — no more missed trucks due to stale listings.

Features include:
- Smart refresh timing  
- Retry/recovery logic  
- Clean modern popup with dark mode toggle  
- Full background operation (even when the DAT tab is hidden)

**Tech:** JavaScript (MV3), Chrome Extensions API, async messaging, HTML/CSS UI  

🧩 [Read full project details →](projects/dat-auto-refresh/README.md)

### ⚠️ Disclaimer

All tools and code shown here were independently developed and are the sole property of the author.  
No proprietary or confidential data from any employer is included.
