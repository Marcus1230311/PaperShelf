PaperShelf

A lightweight, local-first research paper library built around web references, continuous reading, and AI-curated discovery.

PaperShelf is designed for one simple workflow:

ChatGPT finds the papers worth reading → you paste the list into PaperShelf → PaperShelf identifies, deduplicates, organizes, and keeps them ready to read.

The released app is a single self-contained HTML file. No installer, no server, no account, and no platform-specific package is required.

✨ Highlights

Single-file app — the final build is just PaperShelf.html / index.html

Cross-platform — works in modern browsers on Windows, macOS, Linux, iPadOS, iOS, and Android

Local-first — your paper library, notes, priorities, tags, and reading state stay in browser storage

Web-first / reference-first — PaperShelf stores references and metadata instead of forcing local PDF downloads

GPT list import — paste a daily paper list directly from ChatGPT

Single-link import — paste one paper URL when you find something manually

Strong deduplication — one paper stays one record even if it appears on multiple supported sites

Continuous reading — optimized for scrolling through web/HTML versions rather than page-by-page PDF reading

Bilingual UI — Chinese / English

Theme support — Light / Dark / Follow System

Notes & prioritization — Takeaway, Notes, Why I Saved This, Priority, Starred, Tags, Reading Status

Backup & export — JSON backup/restore and structured export support

📚 Supported paper sources

PaperShelf can recognize and normalize references from sources such as:

arXiv

Hugging Face Papers

OpenReview

Semantic Scholar

DOI / publisher links

A paper discovered on one site is not added again when the same paper appears on another site.

PaperShelf prefers strong identifiers for deduplication:

arXiv ID

DOI

OpenReview ID

Semantic Scholar ID

normalized title + author matching as fallback

Additional sources may enrich the same paper record with metadata, venue information, code/project links, or alternative reading URLs.

🚀 Typical workflow

Daily workflow

Ask ChatGPT for a curated list of papers worth reading.

Copy the whole result.

Open PaperShelf.

Click Add Papers.

Paste the list.

Import.

PaperShelf parses the list, detects supported paper references, deduplicates them, and adds the new papers to your library.

Manual single-paper workflow

Paste any supported paper URL into Add Papers:

https://arxiv.org/abs/xxxx.xxxxx

or:

https://huggingface.co/papers/xxxx.xxxxx

or an OpenReview / Semantic Scholar / DOI link.

No separate “single import” mode is required.

🧠 Recommended ChatGPT output format

PaperShelf is designed to accept human-readable lists, so JSON is not required.

A good daily recommendation can look like this:

1. Paper Title
   中文标题：论文中文标题
   Score: 95
   Topic: Agent / Memory
   Reason: Why this paper is worth reading.
   Source: https://arxiv.org/abs/xxxx.xxxxx

2. Another Paper
   Score: 91
   Topic: Multimodal
   Reason: ...
   Source: https://huggingface.co/papers/xxxx.xxxxx

Markdown tables, numbered lists, multiple URLs, and structured JSON can also be supported by the importer.

📖 Reading model

PaperShelf is intentionally not PDF-first.

The preferred reading order is:

Paper card — title, abstract, recommendation reason, personal notes

Continuous reader — use an HTML/web version when available

Open Original — open the canonical source when the site cannot be embedded or fetched

This keeps the reading experience responsive across desktop, tablet, and phone.

Some external websites restrict cross-origin requests or iframe embedding through browser security policies. In those cases, PaperShelf keeps the reference and opens the original source directly.

🗂 Library organization

Each paper can keep:

Original title

Chinese title

Authors

Abstract

Chinese abstract

Source URLs

GPT recommendation score

GPT recommendation reason

Personal priority

Starred state

Tags

Collections

Reading status

Personal takeaway

“Why I saved this”

Notes

Last opened time

Reading progress where supported

Suggested reading states:

Unread

Queue

Reading

Read

📝 Notes philosophy

PaperShelf keeps notes intentionally lightweight.

The goal is not to become another Notion or Obsidian. The useful parts are:

GPT Recommendation — why the paper was recommended

My Takeaway — your one-sentence conclusion

Why I Saved This — why it mattered to you

Notes — free-form personal notes

AI-generated content and personal notes are kept separate.

🎨 UI principles

PaperShelf is designed around:

content-first layout

minimal visual noise

responsive desktop / tablet / mobile layouts

readable typography

light and dark themes

progressive disclosure

quick scanning

distraction-free reading

no unnecessary dashboards

no fake storage/download statistics

The interface may take inspiration from modern motion-rich web design, but readability and research efficiency always take priority over visual effects.

🔐 Privacy & local data

PaperShelf is local-first.

Your library data is stored in the browser using technologies such as IndexedDB/local browser storage.

There is no required account and no required cloud backend.

Important

Browser storage is isolated by browser/profile/device.

For example:

Edge on Windows

Safari on iPad

Chrome on Android

do not automatically share the same local PaperShelf database.

Use Backup / Restore when moving your library between devices.

Cloud sync may be added later if it proves useful.

💾 Backup

Regularly export a PaperShelf backup:

papershelf-backup-YYYY-MM-DD.json

A backup can preserve library metadata, notes, tags, reading states, priorities, collections, and settings.

🌐 Cross-platform use

The production build is intentionally distributed as one HTML file.

PaperShelf.html

or, for GitHub Pages:

index.html

This makes PaperShelf easy to move between:

Windows

macOS

Linux

iPad

iPhone

Android

No EXE, DMG, App Store package, code signing, or installer is required for the web version.

🧱 Development architecture

The project can be developed using modular source code:

src/
├─ app.ts
├─ core.ts
├─ db.ts
├─ importer.ts
├─ dedupe.ts
├─ reader.ts
├─ notes.ts
├─ i18n.ts
├─ theme.ts
├─ styles.css
└─ index.template.html

The build process compiles and bundles everything into one self-contained HTML file:

TypeScript + CSS + HTML
          ↓
        Build
          ↓
     PaperShelf.html

This keeps development maintainable while keeping distribution extremely simple.

🗺 Roadmap

Possible future additions — only if real usage justifies them:

optional cloud sync

PWA / Add to Home Screen support

richer citation export

smarter metadata enrichment

better source fallback

improved mobile reading

code / project page enrichment

optional PDF support

optional offline article cache

PDF management is intentionally not a core requirement in the current product direction.

⚠️ Current limitations

Browser CORS policies may prevent direct metadata fetching from some websites.

Some publishers block iframe embedding.

Local browser databases do not automatically sync between devices.

The web version cannot provide the same unrestricted filesystem access as a native desktop app.

Metadata enrichment should never block importing a paper reference.

PaperShelf is designed so that a failed enrichment request does not cause the paper itself to be lost.

📦 Deployment

For GitHub Pages, rename the release file to:

index.html

and place it at the repository root.

A minimal repository can simply be:

PaperShelf/
├─ index.html
└─ README.md

Status

PaperShelf is currently under active development.

The current focus is the core loop:

Discover → Import → Deduplicate → Read → Prioritize → Note → Retrieve

Features are intentionally kept focused until this workflow is stable and pleasant to use.

License

License not selected yet.

If the repository will be public and open source, add a LICENSE file before encouraging reuse or redistribution.
