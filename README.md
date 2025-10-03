# 📑 Lecture Slides with Jekyll + Reveal.js

This repository hosts lecture slides built using [Reveal.js](https://revealjs.com/) on top of a simple [Jekyll](https://jekyllrb.com/) site. It provides a clean and reproducible way to organize multiple lecture decks, render them as interactive slides, and optionally extend them with features like math rendering and audio narration.


## 🚀 Features

| Feature                              | Description                                                         |
| ------------------------------------ | ------------------------------------------------------------------- |
| **Markdown-based slides**            | Write slides in plain Markdown (`index.md` in each lecture folder). |
| **Reveal.js integration**            | Modern HTML5 slides with themes, transitions, code highlighting, and MathJax. |
| **Multi-lecture organization**       | Each lecture lives in its own folder (`lecture1/`, `lecture2/`, …) and is fully self-contained (slides + images + assets). |
| **Automatic lecture index**.         | The home page lists all lectures as cards with clickable links. |
| **Math support**                     | LaTeX equations rendered with MathJax (`$x^2$, $\alpha$, …`).   |
| **Custom styling**                   | Extend via `assets/custom.css`.                                 |
| *(Experimental)* **Audio narration** | Reveal.js plugin support is included for recording or embedding per-slide audio. |


## 📂 Repository Structure

```bash
$ tree
.
├── _config.yml         # Jekyll configuration
├── _layouts/slide.html # Layout for slides
├── index.html          # Main landing page (lists lectures as cards)
├── lecture1/
│ └── index.md          # Markdown source for Lecture 1 slides
├── lecture2/
│ └── index.md
├── lecture3/
│ └── index.md
├── assets/
│ ├── reveal/           # Reveal.js core + plugins
│ └── custom.css        # Optional CSS overrides
└── README.md
```


- **Each lecture folder** contains a single `index.md` file (with front matter + slides).  
- **Slides are separated** using `---` (horizontal) and `--` (vertical) markers inside the Markdown.

---

## 🖥️ Usage

### 1. Run locally

Install dependencies:

```bash
gem install bundler jekyll
bundle install
```

Serve site locally:

```bash
bundle exec jekyll serve
```

Then open http://127.0.0.1:4000 in your browser.

### 2. Write slides

Inside `lectureX/index.md`, for example [lecture1/index.md](./lecture1/index.md) use standard Markdown:

```markdown
---
layout: slide
title: Lecture 1: Quantum Basics
---

# Introduction

Welcome to **Quantum Basics**.

---

## Schrödinger Equation

The time-dependent form is:

$$ i \hbar \frac{\partial}{\partial t} \Psi = \hat{H} \Psi $$
```

- `---` creates new slide (horizontal)
- `--` creates new sub-slide (vertical)
- `Note:` adds speaker notes.

### 3. Deploy

This repo can be hosted on Github Pages directly. Push your github repo -> Slides auto-publish -> share the URL!


## 🎨 Customization

- Change slide theme in [`_layouts/slide.html`](./_layouts/slide.html) (e.g. black.css, white.css, night.css).

- Adjust fonts, colors, or layout in [`assets/css/custom.css`](./assets/css/custom.css).

- Add `Reveal.js` plugins (math, zoom, notes, search, audio, …) via [`assets/reveal/plugin`](./assets/reveal/plugin/).

## 🎙️ Audio Narration (Optional)

This setup includes support for [reveal.js-plugins/audio-slideshow](https://github.com/rajgoel/reveal.js-plugins/tree/master/audio-slideshow).

- Press r to record narration per slide (browser will ask for microphone access).

- Press z to download recordings as a ZIP.

- Place exported audio files in the same lecture folder to bundle with slides.

_(Experimental: may require additional setup.)_

## 🙌 Contributing

Contributions and suggestions are welcome! Open an issue or PR if you’d like to add features, fix bugs, or improve documentation.

## 🔗 Credits

- [Reveal.js](https://revealjs.com/) by Hakim El Hattab
- [Jekyll](https://jekyllrb.com/) for site generation
- [reveal.js-plugins](https://github.com/rajgoel/reveal.js-plugins) for audio support.