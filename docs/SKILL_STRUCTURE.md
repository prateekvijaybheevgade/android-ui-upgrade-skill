# Skill Structure

This document explains how the Android UI/UX Upgrade Skill is organized and how to navigate it.

## 📚 Main Skill File

The core content is in [SKILL.md](../SKILL.md), which contains:
- Phase-by-phase guidance
- Code examples and patterns
- Best practices backed by Material Design guidelines
- Real-world scenarios and solutions

## 🎯 Quick Links for Users

- **New users**: Start with [USAGE_GUIDE.md](./USAGE_GUIDE.md) for real-world scenarios
- **Need help?**: Check [FAQ.md](./FAQ.md) for common questions
- **Want code?**: Browse [examples/](./examples/) directory
- **Complete reference**: Read [../SKILL.md](../SKILL.md)

## 🗂️ Documentation Organization

```
android-ui-upgrade-skill/
├── SKILL.md                          # Main comprehensive guide (7 phases)
├── README.md                         # Overview & quick start
├── INSTALL.md                        # Installation instructions
├── CONTRIBUTING.md                   # Contribution guidelines
├── CHANGELOG.md                      # Version history
├── LICENSE                           # MIT License
├── .gitignore                        # Git ignore rules
│
├── docs/
│   ├── SKILL_STRUCTURE.md           # This file
│   ├── FAQ.md                       # Frequently asked questions
│   ├── ROADMAP.md                   # Future plans
│   ├── MATERIAL_DESIGN_3.md         # M3 deep dive
│   ├── ACCESSIBILITY_GUIDE.md       # WCAG AA checklist
│   ├── COMPOSE_MIGRATION.md         # Compose migration playbook
│   ├── PERFORMANCE_TIPS.md          # Optimization techniques
│   ├── TROUBLESHOOTING.md           # Common issues & fixes
│   ├── CONTRIBUTORS.md              # List of contributors
│   │
│   └── examples/                    # Production-ready code snippets
│       ├── Phase_1_Design_System/
│       │   ├── themes.xml           # Material3 theme setup
│       │   ├── colors.xml           # Color token system
│       │   ├── dimens.xml           # Spacing system
│       │   └── typography.xml       # Type scale configuration
│       │
│       ├── Phase_2_Layout_Fixes/
│       │   ├── touch_target_fix.xml
│       │   ├── nested_weights_fix.xml
│       │   ├── fixed_height_fix.xml
│       │   ├── recyclerview_item.xml
│       │   └── list_best_practices.xml
│       │
│       ├── Phase_3_Navigation/
│       │   ├── material_navigation_bar.xml
│       │   ├── material_toolbar.xml
│       │   ├── collapsing_toolbar.xml
│       │   └── predictive_back_gesture.kt
│       │
│       ├── Phase_4_State_Management/
│       │   ├── ui_state_sealed_class.kt
│       │   ├── loading_state_shimmer.xml
│       │   ├── empty_state_screen.xml
│       │   ├── error_state_retry.xml
│       │   └── state_management_viewmodel.kt
│       │
│       ├── Phase_5_Accessibility/
│       │   ├── content_descriptions.xml
│       │   ├── focus_order.xml
│       │   ├── font_scaling.xml
│       │   ├── contrast_checker.md
│       │   └── accessibility_best_practices.kt
│       │
│       ├── Phase_6_Performance/
│       │   ├── viewbinding_setup.kt
│       │   ├── recyclerview_optimization.kt
│       │   ├── image_loading_coil.kt
│       │   └── memory_optimization.kt
│       │
│       └── Phase_7_Compose/
│           ├── m3_theme_setup.kt
│           ├── compose_interop.kt
│           ├── composable_screen_example.kt
│           └── migration_strategy.md
```

## 🎯 7 Phases Overview

### Phase 0: Triage (Always Start Here)
**Purpose**: Diagnose the problem before fixing  
**Duration**: 15 minutes  
**Output**: Severity classification, prioritized fix list

**Key Checklist**:
- Target API level / min SDK?
- XML Views or Jetpack Compose?
- Material Design version?
- Dark mode support needed?
- Accessibility requirements?
- Design tokens / style.xml existing?
- Worst 3 screens hated most?

### Phase 1: Design System Foundation
**Purpose**: Establish Material Design 3 base  
**Duration**: 1-2 hours  
**Output**: Theme, colors, typography, spacing system

**Key Topics**:
- Material Design 3 setup
- Color system & semantic tokens
- Typography scale
- Spacing/grid system
- Example: `colors.xml`, `themes.xml`, `dimens.xml`

### Phase 2: Layout Anti-Pattern Fixes
**Purpose**: Fix structural UI issues (P0 priority)  
**Duration**: 2-4 hours  
**Output**: Flat hierarchies, accessible layouts

**Key Topics**:
- Touch target violations (< 48dp = broken)
- Nested weights / deep hierarchy
- Fixed heights on text (accessibility killer)
- RecyclerView item design
- Example: `touch_target_fix.xml`, `nested_weights_fix.xml`

### Phase 3: Navigation Patterns
**Purpose**: Modernize navigation UI  
**Duration**: 1-2 hours  
**Output**: Material nav components, gesture support

**Key Topics**:
- Material NavigationBar (bottom nav)
- Material Toolbar (app bar)
- Collapsing toolbar (large M3 variant)
- Predictive back gestures (Android 14+)
- Example: `material_navigation_bar.xml`, `predictive_back_gesture.kt`

### Phase 4: State Management UI
**Purpose**: Handle all screen states properly  
**Duration**: 1-2 hours  
**Output**: Loading, error, empty, success UI

**Key Topics**:
- UiState sealed class pattern
- Shimmer loading skeleton
- Empty state screens
- Error state with retry
- Example: `loading_state_shimmer.xml`, `error_state_retry.xml`

### Phase 5: Accessibility Fixes
**Purpose**: WCAG AA compliance  
**Duration**: 2-3 hours  
**Output**: TalkBack support, contrast, focus order

**Key Topics**:
- Content descriptions
- Contrast ratios (WCAG AA: 4.5:1 for normal text)
- Focus order management
- Font scaling support
- Example: `content_descriptions.xml`, `focus_order.xml`

### Phase 6: Performance Quick Wins
**Purpose**: Optimize rendering and memory  
**Duration**: 1-2 hours  
**Output**: Smooth scrolling, efficient loading

**Key Topics**:
- ViewBinding (replace findViewById)
- RecyclerView optimization
- Image loading (Coil/Glide)
- Memory leak prevention
- Example: `viewbinding_setup.kt`, `recyclerview_optimization.kt`

### Phase 7: Jetpack Compose Migration
**Purpose**: Gradual migration to Compose  
**Duration**: 2-6 hours (or phases)  
**Output**: ComposeView interop, Compose screens

**Key Topics**:
- Interop-first strategy (no big bang rewrite)
- M3 Compose themes
- Embedding legacy Views in Compose
- Screen-by-screen conversion
- Example: `m3_theme_setup.kt`, `compose_interop.kt`

## 🗣️ How to Use This Skill in Copilot Chat

### Option 1: Linear Journey
Start at Phase 0 and work through sequentially:

```
You: "My Android app's UI is terrible. Help me improve it."
Skill: Starts with Phase 0 triage questions
You: Answer the intake checklist
Skill: Provides severity-classified fix list
You: "Let's fix Phase 1 issues first"
Skill: Provides Material Design 3 setup guidance
...continue through phases
```

### Option 2: Jump to Specific Phase
If you know the problem, skip to the relevant phase:

```
You: "How do I fix RecyclerView performance?"
Skill: Jumps to Phase 6 (Performance)
→ Provides ViewHolder optimization, caching tips, image loading best practices
```

### Option 3: Ask a Specific Question
For targeted help on a problem:

```
You: "Make this 30dp button touch-friendly"
Skill: Provides Phase 2 (Layout) guidance
→ Shows how to achieve 48dp minimum touch targets with proper padding
```

## 📊 Decision Tree

Use this to find the right phase for your problem:

```
Do you have a specific UI/UX problem?
│
├─ → "My colors/spacing are inconsistent"
│    └─ → Go to Phase 1: Design System
│
├─ → "Text gets cut off, buttons are tiny, layout breaks"
│    └─ → Go to Phase 2: Layout Anti-Patterns
│
├─ → "Navigation UI looks outdated"
│    └─ → Go to Phase 3: Navigation Patterns
│
├─ → "My screens don't show loading/error/empty states"
│    └─ → Go to Phase 4: State Management
│
├─ → "My app doesn't support dark mode, accessibility"
│    └─ → Go to Phase 5: Accessibility
│
├─ → "My RecyclerView lags, images load slowly"
│    └─ → Go to Phase 6: Performance
│
├─ → "Should I migrate to Compose? How?"
│    └─ → Go to Phase 7: Compose Migration
│
└─ → "I don't know where to start"
     └─ → Start at Phase 0: Triage
```

## 📖 Recommended Reading Order

### For Beginners
1. [README.md](../README.md) — Overview
2. [INSTALL.md](../INSTALL.md) — Get set up
3. [SKILL.md Phase 0](../SKILL.md) — Understand your problems
4. [SKILL.md Phase 1](../SKILL.md) — Build design foundation

### For Experienced Developers
1. [SKILL.md Phase 7](../SKILL.md) — Compose migration
2. [COMPOSE_MIGRATION.md](./COMPOSE_MIGRATION.md) — Detailed guide
3. Example files for your specific use case

### For Accessibility Advocates
1. [ACCESSIBILITY_GUIDE.md](./ACCESSIBILITY_GUIDE.md) — Full WCAG checklist
2. [SKILL.md Phase 5](../SKILL.md) — Implementation details
3. [Example: Accessibility best practices](./examples/Phase_5_Accessibility/)

### For Performance Engineers
1. [PERFORMANCE_TIPS.md](./PERFORMANCE_TIPS.md) — Optimization guide
2. [SKILL.md Phase 6](../SKILL.md) — Quick wins
3. [Example: RecyclerView optimization](./examples/Phase_6_Performance/recyclerview_optimization.kt)

## 🔗 Cross-References

### Material Design 3 References
- Full reference in [SKILL.md Phase 1](../SKILL.md)
- Deep dive: [MATERIAL_DESIGN_3.md](./MATERIAL_DESIGN_3.md)
- Example: [colors.xml](./examples/Phase_1_Design_System/colors.xml)
- External: [m3.material.io](https://m3.material.io/)

### Accessibility References
- Full reference in [SKILL.md Phase 5](../SKILL.md)
- Checklist: [ACCESSIBILITY_GUIDE.md](./ACCESSIBILITY_GUIDE.md)
- Example: [focus_order.xml](./examples/Phase_5_Accessibility/focus_order.xml)
- External: [WCAG 2.1](https://www.w3.org/WAI/WCAG21/quickref/)

### Jetpack Compose References
- Full reference in [SKILL.md Phase 7](../SKILL.md)
- Detailed guide: [COMPOSE_MIGRATION.md](./COMPOSE_MIGRATION.md)
- Example: [m3_theme_setup.kt](./examples/Phase_7_Compose/m3_theme_setup.kt)
- External: [developer.android.com/jetpack/compose](https://developer.android.com/jetpack/compose)

## 🎓 Learning Outcomes

By working through this skill, you'll learn to:

✅ Diagnose UI/UX problems systematically  
✅ Implement Material Design 3 correctly  
✅ Create accessible, WCAG AA compliant UIs  
✅ Optimize layouts and performance  
✅ Handle all screen states (loading/error/empty)  
✅ Migrate gradually to Jetpack Compose  
✅ Enable dark mode support  
✅ Build responsive, adaptive layouts  

## 📞 Navigation Help

### "I'm confused, where do I start?"
→ Start at [Phase 0 in SKILL.md](../SKILL.md)

### "I want to copy-paste code"
→ Go to [docs/examples/](./examples/) folder for your phase

### "I want step-by-step implementation"
→ Read the phase in [SKILL.md](../SKILL.md) with code examples

### "I need to know if this is right approach"
→ Check [FAQ.md](./FAQ.md) for validation questions

---

**Need help navigating?** Open an issue or check [TROUBLESHOOTING.md](./TROUBLESHOOTING.md).
