# Frequently Asked Questions (FAQ)

Quick answers to common questions about the Android UI/UX Upgrade Skill.

## 📋 General Questions

### Q: Do I need to follow all 7 phases?
**A:** No! You can jump to the phase that matches your problem. However, **Phase 0 (Triage) is always recommended** to prioritize fixes correctly.

Best approach:
- Small fix needed? → Jump to specific phase
- Complete overhaul? → Start at Phase 0 and work sequentially

### Q: How long does a complete UI overhaul take?
**A:** Typical timeline:
- **Phase 0 (Triage)**: 15 minutes
- **Phase 1 (Design System)**: 1-2 hours
- **Phase 2 (Layout Fixes)**: 2-4 hours
- **Phases 3-6**: 1-2 hours each
- **Phase 7 (Compose Migration)**: Varies (can span weeks)

**Total for full modernization**: 1-2 weeks depending on app complexity.

### Q: Can I use this skill on legacy apps (API 16+)?
**A:** 
- **API 21+** (Lollipop): Full Material Design 3 support ✅
- **API 16-20**: Use Material2 instead (guidance in Phase 1)
- **Very old apps**: Start with Phase 2 (Layout Fixes) instead of Phase 1

### Q: My app uses Material Design 2. Should I upgrade?
**A:** **Yes, definitely!** Material Design 3 provides:
- ✅ Better color system (Material You dynamic theming)
- ✅ Improved typography
- ✅ Enhanced accessibility out-of-the-box
- ✅ Backward compatible (works on API 21+)

See [Phase 1](../SKILL.md) for migration path.

### Q: Is this skill Android Studio specific?
**A:** No! This skill works with:
- ✅ Android Studio (primary)
- ✅ VS Code + Android plugins
- ✅ IntelliJ IDEA
- ✅ Any text editor (you just need guidance)

---

## 🎨 Material Design 3 Questions

### Q: What's the difference between Material Design 2 and 3?
**A:** 
| Aspect | M2 | M3 |
|--------|----|----|
| **Color System** | Fixed palette | Dynamic (Material You) |
| **Typography** | 14 type scales | Customizable |
| **Components** | Material | Modernized M3 |
| **Accessibility** | Good | Better (higher contrast) |

**Migration**: See [MATERIAL_DESIGN_3.md](./MATERIAL_DESIGN_3.md)

### Q: Can I use Material Design 3 on API 21?
**A:** **Yes!** The `material:1.12.0` library provides full M3 support on API 21+.

```gradle
implementation 'com.google.android.material:material:1.12.0'
```

### Q: How do I generate M3 colors for my brand?
**A:** Use the **Material Theme Builder**:
1. Visit https://material-foundation.github.io/material-theme-builder/
2. Upload your brand color
3. Download the color config
4. Add to your `colors.xml`

See [Phase 1](../SKILL.md) for code examples.

### Q: Should I hardcode colors or use tokens?
**A:** **Always use tokens!**

```xml
<!-- ❌ NEVER hardcode -->
android:textColor="#333333"

<!-- ✅ ALWAYS use tokens -->
android:textColor="?attr/colorOnSurface"
```

This enables dark mode, accessibility, and theming automatically.

---

## ♿ Accessibility Questions

### Q: What's WCAG AA?
**A:** Web Content Accessibility Guidelines Level AA - minimum accessibility standard for:
- **Contrast**: 4.5:1 for normal text, 3:1 for large text
- **Touch targets**: 48dp × 48dp minimum
- **Focus**: Logical tab order, visible focus indicator

See [ACCESSIBILITY_GUIDE.md](./ACCESSIBILITY_GUIDE.md) for full checklist.

### Q: How do I test for accessibility?
**A:** Use Android's built-in tools:

1. **TalkBack** (screen reader):
   - Settings → Accessibility → TalkBack → Enable
   - Navigate with two-finger swipes

2. **Accessibility Scanner** (automated):
   - Play Store: Download "Accessibility Scanner" by Google
   - Tap button to scan current screen
   - See suggestions

3. **Manual testing** (at 200% font size):
   - Settings → Display → Font size
   - Does text still fit? Does layout adapt?

### Q: Is dark mode accessibility or preference?
**A:** **Both!** Dark mode helps:
- ✅ Users with photophobia (light sensitivity)
- ✅ Battery life (OLED screens)
- ✅ Users in bright environments
- ✅ Reduce eye strain

Use semantic tokens to support it:
```xml
<!-- M3 automatically handles dark mode -->
android:textColor="?attr/colorOnSurface"
```

### Q: How do I add content descriptions?
**A:** Every interactive element needs a content description:

```xml
<ImageButton
    android:id="@+id/btn_close"
    android:contentDescription="@string/cd_close_dialog"
    android:src="@drawable/ic_close_24" />
```

Store descriptions in `strings.xml`:
```xml
<string name="cd_close_dialog">Close dialog</string>
```

See [Phase 5](../SKILL.md) for full guidance.

---

## 🎼 Jetpack Compose Questions

### Q: Should I rewrite my app in Compose?
**A:** **No big bang rewrite!** Use the **interop-first approach**:

1. **Keep existing XML layouts**
2. **Add Compose via ComposeView** on one screen
3. **Convert screen-by-screen** over time
4. **Gradually expand Compose usage**

See [Phase 7](../SKILL.md) and [COMPOSE_MIGRATION.md](./COMPOSE_MIGRATION.md)

### Q: What's the difference between Views and Compose?
**A:**
| Aspect | Views (XML) | Compose |
|--------|------------|---------|
| **Learning curve** | Medium | Steep initially |
| **Performance** | Good | Excellent |
| **State management** | ViewModel + LiveData | State + remember |
| **Reusability** | Layout XML files | Composable functions |
| **Testing** | More boilerplate | Less boilerplate |

**Recommendation**: Start with Views for phase fixes, migrate to Compose later.

### Q: Can I mix XML and Compose?
**A:** **Yes!** This is the recommended migration path:

```kotlin
// XML screen with Compose button
val composeView = ComposeView(context).apply {
    setContent {
        MaterialTheme {
            MyCustomButton()
        }
    }
}
```

See [Phase 7](../SKILL.md) for examples.

### Q: How do I set up M3 theming in Compose?
**A:** Simple three-step setup:

1. Add dependency:
```gradle
implementation 'androidx.compose.material3:material3:1.0.0'
```

2. Create theme:
```kotlin
@Composable
fun AppTheme(content: @Composable () -> Unit) {
    MaterialTheme(
        colorScheme = lightColorScheme(),
        content = content
    )
}
```

3. Use it:
```kotlin
AppTheme {
    MyScreen()
}
```

See [docs/examples/Phase_7_Compose/](./examples/Phase_7_Compose/) for full example.

---

## ⚡ Performance Questions

### Q: Why is my RecyclerView laggy?
**A:** Common causes:
- ❌ Heavy layout (nested weights)
- ❌ Unbounded image sizes (loading 4K photos for 100dp thumbnails)
- ❌ No ViewHolder pattern
- ❌ Creating new objects in `onBindViewHolder`

**Quick fixes** in [Phase 6](../SKILL.md):
- ✅ Use ConstraintLayout (flat hierarchy)
- ✅ Specify image sizes explicitly
- ✅ Cache views properly
- ✅ Load images asynchronously

### Q: What's the best image loading library?
**A:** **Coil** (Kotlin-first, coroutine-based):

```kotlin
imageView.load("https://example.com/image.jpg") {
    crossfade(true)
    placeholder(R.drawable.ic_placeholder)
    error(R.drawable.ic_error)
}
```

Alternatives: Glide (powerful), Picasso (simple)

See [Phase 6](../SKILL.md) for examples.

### Q: How do I prevent memory leaks?
**A:** Common leak sources:
- ❌ ViewBinding not cleared in `onDestroyView`
- ❌ Listener not unregistered
- ❌ Background tasks holding Activity reference

**Fix** in [Phase 6](../SKILL.md):
```kotlin
override fun onDestroyView() {
    super.onDestroyView()
    _binding = null  // Clear binding reference
}
```

---

## 🔧 Implementation Questions

### Q: Can I implement this incrementally?
**A:** **Absolutely!** Recommended incremental approach:

**Week 1**: Phase 0 + Phase 1 (design system)  
**Week 2**: Phase 2 (layout fixes)  
**Week 3**: Phases 3-4 (navigation + states)  
**Week 4**: Phases 5-6 (accessibility + performance)  
**Later**: Phase 7 (Compose migration)

### Q: Should I refactor or rewrite?
**A:** **Refactor!** Each phase builds on previous. No need to rewrite everything:

- Phase 1: Add design tokens to `colors.xml`, `dimens.xml`
- Phase 2: Fix individual screens with bad layouts
- Phase 3: Update navigation components
- ...continue incrementally

### Q: How do I handle existing code that doesn't follow these patterns?
**A:** **Gradual migration**:

1. **Don't rewrite everything** — Fix as you touch code
2. **Use consistent patterns going forward** — All new code follows best practices
3. **Refactor low-risk files first** — Test thoroughly
4. **Create style guide** — Team consensus on patterns

### Q: Can I automate these fixes?
**A:** Partially:
- ✅ Lint rules for touch targets, hardcoded colors
- ✅ Static analysis (Android Lint)
- ❌ Full layout restructuring (requires human judgment)

Use [Android Lint](https://developer.android.com/studio/write/lint) for automation.

---

## 📱 Device & API Questions

### Q: How do I handle phones vs. tablets?
**A:** Use **responsive layout patterns**:
- XML: Multiple `layout-sw*dp` folders
- Compose: `BoxWithConstraints` to adapt

See [Phase 2](../SKILL.md) for responsive layout examples.

### Q: What about foldable devices?
**A:** Use `androidx.window` library:
```gradle
implementation 'androidx.window:window:1.0.0'
```

Plan for Phase 8 (future expansion).

### Q: How do I support API 21 if Material3 requires newer features?
**A:** Material3 library handles backward compat:
- API 21-22: Limited dynamic color
- API 23+: Full Material3 feature support
- Graceful degradation for older APIs

---

## 🐛 Troubleshooting

### Q: I followed the guide but it still looks bad
**A:** Check:
1. Are you using semantic color tokens (`?attr/colorOnSurface`)?
2. Is your layout using ConstraintLayout (not nested LinearLayouts)?
3. Have you tested on multiple screen sizes?
4. Are you testing on the theme you want?

See [TROUBLESHOOTING.md](./TROUBLESHOOTING.md) for common issues.

### Q: Why is the text cut off?
**A:** Most likely cause: Fixed `android:layout_height` with text.

**Solution** (from [Phase 2](../SKILL.md)):
```xml
<!-- ❌ Wrong -->
<TextView android:layout_height="40dp" />

<!-- ✅ Right -->
<TextView
    android:layout_height="wrap_content"
    android:minHeight="40dp" />
```

### Q: Dark mode colors look wrong
**A:** Ensure you're using semantic tokens, not hardcoded colors:

```xml
<!-- ❌ Wrong (hardcoded) -->
android:backgroundColor="#FFFFFF"  <!-- wrong in dark mode! -->

<!-- ✅ Right (semantic) -->
android:backgroundColor="?attr/colorSurface"  <!-- auto-adapts -->
```

---

## 💬 Still Have Questions?

- 🔍 **Search the skill**: Use `Ctrl+F` in [SKILL.md](../SKILL.md)
- 📖 **Read relevant phase**: Each phase has detailed guidance
- 💬 **GitHub Discussions**: [Ask in Discussions](https://github.com/yourusername/android-ui-upgrade-skill/discussions)
- 🐛 **Report bug**: [Open an issue](https://github.com/yourusername/android-ui-upgrade-skill/issues)
- 📧 **Email**: Include in support info (to be added)

---

**Last Updated**: June 2026  
**Version**: 1.0.0

See [README.md](../README.md) for more information.
