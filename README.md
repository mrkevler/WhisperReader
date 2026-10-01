# 📖 WhisperReader by mrKevler

A simple macOS app that turns text and documents into AI speech in Polish and English. Paste, drop, listen, or export Markdown to PDF. Your content stays on your Mac.

A free community project for everyday reading — no account, API key or subscription required.

Repository: [mrkevler/WhisperReader](https://github.com/mrkevler/WhisperReader)

---

## 🔍 Table of Contents

- [✨ Features](#-features)
- [📦 Downloads](#-downloads)
- [🚀 Installation](#-installation)
- [📄 Supported Formats](#-supported-formats)
- [🎨 Markdown to PDF](#-markdown-to-pdf)
- [🔒 Privacy](#-privacy)
- [⌨ Shortcuts](#-shortcuts)
- [💬 Feedback](#-feedback)
- [📝 License](#-license)

---

## ✨ Features

- 📋 **Paste & read** — listen to copied text with one click.
- 📁 **Document import** — open or drop a file, check its text and listen from the beginning.
- 🎚 **Playback controls** — adjust speed from **0.5× to 2×**, pause, resume or stop.
- 🌍 **Polish and English** — choose a male or female voice, with the reading language and interface language set separately.
- ✏️ **Markdown preview** — readable headings, lists, quotes, tables and code, with source editing.
- 📄 **PDF export** — turn pasted text or an imported document into a formatted PDF.
- 🔒 **Local AI speech** — read offline after the initial voice download; saved audio can be replayed without generating it again.

## 📦 Downloads

**Version 1.1.0 · macOS 14 or newer · Apple Silicon (M1 or newer)**

- [Download WhisperReader for macOS](WhisperReader-1.1.0-macOS-AppleSilicon.zip)
- [View the sample PDF](WhisperReader-by-mrKevler_sample-text.pdf)

> The current build is signed locally (ad hoc), has not been notarized by Apple and is still awaiting public distribution verification. macOS may warn about or block a downloaded copy. Read the macOS security notice before deciding whether to open it.

## 🚀 Installation

1. Unzip the package, move **Whisper Reader.app** to **Applications**, and open it.
2. Read the model terms beside **Download AI voice**, then download the voice. The one-time setup needs internet access and downloads about **400 MB** of model files, plus additional space for the runtime, libraries and download cache.
3. Choose **Polski** or **English** as the reading language, and a **male or female voice**.
4. Copy text and click **Paste & read**, or drop a supported document into the window.
5. Adjust the speed and use **Pause**, **Resume** or **Stop** while listening.

The interface starts in Polish when Polish is your primary system language; otherwise, it starts in English. Change it in **Settings**. Your language, voice and speed preferences are remembered.

Import, preview and PDF export work before downloading the AI voice. To export copied text, click **Paste**, then **PDF**.

If voice setup is interrupted or the voice stops loading, choose **Repair or download AI voice…** from the app menu. Existing downloads are reused where possible.

---

## 📄 Supported Formats

| Format | Extensions |
| --- | --- |
| PDF, including scanned pages with local text recognition | `.pdf` |
| Word and OpenDocument text | `.docx`, `.doc`, `.odt` |
| Markdown | `.md`, `.markdown`, `.mdown` |
| Plain and rich text | `.txt`, `.rtf` |
| Saved HTML documents | `.html`, `.htm` |

PDFs are read in page order. Complex columns, tables and poor scans can affect extraction, so check the preview. Text inside images in Word or ODT files is not recognized. Password-protected documents need an unlocked copy.

Saved HTML is imported without downloading external resources. Importing a website by URL is not supported.

## 🎨 Markdown to PDF

Export Markdown as an A4 document with selectable text, Polish characters, headings, lists, tables and page numbers.

Code blocks use a monospaced font, a language label and a subtle frame. Long lines wrap, and long blocks continue onto the next page. Code stays clearly separated in the PDF, without a copy button.

The preview supports common Markdown. Scripts are not executed, remote images are not downloaded, and diagrams or LaTeX are not rendered as graphics. Reading aloud removes formatting markers while keeping the content, including code.

## 🔒 Privacy

Speech runs on your Mac using **Supertonic 3 through ONNX Runtime**, with preset male **M2** and female **F5** voices. No voice recording is required. The speech is machine-generated, not an authentic statement by a real person.

- Text, documents and generated speech are processed locally and are not uploaded to a voice service.
- No analytics or telemetry. Preferences stay on your Mac. There is no separate text history, but saved audio contains the spoken content of your texts, including private material.
- Initial setup downloads the model and runtime. Reading and PDF generation then work offline.
- Generated audio stays in a local cache after playback and after closing the app, so repeated text can play without another generation step.
- The cache targets **256 MiB**. During cleanup, it removes recordings unused for **30 days**, then the least recently used files as needed. Active recordings are protected and can temporarily exceed the limit; cleanup does not run while the app is closed.
- To remove saved recordings, stop reading and choose **Clear saved audio** from the app menu. Audio used by another open copy remains protected until that reading session ends.
- External website links open only when you choose them.

The model loads only when a new audio fragment needs to be generated, not at app startup or when replaying cached audio. Generation uses two CPU threads, and the model is unloaded after 60 seconds once reading has finished or stopped, or during a longer pause.

AI speech may mispronounce names, abbreviations or numbers. Generation speed depends on your Mac and its workload. Choose the reading language manually; mixed-language text uses the selected voice setting throughout.

---

## ⌨ Shortcuts

| Action | Shortcut |
| --- | --- |
| Paste and read | Shift + Command + V |
| Open a document | Command + O |
| Read from the beginning | Command + Return |
| Stop reading | Command + . |
| Export PDF | Shift + Command + E |
| Settings | Command + , |

## 💬 Feedback

Found a problem or have an idea? Open an [issue](https://github.com/mrkevler/WhisperReader/issues) with your macOS version, Mac chip and steps to reproduce it. Remove personal or confidential content from shared examples.

## 📝 License

Free for personal use under the included EULA: [English](LICENSE.en.md) · [Polski](LICENSE.pl.md).

The app is closed-source. This repository contains the app package, this README, both license versions and a sample PDF. Your documents and exported PDFs remain yours. Third-party components and models retain their own licenses; notices are included in the app. The Supertonic 3 model uses [OpenRAIL-M](https://huggingface.co/supertone-oss-archive/supertonic-3/blob/aafc6e32416a594460b32413efc49d7fe4ce6d46/LICENSE), including section 5 and the restrictions in Attachment A. Separate model terms in Polish and English, together with the complete original license, are available offline in the app beside the voice download and in the credits. These model terms do not change the app EULA.

---

Crafted with ♥ by [mrKevler](https://bartoszsergot.com)
