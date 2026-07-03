# Quilhas Finder — Ferramenta Mágica (réplica)

Calculadora interativa de quilhas de surf: um wizard de 4 etapas que recomenda a
quilha ideal com base no perfil do surfista, da prancha e das ondas.
Réplica standalone (HTML + CSS + JS puro, arquivo único) da "Ferramenta Mágica"
do site centerfins.com.br, com catálogo de produtos reais.

## Estrutura

- `index.html` — a calculadora completa (sem dependências externas de JS)
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

## Deploy

Site estático — qualquer host serve. No Vercel: `vercel deploy` na raiz.
