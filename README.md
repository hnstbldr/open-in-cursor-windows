# Open in Cursor (Windows)

Add a safe, user-scoped **"Open in Cursor"** option to the Windows right-click context menu.

This repository provides a small PowerShell script that integrates the Cursor editor into Windows Explorer in a way that is intentionally conservative and reversible.

---

## What this does

The script adds an **"Open in Cursor"** entry to the right-click menu for:

- Folder backgrounds (right-click empty space inside a folder)
- Folders
- Files

It opens the selected path directly in Cursor.

---

## Design goals

This project is intentionally minimal and safety-focused.

- **User-scoped only**  
  Writes exclusively to `HKCU\Software\Classes` (no system-wide changes).

- **No administrator privileges required**  
  Runs in a standard PowerShell session.

- **Registry backups**  
  Any existing keys touched by the script are backed up before modification.

- **Clean uninstall**  
  All changes can be removed cleanly.

- **No Cursor configuration changes**  
  This script only adds a context menu entry. It does not modify Cursor itself.

---

## Requirements

- Windows 10 or Windows 11
- Cursor installed locally

---

## Installation

1. Clone or download this repository.
2. Open PowerShell.
3. Run the installer script:

```powershell
.\install-open-in-cursor.ps1
