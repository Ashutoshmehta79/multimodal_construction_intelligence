# Multimodal Construction Intelligence Platform
**Skill Wallet Capstone Project 1**

A Streamlit application with four modules:
1. Site Safety & PPE Audit (Gemini multimodal image analysis, structured JSON report)
2. Crack Diagnostics & Structural Integrity (preliminary visual defect triage)
3. Planning & Real Estate Valuation (editable thumb-rule estimates and Pollinations prompt link)
4. Daily Site Assistant & Weather-Aware Advisory (weather alerts and multi-turn assistant)

## Run locally
```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
streamlit run app.py
```

## Enable Gemini
- Create an API key in Google AI Studio.
- Paste it into the password-protected sidebar field, or set `GEMINI_API_KEY` in your environment.
- Without a key, or if the SDK is unavailable, the app runs in demonstration mode.
- Do not commit API keys to source control. For Streamlit Community Cloud, use **App settings → Secrets** and add:
  ```toml
  GEMINI_API_KEY = "your-key-here"
  ```
  Note: the app checks the environment variable; if deploying with Streamlit secrets, you can expose it as an environment value or change the key lookup to `st.secrets.get("GEMINI_API_KEY", "")`.

## Streamlit Community Cloud deployment
1. Push `app.py` and `requirements.txt` to a GitHub repository.
2. Create a new app in Streamlit Community Cloud and select `app.py`.
3. Add the Gemini key in app secrets (never hard-code it).
4. Deploy. No external database is required.

## Important limitations
- This is a capstone prototype, not a certified safety or engineering system.
- Demo mode does not analyze the uploaded image; the output is labelled as demonstration data.
- A photograph cannot reliably establish steel-toe footwear, harness anchorage, crack width, or structural capacity.
- OSHA and IS 456 address different areas; IS 456 is primarily a plain/reinforced concrete design code, not a PPE regulation.
- Planning rates, steel/cement factors, and valuation multipliers are illustrative assumptions. Replace them with current local rates, drawings, a BOQ, and a qualified valuation.
- Pollinations rendering opens an external URL. Availability and terms are controlled by the provider.
