# Complete_OS
A lightweight, user-friendly HTA-based post-install setup wizard for custom Windows 10 builds. Features browser selection, BitLocker toggling, and a modern UI
# Complete OS Setup Wizard

A lightweight and modern **Post-Install Wizard (OOBE)** written in HTML/HTA for custom Windows 10 deployments.
Designed for **Complete OS** — a privacy-focused, lightweight Windows build project.

## 🚀 Features

*   **User-Friendly UI:** Modern, clean interface using CSS (no external assets required).
*   **Browser Selection:** Let users choose their preferred browser (Chrome, Firefox, or skip).
*   **Security First:** One-click **BitLocker encryption** setup (checks for TPM).
*   **Lightweight:** Pure HTML/JS/VBScript. No .NET or heavy frameworks needed.
*   **Offline Ready:** Works completely offline during the first system boot.

## 🛠 How to Use in Your Build

1.  Place `CompleteOS.hta` in your ISO image structure:
    `sources\$OEM$\$1\SecurityTools\CompleteOS.hta`

2.  Add a `SetupComplete.cmd` script to run it automatically after installation:
    `sources\$OEM$\$$\Setup\Scripts\SetupComplete.cmd`

    ```
    @echo off
    reg add "HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\RunOnce" /v "CompleteOSSetup" /t REG_SZ /d "mshta.exe \"C:\SecurityTools\CompleteOS.hta\"" /f
    ```

3.  Build your ISO and install! The wizard will appear on the first desktop login.

## 📜 Credits

*   **Concept & UI:** Developed for the Complete OS project.
*   **Maku Tweaker:** This project may utilize Maku Tweaker by **Mark Adderley** for system optimization. All rights for Maku Tweaker belong to its original author.
    *   [Mark Adderley's YouTube](https://youtube.com/@MakuAdarii)
    *   [Adderly.Top](https://adderly.top)

## 📄 License

This project is open-source. Feel free to use and modify it for your own custom Windows builds.
