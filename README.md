# Retrospectiva (CSV) — Notas em ⭐ e 🧦

Aplicação web em HTML, CSS e JavaScript para gerar uma retrospectiva visual das suas leituras a partir de um CSV com notas em estrelas e meia estrela (🧦). Inclui filtros, gráficos (Chart.js) e exportação em imagem (PNG) ideal para Stories.

## CSV esperado

Cabeçalhos:
```
Título,Autor,Editora,Páginas,Notas
```
Opcional:
```
Ano
```

- `Notas` pode ser:
  - Estrelas: `⭐⭐⭐⭐` (4), `⭐⭐⭐` (3), etc.
  - Meia estrela: adicione `🧦` (ex.: `⭐⭐⭐⭐🧦` = 4.5)
  - Números também funcionam (ex.: `4.5`)

Separadores `,` ou `;` são detectados automaticamente. Campos com aspas (e aspas escapadas `""`) são suportados.

## Funcionalidades

- Título central “Retrospectiva”
- Parser de `Notas` em ⭐ e 🧦 para valor numérico 0–5
- Filtros por Ano (se disponível), Autor, Editora e faixa de Notas
- Cards-resumo: total de livros, páginas, média de páginas, média de notas
- Gráficos:
  - Distribuição de notas (0–5, passo de 0.5)
  - Top autores
  - Top editoras
  - Evolução por índice (1..N)
- Exportação da retrospectiva em PNG com html2canvas

## Como usar

1. Coloque `index.html`, `styles.css`, `script.js` e `example.csv` na mesma pasta.
2. Abra `index.html` no navegador.
3. Clique em “Carregar CSV” e selecione seu arquivo.
4. Use filtros para refinar a visão.
5. Clique em “Baixar imagem” para salvar a retrospectiva em PNG.

## Personalização

- Cores em `styles.css` (variáveis no `:root`).
- Gráficos e buckets em `script.js` (Chart.js).
- Campos adicionais: amplie o parser em `script.js`.

```

## Publicação

Quer que eu abra um Pull Request com esses arquivos em `vmr-integrados/ProjetoIntegradoIV`?
- Me informe a branch base (ex.: `main`) e eu crio a PR.
