# NLP Sport News Analysis 📰⚽

## Opis projekta
Ovaj projekt se fokusira se na analizu sportskih vijesti na hr web portalima.
Izvor vijesti: sportnet.hr, večernji.hr/sport, jutarnji.hr/sportske, narod.hr/sport
Tjedan dana je prikupljano 102 sportske vijesti.
ChatGPT sintetizirani dataset od 1000 vijesti, s istim omjerom vijesti po kategorijama, kao stvarni dataset 102.

Cilj projekta je:
- prikupljanje i obrada vijesti na hr jeziku
- ekstrakcija i mapiranje entiteta (NER)
- analizu sentimenta
- tematsko modeliranje (Zero-shot)
- metrika, evaluacija, predikciju
- vizualizacija rezultata

---

## Instalacija

1. Kloniraj repozitorij:
```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

2. (Preporučeno) Kreiraj virtualno okruženje:
```bash
python -m venv venv
source venv/bin/activate  # Linux / Mac
venv\Scripts\activate     # Windows
```

3. Instaliraj potrebne pakete:
```bash
pip install -r requirements.txt
```

---

## Pokretanje projekta

Pokreni Jupyter Notebook:
```bash
jupyter notebook
```

Zatim otvori datoteku:
```
sportnews_FINALNO.ipynb
```

---

## Struktura projekta

```
.
├── sportnews_FINALNO.ipynb   # Glavni notebook s analizom
├── README.md                # Dokumentacija projekta
├── requirements.txt         # Popis potrebnih paketa
└── data/                    # (ako postoji) podaci za analizu
```

---

## Primjeri outputa

### Vizualizacija podataka
- Grafovi distribucije
- Trendovi kroz vrijeme
- Najčešće riječi u člancima

### Analiza teksta
- Tokenizacija
- Frekvencija riječi
- NLP obrada


---

## Tehnologije

- Python
- Jupyter Notebook
- Pandas
- Matplotlib / Seaborn
- NLP biblioteke

---

## Zaključak

U ovom projektu provedena je analiza skupa sportskih vijesti koja uključuje obradu teksta, vizualizaciju podataka i izgradnju modela za klasifikaciju sportskih kategorija.
Nakon početne analize distribucije podataka po kategorijama, provedena je obrada teksta korištenjem biblioteke spaCy, uključujući uklanjanje stop riječi i lematizaciju. Tako pripremljeni podaci korišteni su za daljnju analizu, uključujući izdvajanje imenovanih entiteta (NER), čime su identificirane ključne osobe, organizacije i pojmovi u tekstovima.
Vizualizacije, poput distribucije kategorija i wordcloud prikaza, omogućile su bolji uvid u najčešće pojmove i strukturu podataka.

Za zadatak klasifikacije korišten je TF-IDF pristup za vektorizaciju teksta te model logističke regresije. Model je postigao vrlo visoku točnost od približno 99%, uz gotovo savršene rezultate za većinu sportskih kategorija. Najbolje performanse postignute su kod sportova s jasno prepoznatljivim pojmovima (npr. Formula 1, košarka, tenis), dok je slabija izvedba zabilježena kod kategorije tekvondo, što ukazuje na manjak karakterističnih značajki u podacima.

Model u velikoj mjeri prepoznaje obrasce u tekstu, ali i potencijalnu prisutnost “data leakage”-a, gdje specifične riječi direktno otkrivaju kategoriju. Unatoč tome, projekt jasno demonstrira učinkovitost osnovnih NLP tehnika i modela strojnog učenja u klasifikaciji tekstualnih podataka.

Ograničenja
Unatoč vrlo dobrim rezultatima modela, projekt ima nekoliko važnih ograničenja koja treba uzeti u obzir.
Prvo, postignuta visoka točnost (≈99%) može ukazivati na prisutnost data leakage-a, odnosno situacije u kojoj model uči direktne pokazatelje kategorije (npr. specifične riječi poput naziva sporta). To znači da model možda ne generalizira dobro na nove, nepoznate podatke gdje takvi izrazi nisu eksplicitno prisutni.
Drugo, neuravnoteženost ili ograničenost skupa podataka može utjecati na performanse modela. Kategorije s manje primjera (poput tekvondoa) pokazale su slabije rezultate, što sugerira da model nema dovoljno informacija za pouzdanu klasifikaciju u tim slučajevima.

## Autor

Ana Pajalić
