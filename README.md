# Sentiment analiza objava Donalda J. Trumpa i povezanost s volatilnošću tržišta

Ovaj projekt integrira heterogene izvore podataka o objavama Donalda J. Trumpa (Twitter/X i Truth Social) i tržišnim indikatorima volatilnosti (VIX, SPY) te provodi deskriptivnu analitiku: **sentiment analiza (VADER)**, **korelacije s vremenskim pomakom (lag)**, **jednostavan regresijski model s kontrolom autokorelacije**, **event-study za ekstremno negativne dane**, **K-means klasteriranje** i demonstraciju pristupa podacima kroz **REST API (FastAPI)**.

Projekt je implementiran kao reproducibilna **Jupyter bilježnica**: `finalni_pzap.ipynb`.

---

## Sadržaj (što se radi u bilježnici)

1. Učitavanje i čišćenje podataka iz CSV-a (objave)
2. Normalizacija sheme (sjedinjavanje platformi) + tekstualne značajke
3. VADER sentiment po objavi
4. Agregacija po trgovačkom danu (New York) radi usporedbe s tržištem
5. Dohvat tržišnih podataka (VIX, SPY) preko `yfinance` i pohrana u JSON (heterogen format)
6. Integracija skupa objava i tržišta
7. Lag-korelacije (npr. sentiment danas vs. volatilnost sutra / obrnuto)
8. Regresijski model (deskriptivno, uz oprez u interpretaciji)
9. Event-study (ekstremno negativni dani)
10. K-means klasteriranje (režimi komunikacije i volatilnosti)
11. Pohrana integriranog skupa u SQLite
12. REST API (FastAPI) za dohvat dana/objava/klastera
13. Prikaz rada API-ja (demo)

---

## Preduvjeti

- Python 3.x
- Jupyter Notebook / JupyterLab / Google Colab
- Internet pristup (za `yfinance`, ako se tržišni dio radi “svježe”)

---

## Instalacija ovisnosti

Bilježnica na početku koristi:

```bash
pip install pandas numpy matplotlib scikit-learn nltk yfinance fastapi uvicorn nest_asyncio requests statsmodels scipy
