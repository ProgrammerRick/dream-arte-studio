# Responsive

Sistema de responsividade global da Dream Arte Studio.

## Objetivo

Garantir que todos os componentes e páginas funcionem corretamente em diferentes tamanhos de tela.

## Dispositivos

O frontend deverá considerar:

- Celular
- Tablet
- Desktop

## Requisitos

Todos os componentes devem ser planejados para telas menores desde o início.

Não criar primeiro uma versão desktop e simplesmente reduzir tudo para celular.

## Celular

No celular:

- navegação deve se adaptar;
- menus podem utilizar botão de menu;
- colunas podem ser empilhadas;
- textos devem permanecer legíveis;
- botões devem possuir área adequada para toque;
- imagens devem se adaptar à largura disponível;
- elementos não podem causar rolagem horizontal.

## Tablet

No tablet:

- utilizar layouts intermediários;
- manter espaçamentos adequados;
- ajustar quantidade de colunas quando necessário;
- preservar hierarquia visual.

## Desktop

No desktop:

- aproveitar o espaço disponível sem exagerar nas larguras;
- utilizar containers com largura máxima;
- manter boa distribuição entre conteúdo e espaços vazios.

## Regras

- Nenhum componente deve causar overflow horizontal.
- Evitar larguras fixas desnecessárias.
- Evitar alturas fixas quando o conteúdo puder variar.
- Testar diferentes tamanhos de tela.
- Não depender exclusivamente de um dispositivo específico.
- Manter consistência visual entre breakpoints.

## Elementor Free

A responsividade deve funcionar dentro do Elementor Free.

Quando código personalizado for utilizado, suas regras responsivas deverão ser isoladas para evitar conflitos com Elementor e outros componentes.

## Testes

Cada componente deverá ser verificado em:

- celular pequeno;
- celular comum;
- tablet;
- notebook;
- desktop.

Problemas de responsividade devem ser corrigidos antes da aprovação da etapa.
