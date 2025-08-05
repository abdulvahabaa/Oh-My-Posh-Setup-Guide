# 🚀 Oh My Posh Setup Guide for PowerShell & VS Code

This guide walks you through setting up **Oh My Posh** in **PowerShell** and customizing it for an awesome developer experience in **Windows Terminal** and **VS Code**.

---

## ✅ Step 1: Check if `winget` is Installed

### 🔍 Test if winget is available

Open PowerShell and run:

```powershell
winget --version
```

### ✅ If You See a Version Number

Example output:

```
v1.11.400
```

🎉 Great! `winget` is installed. You can continue with the guide.

---

### ❌ If You Get an Error Like:

```
winget : The term 'winget' is not recognized as the name of a cmdlet...
```

This means `winget` is **not installed** on your PC.

## Install `winget` (Recommended)

### 📝 Requirements

- Windows 10 (Version **1709** or later) or Windows 11
- App Installer package from Microsoft Store

### 📦 Install App Installer (includes winget)

1. Open **Microsoft Store**.
2. Search for **App Installer**.
3. Click **Install** or **Update**.

📥 Or download directly: [App Installer – Microsoft Store](https://apps.microsoft.com/store/detail/app-installer/9NBLGGH4NNS1)

After installing, restart PowerShell and try:

```powershell
winget --version
```

---

## ✅ Step 2: Update Winget

Make sure **Winget** is up to date:

```powershell
winget update
```

Upgrade all installed packages:

```powershell
winget upgrade --all
```

---

## ✅ Step 3: install the latest powershell

Search for the latest version of PowerShell

```powershell
winget search Microsoft.PowerShell
```

Output

```
Name               Id                           Version Source
---------------------------------------------------------------
PowerShell         Microsoft.PowerShell         7.5.2.0 winget
PowerShell Preview Microsoft.PowerShell.Preview 7.6.0.4 winget
```

Install PowerShell using the `id` parameter

```powershell
winget install --id Microsoft.PowerShell --source winget
```

---

## 🎨 Step 4: Install Oh My Posh

Install **Oh My Posh** via Winget:

```powershell
winget install JanDeDobbeleer.OhMyPosh --source winget --scope user --force
```

#### 🔁 After installation, close and restart PowerShell to apply changes and avoid any startup errors.

📖 Official Docs: [Oh My Posh Installation Guide](https://ohmyposh.dev/docs/installation/windows)

---

## 🔤 Step 5: Install Nerd Fonts

Install the fonts required for your theme (this includes glyphs/icons):

```powershell
oh-my-posh font install
```

👉 Recommended: **FiraCode Nerd Font**

---

## 🖋 Step 6: Set Up Windows Terminal

Open Windows Terminal settings (`Ctrl + ,`) and configure your defaults:

```json
"defaults": {
    "colorScheme": "One Half Dark",
    "font": {
        "face": "FiraCode Nerd Font Mono",
        "size": 14
    }
}
```

This ensures the new font is used for all shells.

---

## 📝 Step 7: Configure PowerShell Profile

### Check which shell you’re using:

```powershell
oh-my-posh get shell
```

### Open your PowerShell profile:

```powershell
notepad $PROFILE
```

If the profile doesn’t exist, create it:

```powershell
New-Item -Path $PROFILE -Type File -Force
```

---

## 🎨 Step 8: Choose and Apply a Theme

### 🔎 1. Browse and Pick a Theme

Go to the official theme gallery:

👉 [Oh My Posh Themes](https://ohmyposh.dev/docs/themes)

Click on any theme to preview it.

---

### 📥 2. Download the Theme JSON File

To download your chosen theme from GitHub:

1. On the theme page, click **“View JSON”** to open its configuration file on GitHub.
2. In the GitHub view, click the **Raw** button in the top right.
3. Right-click on the page and select **Save As...** (or press `Ctrl+S`).
4. Save the file in a folder, e.g.:
    
    ```
    C:\Users\<username>\Documents\PowerShell\
    ```
    
5. Rename the file if needed, e.g., `mytheme.omp.json`.

---

### 📝 3. Update PowerShell Profile

In your PowerShell profile (`notepad $PROFILE`), add the following line (replace `<username>` and `<themename>`):

```powershell
oh-my-posh init pwsh --config "C:\Users\<username>\Documents\PowerShell\<themename>.omp.json" | Invoke-Expression
```

---

## 🔄 Step 9: Reload Profile

Apply your changes:

```powershell
. $PROFILE
```

Now, restart your terminal to see the new prompt! 🎉

---

## 💻 Step 10: VS Code Integration (Optional)

👉 **If you are using Visual Studio Code**, follow these steps to apply the same beautiful prompt in VS Code’s terminal.

👉 If not, you can skip to the **Final Result** section.

### 🛠 VS Code Terminal Setup

1. Open **VS Code settings** (`Ctrl + ,`).
2. Search for “terminal font family” and set it to your Nerd Font, e.g.:

```json
"terminal.integrated.fontFamily": "FiraCode Nerd Font Mono",
"terminal.integrated.fontSize": 14
```

1. Make sure your default shell in VS Code is PowerShell.

Now your integrated terminal in VS Code will look just like Windows Terminal.

---

## 🎯 Final Result

You now have a **stylish, functional PowerShell prompt** in both **Windows Terminal** and **VS Code**, powered by **Oh My Posh** and Nerd Fonts.

---

## 📌 Resources

- 🪟 [Installing PowerShell on Window](https://learn.microsoft.com/en-us/powershell/scripting/install/installing-powershell-on-windows?view=powershell-7.5)
- 🌐 [Oh My Posh Documentation](https://ohmyposh.dev/docs)
- 🎨 [Oh My Posh Themes Gallery](https://ohmyposh.dev/docs/themes)
- 💾 [Oh My Posh GitHub Repository](https://github.com/JanDeDobbeleer/oh-my-posh)
- 📥 [App Installer (Winget) – Microsoft Store](https://apps.microsoft.com/store/detail/app-installer/9NBLGGH4NNS1)
