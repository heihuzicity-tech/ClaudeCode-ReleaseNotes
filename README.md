# Claude Code Release Notes

A comprehensive collection of Claude Code release notes, organized and maintained in both English and Chinese.

## 📁 Project Structure

```
ClaudeReleaseNotes/
├── README.md                        # This file
├── release-notes-organized.md       # English release notes (organized by version)
├── release-notes-cn.md             # Chinese release notes with descriptive titles
├── update-release-notes-prompt.md   # Template for updating release notes
└── release-notes-raw.md            # Original raw release notes (archived)
```

## 📋 Contents

### Release Notes Documents

- **English Version** (`release-notes-organized.md`): Complete release notes in English, organized from newest to oldest version
- **Chinese Version** (`release-notes-cn.md`): Translated release notes with descriptive titles for each version
- **Raw Archive** (`release-notes-raw.md`): Original unprocessed release notes for reference

### Utilities

- **Update Template** (`update-release-notes-prompt.md`): A prompt template for updating both English and Chinese release notes when new versions are released

## 🚀 Features

- **Bilingual Support**: Maintains synchronized English and Chinese documentation
- **Version Organization**: All versions sorted from newest to oldest for easy reference
- **Descriptive Titles**: Chinese version includes descriptive titles for quick understanding of each release's main features
- **Update Automation**: Template provided for consistent updates across both language versions

## 📝 How to Use

### Viewing Release Notes

1. For English readers: Open `release-notes-organized.md`
2. For Chinese readers: Open `release-notes-cn.md`
3. Versions are organized from newest (top) to oldest (bottom)

### Updating Release Notes

When a new Claude Code version is released:

1. Open `update-release-notes-prompt.md`
2. Copy the prompt template
3. Add the new release notes content
4. Use the prompt with Claude to update both documents simultaneously
5. Both language versions will be updated maintaining consistency

## 🔄 Version History

The project tracks all Claude Code versions from:
- **Latest**: Version 1.0.93 (Windows clipboard image paste support)
- **Earliest**: Version 0.2.21 (Fuzzy matching for commands)
- **Major Milestone**: Version 1.0.0 (General availability with Sonnet 4 and Opus 4)

## 📌 Key Version Highlights

### Recent Major Features
- **v1.0.93**: Windows clipboard image paste support
- **v1.0.81**: Output styles with educational modes
- **v1.0.71**: Background commands and customizable status line
- **v1.0.60**: Custom subagents for specialized tasks
- **v1.0.51**: Native Windows support

### Platform Support
- Windows (native support from v1.0.51)
- macOS (with Keychain support)
- Linux (including Alpine and musl-based distributions)
- WSL (Windows Subsystem for Linux)

## 🛠️ Maintenance

### Keeping Documents Synchronized

When updating, ensure:
1. Both English and Chinese versions have the same versions
2. Version numbers are in the same order
3. Chinese titles accurately reflect the main features
4. No speculative dates are added unless explicitly provided

### Format Standards

**English Document Format:**
```markdown
## Version X.X.X
• Feature or fix description
• Another feature or fix
```

**Chinese Document Format:**
```markdown
## 版本 X.X.X - 主要功能描述
• 功能或修复描述
• 另一个功能或修复
```

## 📊 Statistics

- **Total Versions Tracked**: 100+ releases
- **Major Version**: 1.0.x series (Generally Available)
- **Beta Version**: 0.2.x series (Pre-release)
- **Documentation Languages**: English, Chinese

## 🤝 Contributing

To contribute to this documentation:
1. Follow the existing format standards
2. Ensure bilingual consistency
3. Use the update template for new releases
4. Maintain chronological ordering (newest first)

## 📄 License

This documentation is maintained for the Claude Code community. Claude Code is a product of Anthropic.

## 🔗 Related Links

- [Claude Code Official Documentation](https://docs.anthropic.com/en/docs/claude-code)
- [Claude Code GitHub Issues](https://github.com/anthropics/claude-code/issues)
- [Anthropic Website](https://www.anthropic.com)

---

*Last Updated: Check the latest version in release notes documents*