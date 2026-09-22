# Frontend Global

Esta pasta contém os componentes visuais reutilizáveis da Dream Arte Studio.

## Objetivo

Centralizar elementos que aparecem em várias páginas da plataforma, evitando duplicação de código e mantendo o visual consistente.

## Componentes

A estrutura global poderá conter:

- Header
- Footer
- Botões
- Variáveis visuais
- Tipografia
- Containers
- Responsividade
- Animações
- Elementos reutilizáveis

## Elementor Free

O frontend deve ser compatível com Elementor Free.

Os componentes visuais poderão ser inseridos em widgets HTML separados quando necessário.

Não depender de recursos exclusivos do Elementor Pro.

## Organização

Cada componente deve ser desenvolvido de forma independente sempre que possível.

Exemplo:

```text
frontend/
└── global/
    ├── header/
    ├── footer/
    ├── buttons/
    ├── styles/
    └── animations/
