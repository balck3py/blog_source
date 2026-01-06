# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a **personal technical knowledge base** (技术知识库) containing technical documentation and study notes written in Chinese. The author is Eugen.

## Directory Structure

```
00.技术积累/
├── 01.后端/       # Backend (.NET Core focus): GC, threading, memory, concurrency
├── 02.前端/       # Frontend (currently empty)
├── 03.DevOps/     # DevOps: K9s, Docker, Ubuntu
├── 04.通用/       # General topics (currently empty)
├── 05.AI/         # AI topics (currently empty)
├── 00.assets/     # Images for embedding in articles
├── rule.md        # Documentation writing standards (MUST READ before creating content)
├── TOTO.md        # Planned future topics
└── GEMINI.md      # Directory overview
```

## Content Creation Requirements

**Before creating or editing any documentation**, read `rule.md` for the complete formatting guide. Key requirements:

- **YAML Frontmatter**: All documents must start with title, date, author (Eugen), and tags
- **Language**: Chinese with English technical terms (first mention bilingual, e.g., `垃圾回收（Garbage Collection，简称 GC）`)
- **Headings**: Use emoji icons for visual hierarchy (see rule.md §3.2 for emoji reference)
- **Code blocks**: Must specify language (`csharp`, `bash`, `yaml`, etc.) and include Chinese comments
- **Images**: Store in `00.assets/`, reference with Obsidian syntax: `![[../00.assets/filename.png]]`
- **File naming**: `[序号]. [Title].md` (e.g., `01. Dot Net Core 中的 GC.md`)

## Document Structure Template

```markdown
---
title: [文档标题]
date: YYYY-MM-DD
author: Eugen
tags:
  - [关键词1]
  - [关键词2]
---
# 🎯 [文档主标题]

> [简介/引言]

---

## 1. 章节标题

### 1.1 子章节

[内容...]

### 📝 小结

> [章节要点总结]

---

## 📚 总结

[文档总结]
```

## Git Workflow

The repository uses automated vault backups. Commit messages for manual changes should be descriptive of the content changes.
