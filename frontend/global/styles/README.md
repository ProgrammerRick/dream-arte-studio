# Styles

Base visual global da Dream Arte Studio.

## Objetivo

Centralizar as regras visuais utilizadas pelos componentes da plataforma, mantendo consistência entre páginas e componentes.

## Elementos

A base visual deverá controlar:

- Cores
- Tipografia
- Espaçamentos
- Bordas
- Raios de borda
- Sombras
- Containers
- Transições
- Breakpoints
- Estados visuais

## Identidade visual

A implementação deve seguir `docs/08-identidade-visual.md`.

As cores e estilos definidos na documentação devem ser tratados como referência central do projeto.

## Tipografia

A plataforma utiliza como referência:

- Plus Jakarta Sans
- Sora

A implementação deverá considerar carregamento adequado das fontes e desempenho.

## Responsividade

O sistema deverá funcionar corretamente em:

- Desktop
- Tablet
- Celular

Os componentes não devem depender de larguras fixas que prejudiquem telas menores.

## CSS

Quando o código real for criado:

- utilizar variáveis CSS quando apropriado;
- evitar estilos globais que possam afetar o WordPress inteiro;
- utilizar classes com nomes organizados;
- evitar `!important` sem necessidade;
- evitar conflitos com Elementor e WooCommerce;
- manter os estilos reutilizáveis.

## Elementor Free

Os estilos devem funcionar dentro da estrutura do Elementor Free e não depender de recursos exclusivos do Elementor Pro.

## Regra

Alterações na base visual devem ser feitas com cuidado, pois podem afetar vários componentes da plataforma.
