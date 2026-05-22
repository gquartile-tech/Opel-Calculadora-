# Opel Etiquetas — Calculadora de Preços

Calculadora de preços para etiquetas personalizadas. Baseada em **5.459 pontos de preço** extraídos de 4.133 orçamentos reais (Jan 2025 – Mai 2026), com preços 2025 ajustados em +6% para equivalência 2026.

## Base de dados

| Fonte | PDFs | Pontos de preço |
|---|---|---|
| Orçamentos 2026 (Jan–Mai) | 578 | 1.429 |
| Orçamentos 2025 (Jan–Dez, +6%) | 3.555 | 4.030 |
| **Total** | **4.133** | **5.459** |

## Tipos de Produto (18)

| Grupo | Produtos |
|---|---|
| Bordada | AD, DD, Cetim, Tafetá, Superbatida |
| Impressa em Tecido | Nylon Calandrado, Nylon Resinado, Cetim Importado, Cetim Impresso, Sarja, Silicone |
| Tag / Papel | Couchê 300g, Triplex 330g |
| Tecnologia Opel | Opelprint, 3D PU, Opellaser, Transfer DTF, Metal Zamak |

## Stack

- Python 3.11 · Flask 3.0 · Gunicorn
- HTML/CSS/JS puro (sem dependências frontend)

## Rodando Localmente

```bash
pip install -r requirements.txt
python app.py
# http://localhost:5000
```

## Deploy no Render

1. Cria repositório GitHub e sobe todos os arquivos na raiz
2. Render → **New Web Service** → conecta o repositório
3. `render.yaml` é detectado automaticamente → **Deploy**

## Arquivos

```
opel-calculadora/
├── app.py              # Flask serve o index.html na rota /
├── index.html          # Calculadora completa (dados + lógica + UI)
├── requirements.txt    # Flask + Gunicorn
├── Procfile            # Comando de start
├── render.yaml         # Config automática Render
├── .gitignore
└── README.md
```

## Atualização de preços

Todo o modelo está no objeto `const P = {...}` dentro do `index.html`.
Para atualizar: substitui o objeto `P`, faz commit → Render redeploy automático.

## Correções aplicadas na v2

- **Curva de 1.500 unidades**: revalidada com base ampliada (5.459 pts). Anomalias onde 1.500 ≥ 1.000 corrigidas por interpolação linear.
- **Guardrails de dimensão**: limites por produto derivados dos orçamentos reais, com chips de tamanhos comuns clicáveis.
- **Tag Couchê 1.500**: corrigido de R$0,56 para R$0,51 (agora entre 1.000 e 2.000).

---

*v2.0 · Mai 2026 · Uso interno Opel Etiquetas*
