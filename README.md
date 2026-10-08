# 📄 ATS Resume Checker

Upload a resume (PDF, DOCX or TXT) and get an **ATS score (0-100)**, section scores,
strengths, weaknesses, prioritized improvements, missing keywords and rewrite examples.
Optionally paste a job description for targeted keyword matching.

Built with [Streamlit](https://streamlit.io) and Google Gemini Flash.

## Run locally

```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt
```

Get a free API key at https://aistudio.google.com/app/apikey, then either:

- paste it in the app sidebar, **or**
- create `.streamlit/secrets.toml` (do NOT commit it):
  ```toml
  GEMINI_API_KEY = "your-key-here"
  ```
- or set an environment variable: `export GEMINI_API_KEY=your-key-here`

```bash
streamlit run app.py
```

## Deploy on Streamlit Community Cloud

1. Push this repo to GitHub (public or private).
2. Go to https://share.streamlit.io and sign in with GitHub.
3. Click **Create app**, pick the repo, branch `main`, main file `app.py`.
4. Open **Advanced settings → Secrets** and add:
   ```toml
   GEMINI_API_KEY = "your-key-here"
   ```
5. Click **Deploy**.

## Notes

- The default model is `gemini-2.5-flash`; you can change it in the sidebar or by editing `DEFAULT_MODEL` in `app.py`.
- Resumes are sent to the Gemini API for analysis and are not stored by this app.
- The score is an AI estimate, not the output of a real employer ATS.
