# GEMINI.md

This file provides guidance to Gemini when working with code in this repository.

## Repository Overview

This is a **personal technical knowledge base** (技术知识库) containing technical documentation and study notes written in Chinese. The author is Eugen.

The main purpose of this repository is to store and manage technical articles on various topics, including backend development, DevOps, and AI.

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
├── CLAUDE.md      # Guidance for another AI model
└── GEMINI.md      # This file, the directory overview
```

## Key Files

*   `rule.md`: This is the most important file in the repository. It defines the **documentation writing standards**, including file naming, content structure, formatting, and style. **You must read and follow these rules before creating or editing any content.**
*   `TOTO.md`: This file lists the topics that are planned for future documentation.
*   `CLAUDE.md`: This file provides guidance for the Claude AI model, similar to this file.

## Content Creation and Modification

When you are asked to create or modify a document, you must adhere to the standards defined in `rule.md`.

Here is a summary of the key requirements:

*   **File Naming**: `[序号]. [Title].md` (e.g., `05. Dot Net中的锁和并发控制.md`).
*   **YAML Frontmatter**: All documents must start with a YAML frontmatter including `title`, `date`, `author` (always `Eugen`), and `tags`.
*   **Language**: Use Chinese (Simplified) for the main content. Technical terms should be in English with a Chinese translation on the first use, like `垃圾回收 (Garbage Collection, GC)`.
*   **Headings**: Use emoji icons for visual hierarchy. The `rule.md` file has a reference table for which emojis to use.
*   **Code Blocks**: Must specify the language (e.g., `csharp`, `bash`, `yaml`) and include Chinese comments to explain the code.
*   **Images**: All images are stored in the `00.assets/` directory. Use the Obsidian-style wiki link `![[../00.assets/filename.png]]` to embed images.
*   **Structure**: Follow the document structure template provided in `rule.md`, including an introduction, optional table of contents, sections with summaries, and a final conclusion for longer articles.

### Quick Guide to Creating a New Document

1.  **Choose a topic and filename**: Check `TOTO.md` for ideas. Create a filename like `06. My New Topic.md` in the appropriate category directory.
2.  **Add the Frontmatter**:
    ```yaml
    ---
    title: My New Topic
    date: YYYY-MM-DD
    author: Eugen
    tags:
      - tag1
      - tag2
    ---
    ```
3.  **Write the content**: Follow the structure, style, and formatting rules from `rule.md`.
4.  **Review**: Ensure all requirements from the quality checklist in `rule.md` are met.
