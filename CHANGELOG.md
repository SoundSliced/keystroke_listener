## 2.1.0
- `s_packages` dependency upgraded to ^1.3.0
- Added `actionHandlers` map for customizable intent callbacks per intent type

## 2.0.0
- package no longer holds the source code for it, but exports/exposes the `s_packages` package instead, which will hold this package's latest source code.
- The only future changes to this package will be made via `s_packages` package dependency upgrades, in order to bring the new fixes or changes to this package
- dependent on `s_packages`: ^1.1.2


## 1.1.2

* fix: The button/widget briefly gets focus (allowing the click to work properly)
After the frame completes, the KeystrokeListener automatically reclaims focus
Keyboard listening continues uninterrupted


## 1.1.1 

* CHANGELOG and README updated

## 1.1.0

* KeystrokeListener now maintains keyboard event detection even when child widgets gain focus, and provides smooth visual debugging feedback:

  - Refactored widget architecture - Replaced FocusableActionDetector with explicit composition of Actions, Shortcuts, and Focus widgets for better control over focus management and key event propagation.

  - Fixed event handling - Changed _handleKeyEvent to return KeyEventResult.ignored instead of KeyEventResult.handled, allowing key events to properly bubble up from focused child widgets while still capturing them in the callback.

  - Improved visual debug UX - Added clearSnackBars() before showing new SnackBar messages to prevent queuing and provide immediate visual feedback when rapidly pressing keys.


## 1.0.1

* `RoleFocusNode` class added: FocusNode with a stable role identifier preserved in release builds.

## 1.0.0

* **Complete package implementation** with comprehensive features
* Added 18+ Intent classes for keyboard event handling:
  - Basic navigation intents (Up, Down, Left, Right)
  - System intents (Escape, Enter, Backspace, Space, Tab)
  - Edit intents (Save, Undo, Redo, Select All, Copy, Paste, Cut, Toggle Comment)
  - Function key intents (F1 Help)
* Enhanced `KeyListenerWrapper` widget with:
  - Full keyboard shortcut mapping for 20+ key combinations
  - Support for both Ctrl (Windows/Linux) and Cmd (macOS) modifiers
  - Reliable modifier key combination detection (Ctrl+X, Cmd+X, etc.)
  - HardwareKeyboard state checking for robust key event handling
  - Visual debug mode with SnackBar feedback showing modifiers
  - Comprehensive FocusNode management
  - Web-compatible focus handling
* Created comprehensive example application demonstrating:
  - Basic keystroke handling
  - Advanced keyboard shortcuts
  - Event logging and monitoring
  - Visual debug features
* Added comprehensive test suite covering:
  - All Intent classes (18+ tests)
  - Widget building and lifecycle (6+ tests)
  - FocusNode management and transitions
  - Edge cases and state changes
  - Advanced widget interactions
  - Total: 35+ individual tests
* Added MIT License
* Comprehensive documentation with usage examples, quick start guide, detailed usage patterns, platform-specific notes, and troubleshooting guide

