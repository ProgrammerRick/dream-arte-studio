# Animations

Sistema de animações globais da Dream Arte Studio.

## Objetivo

Definir padrões de animação e interação utilizados pelos componentes da plataforma.

## Tipos de animação

Poderão ser utilizados:

- Entrada suave de elementos
- Fade
- Slide
- Scale
- Hover
- Microinterações
- Transições
- Animações de carregamento
- Animações relacionadas à navegação

## Requisitos

- Animações suaves e discretas.
- Não prejudicar a experiência do usuário.
- Não exagerar na quantidade de efeitos.
- Manter aparência premium e moderna.
- Funcionar em desktop, tablet e celular.
- Respeitar usuários que preferem redução de movimento.

## Performance

As animações devem ser leves e evitar:

- JavaScript desnecessário;
- animações contínuas sem necessidade;
- efeitos que causem travamentos;
- excesso de elementos animados simultaneamente.

Sempre que possível, utilizar propriedades CSS adequadas para animações.

## Elementor Free

As animações devem funcionar com Elementor Free e não depender de recursos exclusivos do Elementor Pro.

## Estrutura futura

O componente poderá conter:

- CSS
- JavaScript, somente quando realmente necessário.

As animações deverão ser reutilizáveis pelos demais componentes.
