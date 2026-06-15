# Installation Guide

This guide walks you through installing and setting up the **Android UI/UX Upgrade Skill** for VS Code.

## 📥 Installation Methods

### Method 1: VS Code Extensions Marketplace (Recommended)

1. **Open VS Code**
2. **Open the Extensions view**:
   - Windows/Linux: Press `Ctrl+Shift+X`
   - macOS: Press `Cmd+Shift+X`
   - Or click the Extensions icon in the Activity Bar (left sidebar)

3. **Search for "Android UI/UX Upgrade"**

4. **Click the Install button**

5. **Wait for installation to complete** (usually takes 5-10 seconds)

6. **Reload VS Code** (if prompted)

That's it! The skill is ready to use.

---

### Method 2: Manual Installation via .vsix File

If you have a `.vsix` file (extension package):

1. **Download the `.vsix` file**

2. **Open VS Code Extensions view** (`Ctrl+Shift+X`)

3. **Click the "..." menu** in the top-right corner of the Extensions panel

4. **Select "Install from VSIX..."**

5. **Navigate to and select** the `.vsix` file

6. **Wait for installation** and reload VS Code when prompted

---

### Method 3: Installation from Source (For Developers)

If you want to build and test locally:

1. **Clone or download the repository**:
   ```bash
   git clone https://github.com/yourusername/android-ui-upgrade-skill.git
   cd android-ui-upgrade-skill
   ```

2. **Extract the skill file** (it's a ZIP archive):
   ```bash
   # On macOS/Linux
   unzip android-ui-upgrade.skill -d extracted/
   
   # On Windows PowerShell
   Expand-Archive -Path android-ui-upgrade.skill -DestinationPath extracted\
   ```

3. **Install dependencies** (if applicable):
   ```bash
   npm install  # or pip install -r requirements.txt if Python-based
   ```

4. **Load into VS Code as a development extension**:
   - Open VS Code and press `Ctrl+Shift+D` (Debug view)
   - Or use the command palette: `Ctrl+Shift+P` → "Extensions: Show Running Extensions"

---

## ✅ Verify Installation

After installation, verify the skill is working:

1. **Open any file in VS Code** (or create a new one)

2. **Open the GitHub Copilot Chat** (`Ctrl+Shift+I` or `Cmd+Shift+I` on macOS)

3. **Type a message** referencing Android UI/UX issues:
   - "Help me fix my Android app's UI"
   - "Material Design 3 setup"
   - "My app looks terrible"
   - "Accessibility improvements for Android"

4. **The skill should activate** and provide contextual guidance

If you see the skill responding with Android-specific advice, installation is successful! ✨

---

## 🔧 System Requirements

| Requirement | Version |
|-------------|---------|
| **VS Code** | 1.74.0 or later |
| **GitHub Copilot Extension** | Latest stable version |
| **Operating System** | Windows 10+, macOS 10.12+, Linux (Ubuntu 18.04+) |
| **Memory** | 500 MB+ free disk space |
| **Internet** | Required for Copilot functionality |

---

## 🚀 First Use

### **Next Steps After Installation**

1. **Read the Usage Guide**: [docs/USAGE_GUIDE.md](./docs/USAGE_GUIDE.md)
   - Real-world scenarios
   - Example chat interactions
   - User journeys

2. **Try a Quick Example**:
   - Open Copilot Chat (`Ctrl+Shift+I`)
   - Ask one of the example questions below

### **Scenario: Quick Introduction**

Try this first message in Copilot Chat:

```
I'm building an Android app and the UI looks outdated.
Help me understand the main areas that need improvement.
```

**Expected response**: The skill will start with Phase 0 (Triage) and ask diagnostic questions about:
- Target API level
- Current framework (XML Views vs. Jetpack Compose)
- Design system version
- Accessibility needs

---

### **Scenario: Specific Problem**

```
My RecyclerView is laggy when scrolling. How do I optimize it?
```

**Expected response**: The skill will jump to Phase 6 (Performance Quick Wins) and provide:
- Specific RecyclerView optimization code
- Image loading best practices
- Memory management tips

---

## 🛠️ Configuration (Optional)

The skill works out-of-the-box with no configuration. However, you can customize behavior:

### Set Your Preferences

1. **Open VS Code Settings** (`Ctrl+,`)

2. **Search for "copilot"**

3. **Enable/disable skill-specific features** as needed

### Environment Variables (Advanced)

For advanced users, set these environment variables:

```bash
# Example (bash/zsh)
export ANDROID_MIN_SDK=21
export ANDROID_MATERIAL_VERSION=3
export COMPOSE_VERSION=1.5.0
```

---

## ❓ Troubleshooting

### **The skill doesn't appear in Copilot Chat**

1. **Verify installation**:
   - Go to Extensions (`Ctrl+Shift+X`)
   - Search for "Android UI/UX"
   - Confirm it shows as "Installed"

2. **Reload VS Code**:
   - Press `Ctrl+Shift+P` → "Developer: Reload Window"

3. **Check Copilot Chat is active**:
   - Press `Ctrl+Shift+I` to open Copilot Chat
   - Ensure GitHub Copilot extension is enabled

4. **Restart VS Code**:
   - Close and reopen VS Code completely

### **Getting generic responses instead of Android-specific guidance**

- Make sure your message contains **Android-specific keywords**:
  - "Android", "Material Design", "Jetpack Compose", "RecyclerView", "XML layouts"
- Try being more explicit:
  - Instead of "Fix my UI"
  - Try "Fix my Android UI, I'm using Material Design 2 and need to migrate to M3"

### **Extension crashes or throws errors**

1. **Check error logs**:
   - Press `Ctrl+Shift+P` → "View: Toggle Output"
   - Select "Android UI/UX Upgrade" from the dropdown

2. **Report the issue**:
   - Go to [GitHub Issues](https://github.com/yourusername/android-ui-upgrade-skill/issues)
   - Include the error message and steps to reproduce

### **Performance issues or slow responses**

- This is usually a GitHub Copilot service issue, not the skill
- Try asking a simpler question first
- Check your internet connection

---

## 🔄 Updating the Skill

### **Auto-Update**

VS Code will check for updates automatically. When an update is available:

1. Go to Extensions (`Ctrl+Shift+X`)
2. Find "Android UI/UX Upgrade"
3. Click the **Update** button if visible

### **Manual Update**

1. Uninstall the current version (right-click → Uninstall)
2. Restart VS Code
3. Reinstall using Method 1 (Extensions Marketplace)

---

## ✨ Next Steps

Once installed:

1. **Read the [README.md](./README.md)** for an overview of what the skill does
2. **Check the [docs/examples/](./docs/examples/)** folder for code snippets
3. **Explore specific phases** as you encounter UI/UX issues
4. **Share feedback** via GitHub Issues or Discussions

---

## 📞 Need Help?

- 📖 Read the main [README.md](./README.md)
- 💬 Check [FAQ.md](./docs/FAQ.md) for common questions
- 🐛 Report issues on [GitHub Issues](https://github.com/yourusername/android-ui-upgrade-skill/issues)
- 💡 Start a discussion on [GitHub Discussions](https://github.com/yourusername/android-ui-upgrade-skill/discussions)

**Happy coding! 🚀**
