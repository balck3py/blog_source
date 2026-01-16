# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a **personal technical knowledge base** (技术知识库) containing technical documentation and study notes written in Chinese. The author is Eugen.

## Directory Structure

```
├── 01.后端/       # Backend (.NET Core focus): GC, threading, memory, concurrency
├── 02.前端/       # Frontend: WebAssembly
├── 03.DevOps/     # DevOps: K9s, kubectx, Docker, Ubuntu, Git, Nginx, Dockerfile
├── 04.通用/       # General topics: Mihomo proxy
├── 05.AI/         # AI topics: Claude Code skills
├── 06.Other/      # Miscellaneous
├── 00.assets/     # Images for embedding in articles
├── rule.md        # Documentation writing standards (MUST READ before creating content)
├── TODO.md        # Planned future topics
└── _index.md      # Homepage with author CV
```

### File Naming
- Format: `[序号]. [Title].md` (e.g., `05. Dot Net中的锁和并发控制.md`)
- Use two-digit sequence numbers (01, 02, 03...)

### Required YAML Frontmatter
```yaml
---
title: [Document title]
date: YYYY-MM-DD
author: Eugen
tags:
  - [keyword1]
  - [keyword2]
---
```

### Language and Style
- Write in Chinese (Simplified)
- Technical terms: Chinese with English on first use (e.g., `垃圾回收 (Garbage Collection, GC)`)
- Use emoji icons in headings for visual hierarchy (see emoji table in `rule.md`)
- Friendly, professional tone using "你" (not "您")

### Code Blocks
- Always specify language (`csharp`, `bash`, `yaml`, `json`, etc.)
- Include Chinese comments explaining the code
- Use ✅/❌ markers to show correct vs incorrect patterns

### Images
- Store in `00.assets/` directory
- Use Obsidian wiki-link syntax: `![[../00.assets/filename.png]]`

### Document Structure
1. Frontmatter
2. Main title with emoji (e.g., `# 🧹 GC 完全指南`)
3. Introduction in blockquote format
4. Optional table of contents for long documents
5. Sections with `### 📝 小结` summaries
6. Final `## 📚 总结` for longer articles
