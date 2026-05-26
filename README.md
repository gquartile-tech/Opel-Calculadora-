# Opel Etiquetas — Calculadora de Preços

App de precificação com duas abas: etiquetas padrão e UV/3D PU.

## Abas

### Aba 1 — Etiquetas Padrão
Calculadora baseada em orçamentos históricos (5.459 pontos de preço · Jan 2025–Mai 2026).
Produtos: Bordada AD/DD/Cetim/Tafetá/Superbatida, Nylon, Cetim, Sarja, Silicone, Tag Couchê/Triplex, Opelprint, 3D PU, Opellaser, Transfer DTF, Metal Zamak.

### Aba 2 — UV · 3D PU
Calculadora bottom-up de custo real de produção.
Fórmula: `Preço = Custo/peça ÷ (1 − 30% overhead − Lucro%)`

Overhead fixo embutido: Simples Nacional 10% + DDV 3% + Desp Adm Coml 12% + Desp Financ 5% = **30%**

Lucro % selecionável por cliente: 55% (250 un) → 35% (5.000 un), ou manual.

## Arquitetura

```
opel-calculadora/
├── app.py        # Flask serve / e /rules.js
├── index.html    # UI completa (2 abas, toda a lógica)
├── rules.js      # TODOS os preços, multiplicadores, guardrails
├── requirements.txt
├── Procfile
├── render.yaml
├── .gitignore
└── README.md
```

## Atualizar preços (sem redeploy total)

Editar `rules.js` → commit → Render redeploy automático (~30s).
`index.html` e `app.py` não precisam ser alterados.

## Stack

Python 3.11 · Flask 3.0 · Gunicorn · HTML/CSS/JS puro

## Rodar localmente

```bash
pip install -r requirements.txt
python app.py
# http://localhost:5000
```

## Deploy no Render

1. Push todos os arquivos na raiz do repositório GitHub
2. Render → New Web Service → conecta o repo → Deploy
3. `render.yaml` é detectado automaticamente

---
*v2.2 · Mai 2026 · Uso interno Opel Etiquetas*
