# 中英双语简历模板

简洁的单页 LaTeX 简历模板，内置中英双语支持。在同一个 `.tex` 文件中编写内容，一次编译生成对应语言的 PDF。

## 特性

- **单源双输出** — 使用 `\en{}` 和 `\zh{}` 宏在一个文件中编写双语内容
- **单页紧凑排版** — A4 纸面、9pt 字号、窄边距、专业分节样式
- **FontAwesome 图标** — 电话、邮箱、GitHub、LinkedIn、个人主页
- **XeTeX + CJK** — 自动适配 Windows / macOS / Linux 中文字体
- **简单构建** — `make en` / `make zh` / `make all`

## 快速开始

### 环境要求

- [TeX Live](https://www.tug.org/texlive/)（full 或 medium）或 [MacTeX](https://www.tug.org/mactex/)
- XeTeX（已包含在 TeX Live / MacTeX 中）

### 编译

```bash
make en     # 生成英文 PDF  -> resume-en.pdf
make zh     # 生成中文 PDF  -> resume-zh.pdf
make all    # 同时生成两版
make clean  # 清理编译产物
```

### 自定义

1. 编辑 `resume.tex` — 将占位文字（`Your Name`、`你的姓名`、`XX大学` 等）替换为你自己的信息
2. 如需照片：将图片文件放入目录，取消注释 header 区域的 `\includegraphics` 行
3. 按需增删章节 — 各 section 相互独立

## 双语模式原理

模板通过编译时标志 `\resumezh` 切换语言：

```latex
\en{This text appears only in the English PDF}
\zh{这段文字只出现在中文 PDF 中}
不包裹在 \en{}/\zh{} 中的内容在两个版本中都会出现
```

- `make en` 不定义该标志 → `\en{}` 生效，`\zh{}` 被忽略
- `make zh` 定义 `\def\resumezh{1}` → `\zh{}` 生效，`\en{}` 被忽略

## 文件结构

```
.
├── resume.tex    # 主源文件（编辑此文件）
├── resume.cls    # 文档样式类
├── Makefile      # 构建命令
├── .gitignore    # 忽略 LaTeX 编译产物
└── README.md
```

---

# Bilingual Resume Template (EN/ZH)

A clean, one-page LaTeX resume template with built-in bilingual support (English & Chinese). Write your content once, generate both language versions from a single source file.

## Features

- **Single source, dual output** — use `\en{}` and `\zh{}` macros to write bilingual content in one `.tex` file
- **One-page, compact layout** — A4 paper, 9pt font, tight margins, professional section formatting
- **FontAwesome icons** — phone, email, GitHub, LinkedIn, homepage
- **XeTeX + CJK support** — automatic CJK font selection across Windows, macOS, and Linux
- **Simple build system** — `make en` / `make zh` / `make all`

## Quick Start

### Prerequisites

- [TeX Live](https://www.tug.org/texlive/) (full or medium) or [MacTeX](https://www.tug.org/mactex/)
- XeTeX (included in TeX Live / MacTeX)

### Build

```bash
make en     # Generate English PDF  -> resume-en.pdf
make zh     # Generate Chinese PDF  -> resume-zh.pdf
make all    # Generate both
make clean  # Remove build artifacts
```

### Customize

1. Edit `resume.tex` — replace all placeholder text (`Your Name`, `XX大学`, etc.) with your own info
2. Optionally add a photo: place your image file in the directory and uncomment the `\includegraphics` line in the header section
3. Add or remove sections as needed — each section is independent

## How Bilingual Mode Works

The template uses a compile-time flag (`\resumezh`) to switch languages:

```latex
\en{This text appears only in the English PDF}
\zh{This text appears only in the Chinese PDF}
Content outside \en{}/\zh{} appears in both versions
```

- `make en` compiles without the flag → `\en{}` is active, `\zh{}` is suppressed
- `make zh` compiles with `\def\resumezh{1}` → `\zh{}` is active, `\en{}` is suppressed

## File Structure

```
.
├── resume.tex    # Main source file (edit this)
├── resume.cls    # Document class (styling & layout)
├── Makefile      # Build commands
├── .gitignore    # Ignore LaTeX artifacts
└── README.md
```

## License

MIT
