# Logger Finder Fins

Calculadora interativa de quilhas da Logger Surf School. O wizard de quatro
etapas recomenda a quilha ideal com base no perfil do surfista, da prancha e das
ondas, usando um catálogo de produtos reais.

## Estrutura

- `index.html` — a calculadora completa (sem dependências externas de JS)
- `assets/logger-surf-school.jpg` — identidade visual da Logger Surf School

## Como funciona

1. **Etapa 1 — Surfista:** nível, sexo, peso e objetivo principal
2. **Etapa 2 — Prancha:** categoria, configuração, tamanho, peso, rabeta e encaixe
3. **Etapa 3 — Onda:** tamanho e tipo de onda
4. **Etapa 4 — Resultado:** produto recomendado + até 3 alternativas

O motor aplica filtro rígido (produto precisa atender a todos os filtros
selecionados) e facets ao estilo WooCommerce: opções sem nenhum produto
compatível são ocultadas dinamicamente.

Para ajustar as regras de recomendação, edite o objeto `match` de cada produto
no bloco `PRODUTOS` dentro de `index.html`. Lista vazia = aceita qualquer valor.

## Deploy

Site estático — qualquer host serve. No Vercel: `vercel deploy` na raiz.
