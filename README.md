# Jak na podcasty — Web

Statický web pro [jaknapodcasty.cz](https://jaknapodcasty.cz).

## Stack
- Čistý HTML + vlastní CSS (bez build stepu)
- Vanilla JS (animace, mobile menu, scroll efekty)
- GitHub Pages hosting

## Struktura
```
Website/
├── index.html          # Celý web (jedna stránka)
├── style.css           # Všechny styly
├── main.js             # Interakce (menu, animace)
└── .github/
    └── workflows/
        └── deploy.yml  # Auto-deploy na GitHub Pages
```

## Nasazení

1. Vytvoř GitHub repozitář
2. Pushni kód na branch `main`
3. V Settings → Pages → Source nastav **"GitHub Actions"**
4. Web se automaticky nasadí při každém push na `main`

## Google Analytics

V `index.html` nahraď `G-XXXXXXXXXX` svým skutečným Measurement ID z Google Analytics.

## Vlastní doména

V Settings → Pages → Custom domain zadej `jaknapodcasty.cz`.
DNS: přidej CNAME záznam `www → tvujucet.github.io`.
