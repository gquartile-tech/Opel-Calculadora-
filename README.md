# Opel Etiquetas — Calculadora de Preços

Calculadora de preços para etiquetas personalizadas. Baseada em 1.429 orçamentos reais (Jan–Mai 2026), cobrindo 19 tipos de produto.

## Tipos de Produto

| Grupo | Produtos |
|---|---|
| Bordada | AD, AD Premium, DD, Cetim, Tafetá, Superbatida |
| Impressa em Tecido | Nylon Calandrado, Nylon Resinado, Cetim Importado, Cetim Impresso, Sarja, Silicone |
| Tag / Papel | Couchê 300g, Triplex 330g |
| Tecnologia Opel | Opelprint, 3D PU, Opellaser, Transfer DTF, Metal Zamak |

## Stack

- Python 3.11
- Flask 3.0
- Gunicorn (production server)
- HTML/CSS/JS puro (sem dependências frontend)

## Rodando Localmente

```bash
pip install -r requirements.txt
python app.py
# Acesse: http://localhost:5000
```

## Deploy no Render

1. Faça fork/push deste repositório no GitHub
2. No Render → **New Web Service** → conecte o repositório
3. Render detecta automaticamente o `render.yaml` — clique em **Deploy**
4. URL pública gerada automaticamente (ex: `https://opel-calculadora.onrender.com`)

## Arquivos

```
opel-calculadora/
├── app.py              # Flask server
├── index.html          # Calculadora (HTML completo com dados embutidos)
├── requirements.txt    # Dependências Python
├── Procfile            # Comando de start para Render/Heroku
├── render.yaml         # Configuração Render
├── .gitignore
└── README.md
```

## Atualização de Preços

Todo o modelo de preços está embutido diretamente no `index.html` (objeto `const P = {...}`).
Para atualizar com novos orçamentos: substituir os valores no objeto `P` e fazer novo deploy.

---

*Versão 1.0 — Uso interno Opel Etiquetas*
