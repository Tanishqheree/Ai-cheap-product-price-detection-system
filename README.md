# 🛒 AI Smart Price Finder

A real-time AI-powered price comparison tool that scans Google Shopping and Amazon for the cheapest deals on any product, then uses **Google Gemini** to generate a smart buying recommendation — all running live from **Google Colab** with a polished dark-themed **Streamlit** UI, tunneled publicly via **ngrok**.

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Streamlit](https://img.shields.io/badge/Streamlit-App-FF4B4B)
![License](https://img.shields.io/badge/License-MIT-green)
![Platform](https://img.shields.io/badge/Runs%20on-Google%20Colab-orange)

---

## ✨ Features

- 🔴 **Real-time prices** — live data pulled from Google Shopping and Amazon via SerpAPI (no cached/stale results)
- 🤖 **AI recommendations** — Gemini 2.5 Flash analyzes the top deals and gives a direct, 3–4 sentence buying verdict (best value, red flags, a practical tip)
- 📊 **Interactive price chart** — Plotly bar chart comparing prices across stores
- 🌍 **Multi-country support** — India, USA, UK, Germany, Australia, Canada, Singapore
- 🥇 **Auto-ranked deal cards** — cheapest option highlighted, with ratings, reviews, delivery info, and direct product links
- ⬇️ **CSV export** — download the full comparison table
- 🕘 **Search history + quick-search shortcuts** in the sidebar
- 🎨 Custom dark violet/indigo theme, fully responsive Streamlit layout

---

## 🧰 Tech Stack

| Layer            | Tool |
|------------------|------|
| UI               | Streamlit (custom CSS theme) |
| Search data      | SerpAPI (Google Shopping + Amazon engines) |
| AI analysis      | Google Gemini (`google-genai`, model `gemini-2.5-flash`) |
| Charts           | Plotly |
| Public tunnel    | pyngrok |
| Data handling    | pandas |
| Runtime          | Google Colab (CPU-only, no GPU required) |

---

## 🚀 Getting Started (Google Colab)

1. **Open the notebook in Colab**
   Click below (after pushing to GitHub, replace `<username>` and `<repo>`):
   `https://colab.research.google.com/github/<username>/<repo>/blob/main/AI_Smart_Price_Finder.ipynb`

2. **Get your free API keys**
   | Key | Where to get it | Free tier |
   |---|---|---|
   | `SERPAPI_KEY` | [serpapi.com](https://serpapi.com) | 100 searches/month |
   | `GEMINI_KEY` | [aistudio.google.com](https://aistudio.google.com) | Yes, generous free tier |
   | `NGROK_TOKEN` | [dashboard.ngrok.com](https://dashboard.ngrok.com) | Yes |

3. **Run the cells in order:**
   - **Cell 1** — installs all dependencies
   - **Cell 2** — paste your three API keys here
   - **Cell 3** — writes the Streamlit app to `/content/price_finder_app.py`
   - **Cell 4** — launches Streamlit and opens a public ngrok URL

4. Click the printed **Public Tunnel URL** to open the live app.

---

## 💻 Running Locally (optional)

```bash
git clone https://github.com/<username>/<repo>.git
cd <repo>
pip install -r requirements.txt
cp .env.example .env   # then fill in your real keys
```

Set the three environment variables from `.env`, save the app code from the notebook's Cell 3 as `price_finder_app.py`, then run:

```bash
streamlit run price_finder_app.py
```

---

## 📁 Project Structure

```
.
├── AI_Smart_Price_Finder.ipynb   # Main Colab notebook (run this)
├── requirements.txt              # Python dependencies
├── .env.example                  # Template for API keys
├── .gitignore
├── LICENSE
└── README.md
```

---

## ⚠️ Notes

- API keys are never committed — `.env` and the generated `price_finder_app.py` are excluded via `.gitignore`.
- SerpAPI's free tier is limited to 100 searches/month; monitor usage on their dashboard.
- This project is for educational/portfolio purposes; respect the terms of service of Google Shopping and Amazon when scraping/querying data.

---

## 📜 License

Released under the [MIT License](LICENSE).
