# Contributing to Android UI/UX Upgrade Skill

First off, thank you for considering contributing to this skill! 🎉 Your input helps make Android development better for everyone.

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How to Contribute](#how-to-contribute)
- [Development Setup](#development-setup)
- [Contribution Workflow](#contribution-workflow)
- [Reporting Bugs](#reporting-bugs)
- [Suggesting Enhancements](#suggesting-enhancements)
- [Commit Message Guidelines](#commit-message-guidelines)
- [Style Guide](#style-guide)
- [Additional Notes](#additional-notes)

---

## 🤝 Code of Conduct

Please be respectful and constructive. We're all here to help each other build better Android apps.

### Our Pledge

We are committed to providing a welcoming and inclusive environment for all contributors, regardless of:
- Background or experience level
- Gender, gender identity, or gender expression
- Age, body size, disability
- Ethnicity, national origin
- Religion
- Sexual identity or orientation

### Expected Behavior

- Use welcoming and inclusive language
- Be respectful of differing opinions
- Accept constructive criticism gracefully
- Focus on what is best for the community
- Show empathy toward other community members

### Unacceptable Behavior

- Harassment or discrimination of any kind
- Offensive language or personal attacks
- Publishing private information (doxxing)
- Other conduct that would reasonably be considered inappropriate

---

## 💡 How to Contribute

### **I Don't Want to Read This Entire Thing, I Just Have a Question**

> **Please don't file an issue for questions.** You'll get faster results by using:
> - [GitHub Discussions](https://github.com/yourusername/android-ui-upgrade-skill/discussions) — for general questions
> - [FAQ.md](./docs/FAQ.md) — common questions and answers
> - [Stack Overflow](https://stackoverflow.com/questions/tagged/android) — for broader Android questions

### **I Found a Bug**

→ Go to [Reporting Bugs](#reporting-bugs) section below.

### **I Have a Feature Idea**

→ Go to [Suggesting Enhancements](#suggesting-enhancements) section below.

### **I Want to Improve Documentation**

→ See [Contributing Documentation](#contributing-documentation) section below.

### **I Want to Add Code Examples or Snippets**

→ See [Contributing Code Examples](#contributing-code-examples) section below.

---

## 🛠️ Development Setup

### Prerequisites

- Git installed on your machine
- VS Code installed
- Node.js 16+ and npm (for building the skill)
- Basic understanding of the skill structure

### Setting Up Your Development Environment

1. **Fork the repository**:
   ```bash
   # Go to https://github.com/yourusername/android-ui-upgrade-skill
   # Click the "Fork" button in the top-right
   ```

2. **Clone your fork locally**:
   ```bash
   git clone https://github.com/YOUR-USERNAME/android-ui-upgrade-skill.git
   cd android-ui-upgrade-skill
   ```

3. **Create a branch for your work**:
   ```bash
   git checkout -b feature/your-feature-name
   # or
   git checkout -b fix/your-bug-fix-name
   ```

4. **Install dependencies** (if applicable):
   ```bash
   npm install
   # or
   pip install -r requirements.txt  # if Python-based
   ```

5. **Build the skill** (if applicable):
   ```bash
   npm run build
   # or
   python build.py
   ```

---

## 📝 Contribution Workflow

### Step 1: Make Your Changes

- Edit files according to the [Style Guide](#style-guide) below
- Keep changes focused and atomic (one feature/fix per commit)
- Test your changes thoroughly

### Step 2: Commit Your Work

```bash
git add .
git commit -m "feat: add Material Design 3 color tokens example"
```

Follow the [Commit Message Guidelines](#commit-message-guidelines) below.

### Step 3: Push to Your Fork

```bash
git push origin feature/your-feature-name
```

### Step 4: Create a Pull Request (PR)

1. Go to the original repository: https://github.com/yourusername/android-ui-upgrade-skill
2. Click "New Pull Request"
3. Select your fork and branch
4. Fill in the PR template with:
   - **Title**: Brief description of changes
   - **Description**: Why this change? What does it fix/add?
   - **Related Issues**: Link any related issues (e.g., "Fixes #42")
   - **Testing**: How did you test this?

### Step 5: Respond to Review

- A maintainer will review your PR
- Be open to feedback and iterate as needed
- Once approved, your PR will be merged!

---

## 🐛 Reporting Bugs

### Before Submitting a Bug Report

- **Check the [FAQ](./docs/FAQ.md)** — Your issue might already be documented
- **Search [existing issues](https://github.com/yourusername/android-ui-upgrade-skill/issues)** — It might already be reported
- **Check the [CHANGELOG](./CHANGELOG.md)** — It might be fixed in the latest version

### How to Submit a Great Bug Report

When you do submit an issue, please include:

1. **Clear, descriptive title**: "Crash when opening Compose migration guide"

2. **Step-by-step reproduction**:
   ```
   1. Open VS Code
   2. Install the skill
   3. Open Copilot Chat
   4. Type "Help with Compose migration"
   5. [Error occurs]
   ```

3. **Expected vs. Actual behavior**:
   - **Expected**: Should show Compose migration guide
   - **Actual**: Error message appears

4. **Screenshots or code snippets** (if applicable)

5. **Environment**:
   ```
   - OS: Windows 10 / macOS 12.5 / Ubuntu 22.04
   - VS Code Version: 1.78.0
   - GitHub Copilot Extension Version: 1.x.x
   - Skill Version: 1.0.0
   ```

6. **Error logs** (if applicable):
   - Press `Ctrl+Shift+P` → "View: Toggle Output"
   - Select "Android UI/UX Upgrade" from dropdown
   - Copy any error messages

---

## ✨ Suggesting Enhancements

### Before Submitting a Feature Suggestion

- **Check the [README](./README.md)** — Feature might already exist
- **Search [existing discussions](https://github.com/yourusername/android-ui-upgrade-skill/discussions)** — Someone might have suggested it
- **Check [planned features](./docs/ROADMAP.md)** — It might be on our roadmap

### How to Submit a Great Feature Suggestion

1. **Use a clear, descriptive title**: "Add Phase 8: Advanced Animation Patterns"

2. **Provide a detailed description**:
   - What problem would this solve?
   - Who would benefit?
   - Are there any related Material Design guidelines?

3. **Provide examples or references**:
   - Links to Material Design docs
   - Code examples or mockups
   - Links to similar features in other tools

4. **Explain why this matters**:
   - How often would users need this?
   - What's the impact on Android developers?

---

## 📖 Contributing Documentation

### How to Improve Docs

1. **Create a fork and branch** (see [Development Setup](#development-setup))

2. **Edit the relevant documentation file**:
   - Main guide: `SKILL.md`
   - Phase-specific guides: `docs/PHASE_*.md`
   - Examples: `docs/examples/`
   - FAQ: `docs/FAQ.md`

3. **Follow the [Style Guide](#style-guide)**:
   - Use clear, concise language
   - Include code examples where helpful
   - Use proper Markdown formatting
   - Add links to relevant resources

4. **Commit and create a PR** (see [Contribution Workflow](#contribution-workflow))

### Documentation Standards

- **Clarity**: Anyone new to Android should understand
- **Completeness**: Include context and examples
- **Accuracy**: Double-check all code and links
- **Consistency**: Match existing documentation style
- **Actionability**: Give users concrete steps to follow

---

## 💻 Contributing Code Examples

### Where to Add Examples

Examples live in `docs/examples/` organized by phase:
```
docs/examples/
├── Phase_1_Design_System/
│   ├── themes.xml
│   ├── colors.xml
│   └── dimens.xml
├── Phase_2_Layout_Fixes/
│   ├── touch_target_fix.xml
│   ├── nested_weights_fix.xml
│   └── ...
└── Phase_7_Compose/
    ├── m3_theme_setup.kt
    ├── compose_interop.kt
    └── ...
```

### Guidelines for Code Examples

1. **Keep examples focused and copy-paste ready**
2. **Include comments explaining key concepts**
3. **Show both "wrong" and "right" approaches** when applicable
4. **Test code works on API 21+**
5. **Use real-world scenarios** (not contrived examples)
6. **Include Kotlin and XML examples** where relevant
7. **Add a header comment** explaining:
   - What problem this solves
   - What Material version / API level required
   - Any dependencies needed

### Example Template

```kotlin
/**
 * M3 Material Theme Setup for Jetpack Compose
 * 
 * Problem: Setting up Material Design 3 theming in Compose
 * API Level: 21+
 * Dependencies: androidx.compose.material3:material3:1.0.0+
 * 
 * Learn more: https://developer.android.com/jetpack/compose/designsystems/material
 */

@Composable
fun AppTheme(
    darkTheme: Boolean = isSystemInDarkTheme(),
    content: @Composable () -> Unit
) {
    // ... theme setup
}
```

---

## 📝 Commit Message Guidelines

Follow the **Conventional Commits** format for consistency:

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types

- `feat`: A new feature or content
- `fix`: Bug fix or correction
- `docs`: Documentation only
- `style`: Formatting, missing semicolons, etc.
- `refactor`: Code refactoring without feature changes
- `perf`: Performance improvements
- `test`: Adding or updating tests

### Examples

```bash
# Feature
git commit -m "feat(compose): add Compose migration phase example"

# Bug fix
git commit -m "fix(accessibility): correct WCAG AA contrast ratio documentation"

# Documentation
git commit -m "docs(faq): add troubleshooting section"

# Multiple lines with context
git commit -m "feat(phase-6): add RecyclerView optimization examples

- Add ViewHolder pattern example
- Add setHasFixedSize() best practice
- Include image loading optimization with Coil"
```

---

## 🎨 Style Guide

### Markdown Style

- **Headers**: Use `##` for section headers (not `#` or `###`)
- **Code blocks**: Use triple backticks with language specified
  ```markdown
  \`\`\`kotlin
  // code here
  \`\`\`
  ```
- **Links**: Use descriptive text, not "click here"
  ```markdown
  # Wrong
  Click [here](link) for more info
  
  # Right
  See [Material Design 3 guidelines](link) for more info
  ```
- **Lists**: Use `-` for unordered, `1.` for ordered
- **Emphasis**: Use `**bold**` and `*italic*` sparingly

### Code Style

#### Kotlin/Java

- Follow [Google's Kotlin Style Guide](https://kotlinlang.org/docs/coding-conventions.html)
- Use 4-space indentation
- Use descriptive variable names
- Add comments for complex logic

#### XML

- Use 4-space indentation
- Group related attributes
- Use semantic naming (not `view1`, `view2`)
- Add comments for custom or non-obvious attributes

#### Example:
```xml
<!-- Good ✅ -->
<com.google.android.material.button.MaterialButton
    android:id="@+id/btn_submit"
    style="@style/Widget.Material3.Button"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="@string/label_submit"
    android:contentDescription="@string/cd_submit_button" />

<!-- Avoid ❌ -->
<Button android:id="@+id/b1" android:layout_width="100dp" android:layout_height="48dp" android:text="Submit" />
```

---

## 🧪 Testing

### Before Submitting a PR

1. **Test locally**:
   ```bash
   npm run test
   # or test manually in VS Code
   ```

2. **Check for linting errors**:
   ```bash
   npm run lint
   ```

3. **Build the skill**:
   ```bash
   npm run build
   ```

4. **Manual testing in VS Code**:
   - Open the skill folder in VS Code
   - Press `F5` to launch a development instance
   - Test the skill in Copilot Chat

---

## 📋 Pull Request Template

When creating a PR, use this template:

```markdown
## Description
Brief description of what this PR does.

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation update
- [ ] Example/snippet
- [ ] Performance improvement

## Related Issues
Fixes #(issue number)

## Testing
How was this tested? Include any relevant steps or commands.

## Screenshots (if applicable)
Add screenshots for UI/documentation changes.

## Checklist
- [ ] I have read the CONTRIBUTING.md guide
- [ ] I have tested my changes
- [ ] I have added comments to complex code
- [ ] I have updated relevant documentation
- [ ] My commits follow the commit message guidelines
```

---

## 🏆 Recognition

Contributors are recognized in:
- [Contributors list](./docs/CONTRIBUTORS.md)
- Release notes for significant contributions
- Thank you message in PR

---

## 📚 Additional Resources

- [Android Developer Docs](https://developer.android.com/docs)
- [Material Design 3 Guidelines](https://m3.material.io/)
- [Jetpack Compose Documentation](https://developer.android.com/jetpack/compose)
- [Conventional Commits](https://www.conventionalcommits.org/)
- [GitHub Flow Guide](https://guides.github.com/introduction/flow/)

---

## ❓ Questions?

- 📖 Check [FAQ.md](./docs/FAQ.md)
- 💬 Start a [Discussion](https://github.com/yourusername/android-ui-upgrade-skill/discussions)
- 📧 Reach out to maintainers

---

**Thank you for contributing! 🙌**

Your work helps make Android development better for everyone. We appreciate you!
