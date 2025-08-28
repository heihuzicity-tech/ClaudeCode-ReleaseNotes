# Claude Code Release Notes 更新提示词模板

## 使用方法
当 Claude Code 有新版本发布时，复制以下提示词并附上新的 release notes 内容，让 Claude 帮你更新文档。

---

## 提示词模板

请将以下新版本的 release notes 同时更新到项目中的英文和中文两份文档中：
- 英文文档：`release-notes-organized.md`
- 中文文档：`release-notes-cn.md`

要求：
1. 将新版本插入到文档顶部（最新版本在最上面）
2. 保持版本号从新到旧的排序
3. 不要添加推测的日期，除非 release notes 中明确提供了日期
4. 保持现有文档的格式风格
5. 如果新版本号已存在，请更新而不是重复添加
6. 英文文档保持原始格式（## Version X.X.X）
7. 中文文档需要：
   - 翻译为中文
   - 为每个版本添加描述性标题（格式：## 版本 X.X.X - 主要功能描述）
   - 保持与英文文档相同的版本顺序

新版本内容：
```
[在这里粘贴新的 release notes 内容]
```

---

## 示例

假设新版本是 1.0.95，使用方式如下：

```
请将以下新版本的 release notes 同时更新到项目中的英文和中文两份文档中：
- 英文文档：`release-notes-organized.md`
- 中文文档：`release-notes-cn.md`

要求：
1. 将新版本插入到文档顶部（最新版本在最上面）
2. 保持版本号从新到旧的排序
3. 不要添加推测的日期，除非 release notes 中明确提供了日期
4. 保持现有文档的格式风格
5. 如果新版本号已存在，请更新而不是重复添加
6. 英文文档保持原始格式（## Version X.X.X）
7. 中文文档需要：
   - 翻译为中文
   - 为每个版本添加描述性标题（格式：## 版本 X.X.X - 主要功能描述）
   - 保持与英文文档相同的版本顺序

新版本内容：
```
Version 1.0.95:
• New feature: Added support for XYZ
• Fixed bug in ABC component
• Performance improvements for DEF operation
```
```

## 更新后的示例输出

### 英文文档 (release-notes-organized.md)
```markdown
## Version 1.0.95
• New feature: Added support for XYZ
• Fixed bug in ABC component
• Performance improvements for DEF operation

## Version 1.0.93
• Windows: Add alt + v shortcut for pasting images from clipboard
[...]
```

### 中文文档 (release-notes-cn.md)
```markdown
## 版本 1.0.95 - XYZ支持与性能优化
• 新功能：添加了对 XYZ 的支持
• 修复了 ABC 组件中的错误
• DEF 操作的性能改进

## 版本 1.0.93 - Windows 剪贴板图片粘贴支持
• Windows：添加 Alt + V 快捷键用于从剪贴板粘贴图片
[...]
```

## 备注
- 文档位于项目根目录
- 如果需要查看当前文档内容，可以要求：「请先显示两份 release notes 文档的前几个版本，确认当前格式」
- 中文标题应该简洁概括该版本的主要更新内容