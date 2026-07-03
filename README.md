# Quilhas Finder — Ferramenta Mágica (réplica)

Calculadora interativa de quilhas de surf: um wizard de 4 etapas que recomenda a
quilha ideal com base no perfil do surfista, da prancha e das ondas.
Réplica standalone (HTML + CSS + JS puro, arquivo único) da "Ferramenta Mágica"
do site centerfins.com.br, com catálogo de produtos reais.

## Estrutura

- `index.html` — a calculadora completa (sem dependências externas de JS)
- `docs/matriz-decisao-quilhas.html` — versão web da matriz de decisão
- `docs/matriz-decisao-quilhas.md` — documentação editável da matriz
- `docs/quilhas-calculadora-logica.pdf` — documentação da lógica, filtros, regras de matching e mapa de assets
- `docs/quilhas-calculadora-logica.docx` — mesma documentação em Word

## Como funciona

1. **Etapa 1 — Surfista:** tipo/categoria de prancha, nível, sexo, altura e peso
2. **Etapa 2 — Prancha:** objetivo, tamanho, peso, rabeta e tipo de encaixe
3. **Etapa 3 — Onda:** tamanho e tipo de onda
4. **Etapa 4 — Resultado:** produto recomendado + até 3 alternativas

O motor aplica filtro rígido (produto precisa atender a todos os filtros
selecionados) e facets ao estilo WooCommerce: opções sem nenhum produto
compatível são ocultadas dinamicamente.

Para ajustar as regras de recomendação, edite o objeto `match` de cada produto
no bloco `PRODUTOS` dentro de `index.html`. Lista vazia = aceita qualquer valor.

## Matriz de decisão

A documentação consolidada cruza três perfis:

1. **Perfil da prancha:** tipo, modalidade, tamanho, peso, rabeta e encaixe.
2. **Perfil da onda:** tamanho e velocidade/pressão da onda.
3. **Perfil do surfista:** nível, peso e objetivo de surf.

Ordem prática de decisão:

1. Eliminar incompatíveis por encaixe, modalidade e tamanho da prancha.
2. Escolher o comportamento desejado: noseriding, velocidade, troca de borda,
   curva horizontal ou performance vertical.
3. Validar com o tipo/tamanho de onda.
4. Ajustar nível de exigência e tamanho físico da quilha pelo surfista.

Arquivos principais:

- [`docs/matriz-decisao-quilhas.html`](docs/matriz-decisao-quilhas.html)
- [`docs/matriz-decisao-quilhas.md`](docs/matriz-decisao-quilhas.md)

## Deploy

Site estático — qualquer host serve. No Vercel: `vercel deploy` na raiz.
