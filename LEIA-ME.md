# INTEGRALL 4 — catálogos PDF cadastrados na loja

Branch/commit atual traz o resultado da extração dos 5 catálogos em PDF para o
catálogo da loja (INTEGRALL Online v11.0.4).

| arquivo | o que é |
|---|---|
| `INTEGRALL-v11.0.4-com-catalogo.zip` | projeto completo, com os 227 produtos e as 220 fotos aplicadas (`data/catalog.json` + `public/assets/products/pdf/`) |
| `CATALOGO-para-importar-no-admin.json` | só o catálogo — para Admin → Importar catálogo, sem trocar o resto do código. **A importação substitui o catálogo atual** (o arquivo já vem com os 5 produtos que existiam mesclados) |
| `PRECOS-A-PREENCHER.csv` | uma linha por variante, coluna de preço em branco (os PDFs não trazem preço) |
| `RELATORIO-CADASTRO.md` | o que foi cadastrado, o que falta e o que revisar |
| `AUDITORIA-CATALOGO.md` | auditoria de completude: nenhum código do PDF ficou sem produto |
| `*.pdf` | os 5 catálogos fonte (usados na extração) |
| `INTEGRALL-v11.0.4-corrigido-auditado.zip` | projeto **antes** da importação (original) |

## Como usar

```bash
unzip INTEGRALL-v11.0.4-com-catalogo.zip -d integrall
cd integrall && npm install && npm run check && npm test && node server.js
```

Antes de publicar: preencha o preço (planilha) e marque a disponibilidade por
produto — os novos entraram com `preço = 0` e `disponível = não` de propósito,
para nada ir ao ar sem preço.
