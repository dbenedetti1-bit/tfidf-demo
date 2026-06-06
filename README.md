# TF-IDF Interactive Demo

A self-contained, step-by-step visual explanation of the TF-IDF algorithm — no installation, no dependencies, runs directly in the browser.

**[→ Live demo](https://your-username.github.io/tfidf-demo/)** *(update link after enabling GitHub Pages)*

---

## What is TF-IDF?

**TF-IDF** (Term Frequency – Inverse Document Frequency) is a numerical statistic used in information retrieval and natural language processing to measure how important a word is to a document within a collection. Words that appear often in a specific document but rarely across the corpus get a high score — words that are common everywhere (like "the", "is") get a low one.

---

## How the demo works

The demo guides the user through 5 sequential steps, each activated by a button. A corpus of 5 short scientific texts (Physics, Biology, Chemistry, Computer Science, Mathematics) is used throughout.

### Step 0 — Preprocessing
Tokenization and stopword removal. See exactly which words survive and which are discarded before any calculation begins.

### Step 1 — Dictionary
All unique surviving terms are collected into a shared vocabulary, sorted alphabetically. Navigate with the mouse or ↑ ↓ arrow keys. Selecting a word highlights every occurrence in the document viewer on the left.

### Step 2 — Term Frequency (TF)
For each document, a vector aligned to the dictionary is shown, with raw word counts and normalized TF values. Selecting a word highlights its occurrences so you can verify the count directly in the text.

> `TF(t, d) = count(t, d) / |d|`

### Step 3 — Document Frequency & IDF
For each term in the vocabulary, the demo shows which documents contain it (as colored dots), the document frequency (DF), and the resulting IDF weight. Rare terms get a higher IDF; terms present in all documents get IDF = 0.

> `IDF(t) = log( N / df(t) )`

### Step 4 — TF-IDF Final Vectors
The final TF-IDF vector for each document is displayed, with the top 3 most discriminating terms highlighted. Switch between documents to compare how each one is characterized by different vocabulary.

> `TF-IDF(t, d) = TF(t, d) × IDF(t)`

---

## Features

- **Bidirectional interaction**: click a word in the dictionary → it highlights in the text; click a word in the text → it selects in the dictionary
- **Step-by-step progression**: each phase must be explicitly unlocked, mirroring the algorithm's logical sequence
- **Corpus of 5 documents**: chosen to produce meaningful overlap and contrast between vocabularies
- **Zero dependencies**: plain HTML + CSS + JavaScript, no build step, no frameworks

---

## Running locally

Just open `index.html` in any modern browser — no server needed.

```
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux
```

---

## Deploying to GitHub Pages

1. Push `index.html` (and this README) to a GitHub repository
2. Go to **Settings → Pages**
3. Under *Source*, select **Deploy from a branch → main → / (root)**
4. Click **Save** — the site will be live at `https://<your-username>.github.io/<repo-name>/`

---

## Corpus

| Document | Topic |
|----------|-------|
| Physics | Matter, energy, quantum mechanics, relativity |
| Biology | Cells, DNA, evolution, ecosystems |
| Chemistry | Atoms, molecules, chemical bonds, reactions |
| Computer Science | Algorithms, data structures, networks, machine learning |
| Mathematics | Numbers, functions, theorems, proofs |

---

## Educational context

This demo was built for classroom use to make the TF-IDF construction process tangible and inspectable. It is intentionally minimal: no stemming, no advanced weighting schemes — just the core algorithm made visible.

---

*Built with Claude Code · [Anthropic](https://anthropic.com)*
