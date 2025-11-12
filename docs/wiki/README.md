# 📚 Windsurf Reset Wiki Documentation

This directory contains the complete wiki documentation for Windsurf Reset.

## 📖 How to Use These Docs

### Option 1: Upload to GitHub Wiki (Recommended)

1. **Enable Wiki** on your GitHub repository:
   - Go to your repository settings
   - Enable the Wiki feature

2. **Clone the Wiki repository**:
   ```bash
   git clone https://github.com/yuzeguitarist/Windsurf-Reset.wiki.git
   ```

3. **Copy all wiki files**:
   ```bash
   cp docs/wiki/*.md Windsurf-Reset.wiki/
   cd Windsurf-Reset.wiki
   ```

4. **Commit and push**:
   ```bash
   git add .
   git commit -m "Add complete wiki documentation"
   git push origin master
   ```

5. **Your wiki is now live!**
   - Access at: `https://github.com/yuzeguitarist/Windsurf-Reset/wiki`

---

### Option 2: Keep in Repository

These files can stay in `docs/wiki/` and be accessed directly from the repository.

**Benefits:**
- ✅ Version controlled with your code
- ✅ Easy to update with pull requests
- ✅ No separate wiki setup needed

**To link from README:**
```markdown
[📖 Documentation](docs/wiki/Home.md)
```

---

### Option 3: Build Documentation Site

You can use these markdown files with documentation generators:

**Using MkDocs:**
```bash
pip install mkdocs mkdocs-material
mkdocs new .
# Copy wiki files to docs/
mkdocs serve
```

**Using Docusaurus:**
```bash
npx create-docusaurus@latest website classic
# Configure and add wiki files
npm start
```

---

## 📑 Wiki Structure

```
docs/wiki/
├── Home.md                    # Wiki home page (start here)
├── Installation-Guide.md      # Detailed installation instructions
├── User-Guide.md              # Complete usage guide
├── FAQ.md                     # Frequently asked questions
├── Troubleshooting.md         # Problem solving guide
├── Technical-Details.md       # Technical architecture & details
├── License-Details.md         # Complete license information
└── README.md                  # This file
```

---

## 🌍 Multi-Language Support

All wiki pages include three languages:

- 🇬🇧 **English** - Primary documentation
- 🇨🇳 **中文** - Complete Chinese translation
- 🇩🇪 **Deutsch** - Complete German translation

Each page has language navigation links at the top.

---

## 📝 Content Overview

### [Home.md](Home.md)
- Wiki overview and welcome
- Quick navigation to all sections
- Getting started guide
- FAQ preview

### [Installation-Guide.md](Installation-Guide.md)
- System requirements
- Platform-specific installation (macOS, Windows, Linux)
- Post-installation setup
- Troubleshooting installation issues

### [User-Guide.md](User-Guide.md)
- Interface overview
- Basic operations (reset, restore)
- Advanced features
- Best practices
- Common scenarios

### [FAQ.md](FAQ.md)
- General questions
- Compatibility information
- Usage questions
- Licensing FAQs
- Technical FAQs
- Troubleshooting tips

### [Troubleshooting.md](Troubleshooting.md)
- Installation issues
- Detection problems
- Operation failures
- UI/Display issues
- Performance problems
- Advanced debugging

### [Technical-Details.md](Technical-Details.md)
- System architecture
- Technology stack
- Reset process flow
- File locations
- Security considerations
- Platform-specific details
- Performance metrics
- API documentation

### [License-Details.md](License-Details.md)
- Complete license terms
- Usage permissions
- Prohibited uses
- Modification requirements
- Commercial licensing
- Quick reference table

---

## ✏️ Updating Documentation

### Adding New Pages

1. Create a new `.md` file in `docs/wiki/`
2. Follow the multi-language structure
3. Add links to the new page in `Home.md`
4. Update this README if needed

### Editing Existing Pages

1. Edit the `.md` file directly
2. Maintain the three-language structure
3. Update all language sections
4. Test all internal links

### Style Guidelines

**Markdown Features:**
- Use headers (#, ##, ###) for structure
- Use tables for comparisons
- Use code blocks with language tags
- Use emoji for visual appeal (but sparingly)
- Use `<details>` tags for FAQs
- Use blockquotes for important notes

**Language Sections:**
- Always include all three languages
- Use `[English](#english)` anchor links
- Separate sections with `---`
- Keep translations synchronized

**Code Examples:**
```bash
# Always specify the language
command example here
```

---

## 🔗 Internal Linking

Link to other wiki pages using relative paths:

```markdown
See the [Installation Guide](Installation-Guide.md)
Check [FAQ](FAQ.md) for common questions
```

Link to sections within a page:

```markdown
See [Reset Process](#reset-process-flow)
Jump to [中文](#中文) section
```

---

## 📊 Wiki Statistics

| Metric | Count |
|--------|-------|
| **Total Pages** | 7 |
| **Languages** | 3 |
| **Sections** | ~50+ |
| **Word Count** | ~25,000+ |
| **Code Examples** | 100+ |
| **Tables** | 30+ |

---

## 🤝 Contributing to Documentation

Contributions to improve documentation are welcome!

**How to Contribute:**

1. Fork the repository
2. Create a branch for your documentation changes
3. Update the wiki files
4. Test all links and formatting
5. Submit a pull request

**What to Contribute:**
- Fix typos or grammar
- Add missing information
- Improve explanations
- Add more examples
- Translate to additional languages
- Update outdated information

---

## 📞 Need Help?

If you have questions about the documentation:

1. **Read the wiki** - Most questions are answered there
2. **Check FAQ** - Common questions are covered
3. **Search issues** - Someone may have asked before
4. **Open an issue** - We're happy to help!

---

## 📜 License

This documentation is part of Windsurf Reset and is covered by the same [Custom Open License](License-Details.md).

---

<div align="center">

**[🏠 Go to Wiki Home](Home.md)**

---

Made with ❤️ by [Yuze Pan](https://github.com/yuzeguitarist)

</div>
