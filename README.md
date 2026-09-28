# jev-basic

Beginner-friendly, step-by-step Jupyter notebooks for learning the [TypeSafe AI](https://docs.typesafe.ai) Python SDK (`typesafe_sdk`) — one use case per notebook, explained from scratch.

Every notebook is self-contained: install the SDK, paste your API key, and run the cells top to bottom.

## The 3 building blocks

Every use case below is built from just 3 question types:

| Primitive | What it does | Analogy |
|---|---|---|
| `Choice` | Picks one label out of a list | Dropping a letter into one of several labeled mailboxes |
| `Score` | Rates text on an ordered scale | Dropping a bug report into "not serious / kind of serious / very serious" baskets |
| `Noul` | Answers a yes/no question as a probability (0–1) | Pushing a needle somewhere between "No" and "Yes" on a dial |

## Use cases covered so far

| # | Notebook | Use case | Primitives used |
|---|---|---|---|
| 1 | [`notebooks/01_choice_ticket_classification.ipynb`](notebooks/01_choice_ticket_classification.ipynb) | Sort a customer support ticket into billing / technical / other | `Choice` |
| 2 | [`notebooks/02_score_bug_severity.ipynb`](notebooks/02_score_bug_severity.ipynb) | Rate how severe a bug report is | `Score` |
| 3 | [`notebooks/03_noul_human_escalation.ipynb`](notebooks/03_noul_human_escalation.ipynb) | Detect whether a customer is asking for a human agent | `Noul` |
| 4 | [`notebooks/04_llm_guardrails.ipynb`](notebooks/04_llm_guardrails.ipynb) | Screen a chatbot message for jailbreaks / harmful requests before it's answered | `Noul` + `Score` |
| 5 | [`notebooks/05_rag_search_reranking.ipynb`](notebooks/05_rag_search_reranking.ipynb) | Re-rank a shortlist of search results by true relevance (RAG retrieval) | `Noul` |
| 6 | [`notebooks/06_ecommerce_listing_check.ipynb`](notebooks/06_ecommerce_listing_check.ipynb) | Categorize a marketplace listing and flag counterfeit red flags | `Choice` + `Noul` |

Go through them in order (1 → 6) — each one builds on ideas explained in the previous notebook, so later notebooks assume you already understand `state`, `questions`, and how to read a response.

## How to run a notebook

1. **Get a TypeSafe API key** from the [TypeSafe playground/console](https://console.typesafe.ai/playground).
2. **Open a notebook** in Jupyter, VS Code, or any notebook editor that supports `.ipynb` files.
3. **Pick the Python 3 kernel** (sometimes shown as "Python 3 (ipykernel)") when prompted — there's only one on a fresh setup, so if you're asked to choose, that's the one.
4. **Run every cell from top to bottom** (click a cell, press `Shift+Enter`):
   - The first cell (`%pip install typesafe-sdk`) installs the SDK — only needs to succeed once per environment, safe to re-run.
   - The second cell is where you paste your API key — replace `PASTE_YOUR_API_KEY_HERE` with your real key, keeping the quote marks around it.
   - Every notebook has one or more "✏️ Try it yourself" cells — edit the example text and re-run that cell to see the answer change.
5. **Read the markdown explanations** between code cells — each one explains the plain-English idea (with an analogy) before the code that implements it.

⚠️ Treat your API key like a password. Don't commit a notebook to git after running it without first replacing the real key back with the `PASTE_YOUR_API_KEY_HERE` placeholder — a pasted key stays saved in the notebook's cell output/source even after you close it.
