# 📦 BrokerTools - Load Posts Suite

## 🚀 Overview

**BrokerTools** turns the everyday chaos of posting and quoting into a controlled, automated system.
Built entirely in VBA, it bridges Excel and Outlook so brokers can post, track, and reply in seconds — no retyping, no searching for load details, no wasted motion.

The suite serves as the backbone of the Load Posts operation: centralizing load data, automating DAT CSV exports, and powering instant Smart Replies directly from Outlook — keeping communication fast, accurate, and professional.

## 🧩 Problem

Posting and managing freight has traditionally been a slow, manual process. Most brokers still enter load details into DAT one by one, retyping everything from their TMS — a task that takes 3–5 minutes per load and quickly consumes hours of the day. Once the posts go live, they’re often flooded with dozens or even hundreds of carrier emails within minutes. To keep up, many rely on patchwork systems like Excel sheets, Word templates, or copied email drafts. But under that volume, staying organized, responding accurately, and keeping every lane straight becomes nearly impossible. The result is missed details, lost time, and inconsistent communication. BrokerTools eliminates that manual bottleneck — automating posts, replies, and load management so brokers can handle more freight, faster, with total consistency and control.

## ⚙️ Solution

BrokerTools transforms the manual, high-volume chaos of load posting and carrier communication into a streamlined, automated workflow.

- Posting dozens of loads to DAT in minutes, not hours. Instead of typing every load into DAT by hand, brokers can generate a full, ready-to-upload CSV with a single click. The export compiles every uncovered load, formats it for DAT’s uploader, and eliminates the need to re-enter the same details dozens of times.

- Instant, accurate email replies. When carrier emails start flooding in, brokers no longer have to search for or copy load details. Outlook connects directly to the Excel workbook, matching each email to the correct load and sending a perfectly formatted reply in seconds — even across hundreds of messages.

- One source of truth. Excel serves as the command center, maintaining a clean master roster and individual load sheets that feed every export and reply. Whether a load is new, covered, or hidden, the system keeps everything organized and synchronized automatically.

- The result is a fully connected workflow that eliminates manual re-entry, speeds up response times, and gives brokers total control over their freight from a single hub.

Together, these automations eliminate retyping, reduce response times from minutes to seconds, and allow a single broker to handle the volume that once required an entire team.

## 🧰 Key Features

### 🧭 Manual Load Wizard

Step-by-step forms guide brokers through creating loads — equipment, weight, stops, and notes — then automatically generate a formatted load sheet and master-sheet entry with hyperlinks and status tracking.

### 📥 Bulk Add from TMS

Paste raw TMS lane dumps directly into Excel. The importer parses, normalizes, and batches entire lane lists into clean records, ready to review and post — turning 30-minute data entry sessions into a 3-minute process.

### 📊 Master Sheet Automation & Hygiene

Hyperlinks control everything: Copy, Details, Hide, Delete.
Hidden Loads form allows quick restore, while the Orphan Cleaner finds stray sheets or duplicates and safely removes them.

### 📤 DAT Bulk Upload Export

One-click export builds a DAT-formatted workbook using the Uncovered Loads Cache.
It parses stop data, standardizes equipment codes, and creates a CSV-ready DAT sheet instantly — saving 3-5 minutes of manual entry per load.

### 📋 Clipboard & Rate Tools

The Clipboard Utility copies clean, formatted load summaries (label + value pairs) into any app or email.
The Rate Sheet Opener remembers shared network paths for quick access to team rate books.

### ✉️ Smart Bulk Reply Engine

The Smart Bulk Reply Engine turns a flooded inbox into a few simple clicks.
Brokers can select dozens of carrier emails at once, and the system automatically matches each one to the correct load using lane data, city/state keywords, and load numbers. A review form confirms all matches before sending, allowing brokers to verify or manually pair any that don’t auto-detect.

Once confirmed, the engine replies to every selected message — each with a perfectly formatted, load-specific email pulled directly from Excel. What used to take up a significant portion of a broker’s day now happens in just a few minutes.

DNU (Do-Not-Use) carriers are automatically identified and excluded from replies, ensuring no blocked carriers receive load details. The result is an organized, high-volume response system that keeps communication fast, accurate, and effortless — even when handling a hundred quotes at once.

### 🤖 SmartBot Automation

The SmartBot feature brings automation beyond the desk, responding to carrier emails instantly — even when the broker isn’t at their computer.
When enabled, SmartBot watches a dedicated Outlook folder for new messages. Dropping or moving a carrier email into that folder — whether from the desktop app or a phone — triggers a fully automated reply cycle.

SmartBot instantly matches the email to the correct load, verifies the carrier against the DNU list, and sends a complete, formatted load reply pulled directly from Excel. Within seconds, the carrier receives accurate load details with zero manual effort.

Every action SmartBot takes is logged in a Bot Results folder for full transparency and recordkeeping.
The result is an always-on response system that allows brokers to stay responsive and competitive — whether they’re at their desk or on the go.

## 🧹 Installer & Maintenance Tools

A bundled installer handles Outlook macro deployment, backups, and restarts automatically.
The VBA Export Utility snapshots all modules and forms into timestamped folders for versioning and updates.

## 🔍 How It Works (Under the Hood)

- **Excel Core:** Houses all load records, hidden caches, and detail sheets with synchronization events to maintain consistency.
- **Outlook Bridge:** COM automation links Outlook macros to the open workbook, sharing SmartBot states and clipboard data live.
- **Data Handling:** Scripting.Dictionary and RegEx routines power fast lookups and flexible text matching for load numbers and MC detection.
- **Registry Persistence:** Workbook paths, SmartBot toggle, and rate locations persist through Windows registry for seamless startup.
- **Export & Clipboard:** File I/O is minimal — only DAT CSV export, clipboard copy, and registry writes — keeping deployment lightweight.

## 🧠 Impact

BrokerTools transformed how brokers manage their day — replacing hours of typing and tab-switching with a single connected workflow.

- **TMS to DAT in one motion.** Load data flows straight from the TMS into the suite and can be live on DAT within seconds — no manual posting, no re-entry.

- **Inbox under control.** The suite handles hundreds of carrier emails with perfect accuracy, delivering consistent replies and freeing brokers to focus on negotiations instead of copy-paste work.

- **Always responsive.** SmartBot keeps brokers competitive by replying instantly, even while they’re away from the desk.

- **Consistency across the team.** Every message, format, and data point originates from the same verified source — ensuring professional, error-free communication every time.

Together, these outcomes redefine what a single broker can accomplish — enabling speed, precision, and organization at a scale most teams can’t match manually.

## 🖥️ Ease of Use

- Intuitive buttons and wizards — no code knowledge required.
- Confirmation prompts for all irreversible actions.
- Clear progress bars and completion dialogs.
- SmartBot and Quick-Access buttons handle repetitive tasks in a click.
- Works seamlessly from both desktop and mobile Outlook workflows.

## ⚙️ Tech Stack

- **Languages:** VBA (Excel & Outlook)
- **APIs:** Excel/Outlook Object Models, Windows Clipboard API, MSForms
- **Architecture:** Excel + Outlook COM bridge with registry-backed state
- **Data Model:** Structured master table + hidden caches for uncovered/hidden loads
- **File I/O:** CSV export, clipboard write, registry read/write
- **Installer:** Batch-based Outlook deployment with auto-restart

## 📈 Scalability & Maintenance

- Modular VBA structure keeps Excel and Outlook code isolated but connected through COM.
- Deployment only requires updating the shared workbook and rerunning the installer — no manual configuration needed.
- Built-in exporters and orphan cleaners simplify maintenance and repository syncing.

## ⚠️ Disclaimer

All automation systems described here were independently designed and developed by the author.
No proprietary code or data from any employer is included.
