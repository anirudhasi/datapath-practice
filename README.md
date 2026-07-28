# DataPath — Practice Notebooks

Runnable code for every lesson on the DataPath site. Each notebook is **self-contained**:
open it, run the cells top to bottom, and you reproduce exactly what the lesson shows —
same datasets, same numbers, same plots.

## Layout

```
practice/
├── requirements.txt
├── data/                      # real datasets, committed so notebooks just run
├── deep-learning/
│   ├── 016_backprop_how.ipynb
│   └── …one notebook per lesson
├── generative-ai/
├── langgraph/
└── …one folder per track
```

The naming matches the site: lesson `016` on `/deep-learning/016/` is
`deep-learning/016_*.ipynb` here, and the lesson page links straight to it.

## Running them

**In your browser, nothing to install** — open any notebook in Google Colab:

```
https://colab.research.google.com/github/anirudhasi/datapath-practice/blob/main/<path>
```

**Locally:**

```bash
git clone https://github.com/anirudhasi/datapath-practice.git
cd datapath-practice
python -m venv .venv && source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter lab
```

## Where the code comes from

These notebooks are **rebuilt, not copied**. The course author published Colab
notebooks alongside his videos; those are held privately as reference so that our
versions use the **same datasets, the same hyperparameters and produce the same
numbers** — but the implementation, commentary and exercises here are our own.

That matters for two practical reasons beyond the obvious one:

- His Colab links point at personal Drive files. They can be moved or revoked at
  any time, and a lesson linking straight to one would silently 404. Ours won't.
- Rebuilding means we can fix what's wrong. The reference backprop notebook has a
  bias-update typo; our lesson 016 reproduces it deliberately (the published loss
  figures come from the buggy version) and makes finding it an exercise.

Datasets live in `data/` so every notebook is self-contained — no uploading a CSV
to `/content/` before anything runs, which is what the originals require.

## House rules for these notebooks

So they stay useful as a practice set rather than a wall of code:

1. **Runnable top to bottom** on a fresh kernel, with no manual edits.
2. **No hidden state** — every dataset is generated or downloaded in the notebook itself.
3. **Numbers match the lesson.** Random seeds are fixed so the printed loss is the loss
   the lesson quotes.
4. **From scratch first, framework second.** Where a lesson derives something by hand, the
   notebook implements it in NumPy *and* verifies it against Keras/PyTorch, so you can see
   the two agree.
5. **Exercises at the end.** Each notebook closes with a few "now change this and see what
   happens" prompts, with answers collapsed.

## Status

| Track | Notebooks | Lessons |
|---|---|---|
| Deep Learning | 1 | 84 |
| everything else | 0 | 119 |

Populated alongside the lesson enrichment — a notebook lands when its lesson is enriched.
