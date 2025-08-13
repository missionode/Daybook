# Daybook
A minimal, responsive day-planner that feels like a diary: drag &amp; resize tasks on a vertical timeline, quick search with “Next” navigation, Sunday/ custom holidays, auto-postpone unfinished tasks, and share-out. Data lives locally (localStorage) with an optional remembered auto-backup to a chosen .json file via the File System Access API.

**Day Planner — Minimal**
A lightweight, single-file day planner with a draggable timeline, smart title generation, search with next-match, holidays, auto-postpone, and local backup that remembers your chosen file across reloads.

**Highlights**
🗓 Today-first UI with prev/next and date picker

🧲 Drag & drop tasks; resize by handle; snap to slot minutes

🕘 12/24-hour clock, configurable workday + slot size

🔍 Search by title + Next ▶ to jump through multiple matching days

✅ Complete checkbox (completed tasks fade)

🚫 Holiday/Off day: Sundays by default + manual toggle; adding disabled on holidays

⏭ Auto-postpone yesterday’s unfinished tasks → next least-busy future day and first free slot

↗ Share (native share when available, fallback dialog to copy/download)

💾 Local storage + Auto-backup to a file (File System Access API)

Remembers your chosen backup file using IndexedDB; auto-saves on every change

📱 Responsive: two-row header on small screens, single row on large

🧪 Built-in console tests for key behaviors

**Quick start**
Save the HTML file as index.html.

Open in a modern Chromium browser (Chrome/Edge).

Works in Safari/Firefox too, but auto-backup (File System Access API) might be limited; Export/Import still work.

Tip: For a more “app-y” feel, install as a shortcut (Chrome: ⋮ → Save & share → Create shortcut).

**Using the app**
Add & edit tasks
Double-click the timeline to create a task at that time.

Drag a task to move; drag the bottom handle to resize.

Click a task to edit; mark Completed to fade it out.

**Search**
Type a title in Search → Enter to jump to the first matching day.

If multiple matches exist, Next ▶ cycles through days (wraps around).

**Holidays**
Sundays are holidays by default.

Toggle Holiday to mark/unmark the current day.

On holidays, adding new tasks is disabled.

**Auto-postpone**
On first load of a new day, any unfinished tasks from yesterday are automatically moved to:

A future day (within 14 days) with the least pending tasks, then

The first free slot that fits the duration.

**Share**
Click Share. If native share is available, it’s used; otherwise a dialog opens to copy or download a .txt.

**Preferences**
Workday start/end

Slot minutes (snap size)

Clock (12/24-hour)

**Backup (see next section)**

**Data & Backup**
Where data lives
Primary: localStorage (per-browser, per-device).

Backup: optional .json file you choose once.

Auto-backup (remembered)
Open Preferences → Backup → Choose backup file…

Grant permission → Auto-save turns on and is remembered across reloads via IndexedDB.

On each change, the app writes the current state to that file.

If you clear site data/cache, or move the file, the browser forgets access. Just choose the file again to resume.

**Manual backup**
Export .json (download current state)

Import .json (merge or replace)

**Known limitations**
File System Access API is best supported on Chromium. Safari/Firefox may require manual Export/Import.

Clearing site data removes the remembered file handle. You’ll be prompted to pick it again (by design).

**Keyboard & gestures**
Double-click timeline → new task at clicked time

Drag task → move; drag bottom edge → resize

Enter in Search → go to first match

Next ▶ → cycle to next matching day

**Built-in tests**
Open DevTools Console; you’ll see [TEST] logs verifying:

smartTitleFrom edge cases (quotes, punctuation, whitespace, length cap)

Search sorting and next-cycle

**Free-slot finder**

Backup payload shape and IndexedDB write

**Troubleshooting**
Search Next not visible → Only one match exists for that query.

Share doesn’t open → Your browser blocks navigator.share; use the fallback dialog.

Auto-backup didn’t resume → You cleared site data or the file moved. Open Preferences → Choose backup file… again.

Holiday banner everywhere → Only shows on Sundays and days you toggled; ensure your system date/time is correct.

**Roadmap (optional)**
Google Sheets sync (serverless Apps Script)

Keyboard shortcuts (Prev/Next day, New task)

Overlap visualization for concurrent tasks

License
MIT — do whatever, just keep attribution.
