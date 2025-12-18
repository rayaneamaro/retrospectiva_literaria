# Retrospectiva Literária

Aplicação single-page em HTML/CSS/JS que transforma um CSV de leituras em um painel com métricas, destaques e exportação em PNG.

## Página online
- https://rayaneamaro.github.io/retrospectiva_literaria/
- Publicação direta do `main` no GitHub Pages para testar upload de CSV, visualizar métricas e exportar o PNG.

## Como usar
1. Abra `index.html` em um navegador moderno (sem dependências externas).
2. Escolha o ano (afeta título e PNG exportado).
3. Clique em "Carregar CSV" e selecione o arquivo.
4. Navegue pelas abas: Visão Geral (métricas + gráficos + destaques), Favoritos, Abandonados e Todos os Livros.
# Retrospectiva Literária

Aplicação single-page em HTML/CSS/JS que transforma um CSV de leituras em um painel com métricas, destaques e exportação em PNG.

## Página online
- https://rayaneamaro.github.io/retrospectiva_literaria/
- Publicação direta do `main` no GitHub Pages; basta abrir, subir seu CSV e exportar o PNG.

## Como usar
1. Abra `index.html` em um navegador moderno (sem dependências externas).
2. Escolha o ano (afeta o título da página e o PNG exportado).
3. Clique em “Carregar CSV” e selecione seu arquivo.
4. Explore as abas: Visão Geral (métricas + gráficos + destaques), Favoritos, Abandonados e Todos os Livros.
5. Clique em “📸 Exportar Story (PNG)” para baixar a imagem com a assinatura no rodapé.

## Formato do CSV
- Detecta separador `,` ou `;`, lida com BOM/CRLF e aspas/aspas escapadas.
- Cabeçalhos aceitos (variações comuns):
  - Título: `titulo`, `title`, `livro`
  - Autor: `autor`, `autora`, `author`
  - Editora: `editora`, `publisher`
  - Páginas: `paginas`, `pages`, `pag`
  - Nota: `nota`, `rating`, `avaliacao`, `estrelas`
  - Favorito: `favorito`, `favorite`, `fav`
  - Status: `status`, `estado`
- Notas: números (0–5, passo 0.5), estrelas (`⭐`, `★`, `🌟`) e meia (`½`, `☆`, `🧦`).
- “Abandonado”/`dnf` detectado via nota ou status não conta em média nem em total lido.
- “Favorito” reconhece `favorito`, `fav`, `sim`, `yes`, `true`, `1`, `x`.

### Exemplo
```
titulo,autor,editora,paginas,nota,favorito,status
Dom Casmurro,Machado de Assis,Riachuelo,256,5,sim,
Livro X,Autora Y,Editora Z,310,⭐⭐⭐,nao,
Livro Z,Autor W,Editora K,200,,x,abandonado
```

## O que o painel mostra
- Cards: livros lidos, páginas lidas, média, nota máxima, nota mínima, editora mais lida, autor(a) favorito(a), favoritos, abandonados.
- Gráficos de barras nativos: distribuição de notas, autores favoritos, top editoras.
- Destaques: top 6 melhores notas.
- Abas separadas: Favoritos, Abandonados, Todos os Livros.
- Exportação PNG: gradiente escuro, cartões em glassmorphism e assinatura no rodapé (ajuste em `exportStory()` em `index.html`).

## Observações
- O seletor de ano só altera título/PNG; para filtrar dados por ano, ajuste `calculateStats` para ler um campo de ano no CSV.
- Sem dependências externas; tudo roda em arquivo local.

## Licença
Consulte [LICENSE](LICENSE).

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

