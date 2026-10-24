# Privacy

Skontz Control System works on your PC and **does not collect data about you or your PC**. There is no advertising, no
usage analytics and no account. The only thing it can send on its own is an **optional, cleaned plain-text error report**,
and only if you turn that on.

## What the app connects to

- **GitHub (this repository)**: a read-only request for the signed version list, to tell you when a new version exists. No
  information about you or your PC is included. You can switch the start-up check off in Settings > Updates.
- **The error report receiver** (`skontz-reports.skontz-app.workers.dev`): only if you turned error reports on (below).
- **The Dashboard check-up**, when it opens: a connectivity test with one small connection to Cloudflare (1.1.1.1) and Google (8.8.8.8)
  public DNS and one name lookup. Nothing about your PC is sent.
- **Only when you ask for it**: Microsoft's `winget` and the catalogs it uses (Install apps), Cloudflare's public speed-test servers
  (Speed test), and the download sources of tools you choose to enable (for example the FPS meter or the sensor driver).

## Error reports (optional, off by default)

- **Off by default.** You can turn them on in the first-run screen ("Help fix errors (optional)", which starts on "Not now")
  or in **Settings > Privacy and reports > Send error reports**. The same switch turns them off at once. Errors from before
  you turned it on are not sent automatically.
- **What is sent:** a short block of plain text (JSON) with a fixed list of fields and nothing else: a format number, a random
  report id, a random install id (created when you turn reports on; not linked to you or your PC), the time, the app version
  and build, the app language, the Windows edition/build, the processor type, the memory size rounded to a power of two, the
  number of processor threads, whether the app runs as administrator and whether it is the installed version, and up to 20
  errors. Each error has its type, a cleaned message (at most 1000 characters), where the app caught it (with the app page and
  long action that were open and the minutes since start), its time, a short code for the error, and the names and line
  numbers of the app's **own** code files. Unexpected closes (a crash, or the app being ended from outside) are reported the
  same way; Windows shutting down, closing the app and updates are not counted.
- **Cleaned on your PC first:** your user name, computer name, folders and file paths, SIDs, GUIDs, e-mail, IP and MAC
  addresses, passwords inside web addresses and long tokens are removed before anything leaves your PC.
- **Never sent:** files of any kind, file contents or names, screenshots, what you type, the clipboard, browsing history, the
  list of installed programs or running processes, network settings, product keys or serial numbers.
- **See it first:** "View what will be sent" shows the exact text; "Send report now" sends only when you press Send.
- **Limits:** at most one report per error per day and 20 per week. Unsent reports wait in
  `C:\ProgramData\SkontzControl\report_queue` as plain text you can open.
- **On the receiver:** HTTPS only. It accepts only that exact format, stores it as text for 90 days and never opens, runs or
  follows anything inside a report. Your IP address is used only for a moment to limit abuse and is not stored.
- **Delete:** "Delete my data" turns reports off and deletes the install id and any waiting reports on your PC; it shows your
  old id, which you can send to the maintainer to delete reports already received before the 90 days.

## Report text you can copy

**Settings > Privacy and reports > View report text** shows a short plain-text report on screen (version, Windows, the last few
errors, cleaned the same way). Read it first; if you want to share it, press **Copy** and paste the text into a message. No file
is created and nothing leaves your PC. Please **never send files to anyone**: unknown files are a common way to attack people.
Files the app can save for you (the hardware sheet, the packet-loss CSV) are for your own use only.

## Local data

Settings, the history of changes, test results and the error log stay in `C:\ProgramData\SkontzControl` on your PC (only
administrators can change that folder). While the app runs it also keeps a small `running.marker` and a `native_crash.txt` there
to recognize an unexpected close; both are deleted when it closes normally. Uninstalling offers to delete everything.
