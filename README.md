# Dream Arte Studio

Plataforma própria da Dream Arte para venda, configuração, pagamento, acompanhamento e entrega de serviços digitais.

---

## Visão geral

A Dream Arte Studio será uma plataforma onde o cliente poderá escolher um serviço, configurar o projeto, visualizar o preço, realizar o pagamento e acompanhar a produção até a entrega.

Fluxo principal:

```text
Home
↓
Serviços
↓
Configuração
↓
Resumo
↓
Carrinho
↓
Checkout
↓
Mercado Pago
↓
Pagamento aprovado
↓
Projeto
↓
Produção
↓
Revisões
↓
Entrega
↓
Download
```

---

# Arquitetura

A plataforma utiliza diferentes tecnologias com responsabilidades separadas.

```text
WordPress
│
├── Elementor Free
│   └── Interface visual
│
├── WooCommerce
│   ├── Carrinho
│   ├── Checkout
│   ├── Pedidos
│   └── Integração comercial
│
├── Mercado Pago
│   ├── Pix
│   └── Cartão
│
└── Dream Arte Studio Core
    ├── Configuradores
    ├── Preços
    ├── Projetos
    ├── Área do cliente
    ├── Favoritos
    ├── Entregas
    ├── Downloads
    ├── Revisões
    ├── Pedidos personalizados
    └── Integrações
```

---

# Princípios importantes

## Segurança

Nenhum dado enviado pelo navegador deve ser considerado confiável.

Preços, opções, permissões, IDs e outras informações importantes devem ser validados no servidor.

## Preços

O frontend pode calcular o preço para melhorar a experiência.

O valor definitivo deve ser recalculado e validado no backend.

## Pagamentos

O Mercado Pago será responsável pelo processamento de Pix e cartão.

O sistema próprio não deve armazenar dados completos de cartão.

## Privacidade

Um cliente nunca poderá acessar dados, projetos ou arquivos pertencentes a outro cliente.

## Arquivos

Arquivos privados de clientes devem possuir controle de acesso no servidor.

Conhecer a URL do arquivo não deve ser suficiente para acessá-lo.

## Modularidade

O Dream Arte Studio Core deve ser desenvolvido de forma modular.

Evitar criar um único arquivo gigante contendo toda a plataforma.

---

# Serviços

A plataforma terá inicialmente os seguintes serviços:

1. Música personalizada
2. Imagem personalizada
3. Post para Instagram/WhatsApp
4. Logo
5. Convite
6. Flyer/Cartão
7. Template
8. Landing Page
9. Site institucional
10. Loja Virtual
11. Pedido personalizado

Os preços e configurações completas estão em:

`docs/02-servicos-e-precos.md`

---

# Principais páginas

```text
/
├── /servicos/
│
├── /servicos/musica-personalizada/
├── /servicos/imagem-personalizada/
├── /servicos/posts/
├── /servicos/logo/
├── /servicos/convite/
├── /servicos/flyer-cartao/
├── /servicos/templates/
├── /servicos/landing-page/
├── /servicos/site/
├── /servicos/loja-virtual/
│
├── /pedido-personalizado/
├── /favoritos/
├── /meu-projeto/
└── /minha-conta/
```

Essas URLs representam a estrutura planejada e podem ser ajustadas durante a implementação se houver necessidade técnica.

---

# Área do cliente

O cliente deverá conseguir acompanhar seus projetos através de uma área própria.

Principais informações:

* Projetos
* Pedidos
* Status
* Arquivos
* Entregas
* Revisões
* Solicitações
* Favoritos
* Dados da conta

A estrutura completa está em:

`docs/04-area-do-cliente.md`

---

# Entregas

Depois que a Dream Arte finalizar um projeto, o administrador poderá adicionar os arquivos e liberar a entrega.

Fluxo:

```text
Produção concluída
↓
Arquivos adicionados
↓
Entrega liberada
↓
Cliente notificado
↓
Cliente acessa o projeto
↓
Cliente baixa os arquivos
```

Regras completas:

`docs/06-entregas-e-downloads.md`

---

# Pagamentos

Métodos previstos:

* Pix
* Cartão

A integração será realizada através do Mercado Pago conectado ao WooCommerce.

A arquitetura de pagamentos está documentada em:

`docs/05-pagamentos.md`

---

# Fluxo do cliente

O fluxo detalhado da experiência está em:

`docs/03-fluxo-do-cliente.md`

Resumo:

```text
1. Descobrir serviço
2. Escolher serviço
3. Configurar
4. Informar detalhes
5. Adicionar ao projeto/carrinho
6. Conferir resumo
7. Checkout
8. Pagamento
9. Acompanhar produção
10. Responder solicitações
11. Revisar quando necessário
12. Receber entrega
13. Baixar arquivos
```

---

# Regras do sistema

As regras fundamentais estão em:

`docs/07-regras-do-sistema.md`

Esse documento deve ser consultado antes de implementar funcionalidades importantes.

---

# Identidade visual

A identidade visual da Dream Arte Studio está documentada em:

`docs/08-identidade-visual.md`

Direção visual:

* Roxo/lilás
* Branco
* Fundos escuros em áreas de destaque
* Visual moderno
* Criativo
* Tecnológico
* Premium
* Animações suaves
* Boa organização
* Mobile-first

A plataforma não deve parecer um WooCommerce genérico.

---

# Documentação

## Arquitetura

`docs/01-arquitetura.md`

Define a arquitetura geral da plataforma.

## Serviços e preços

`docs/02-servicos-e-precos.md`

Define os serviços, pacotes, opções e preços.

## Fluxo do cliente

`docs/03-fluxo-do-cliente.md`

Define a jornada do cliente.

## Área do cliente

`docs/04-area-do-cliente.md`

Define o painel e as funcionalidades disponíveis para clientes.

## Pagamentos

`docs/05-pagamentos.md`

Define a arquitetura de pagamento.

## Entregas e downloads

`docs/06-entregas-e-downloads.md`

Define a entrega, armazenamento, permissões e downloads.

## Regras do sistema

`docs/07-regras-do-sistema.md`

Define segurança, permissões, pedidos, projetos, preços e regras de desenvolvimento.

## Identidade visual

`docs/08-identidade-visual.md`

Define a linguagem visual da plataforma.

---

# Estrutura planejada do repositório

```text
dream-arte-studio/
│
├── README.md
│
├── docs/
│   ├── 01-arquitetura.md
│   ├── 02-servicos-e-precos.md
│   ├── 03-fluxo-do-cliente.md
│   ├── 04-area-do-cliente.md
│   ├── 05-pagamentos.md
│   ├── 06-entregas-e-downloads.md
│   ├── 07-regras-do-sistema.md
│   └── 08-identidade-visual.md
│
├── frontend/
│   ├── home/
│   ├── servicos/
│   ├── carrinho/
│   ├── checkout/
│   └── conta/
│
├── plugin/
│   └── dream-arte-studio-core/
│
└── assets/
    ├── images/
    ├── icons/
    └── fonts/
```

Essa estrutura poderá evoluir conforme o desenvolvimento.

---

# Dream Arte Studio Core

O plugin será o núcleo personalizado da plataforma.

Responsabilidades planejadas:

* Configuradores
* Regras de serviços
* Cálculo de preços
* Validação de preços
* Criação/integração de projetos
* Área do cliente
* Favoritos
* Status
* Revisões
* Solicitações
* Entregas
* Downloads
* Pedidos personalizados
* Integrações necessárias

O plugin não deverá substituir desnecessariamente funcionalidades já fornecidas pelo WordPress, WooCommerce ou Mercado Pago.

---

# Desenvolvimento

O projeto será desenvolvido de forma incremental.

Não tentar construir toda a plataforma de uma vez.

Cada etapa deverá:

1. Ter objetivo definido.
2. Ser implementada.
3. Ser testada.
4. Ser corrigida.
5. Ser documentada quando necessário.
6. Só então avançar para a próxima etapa.

---

# Regra para ferramentas de IA

Antes de modificar o projeto, a ferramenta de IA responsável pelo desenvolvimento deverá:

1. Ler este README.
2. Ler os documentos relevantes em `docs/`.
3. Verificar o código existente.
4. Entender a arquitetura atual.
5. Evitar recriar funcionalidades existentes.
6. Não remover funcionalidades sem motivo.
7. Manter compatibilidade com WordPress, WooCommerce, Elementor Free e Mercado Pago.
8. Priorizar segurança no backend.
9. Testar as alterações.
10. Informar quais arquivos foram modificados.

---

# Estado atual do projeto

Documentação principal:

**Concluída**

Arquitetura:

**Definida**

Serviços:

**Definidos**

Pagamentos:

**Configurados no WordPress**

Frontend:

**Em desenvolvimento**

Dream Arte Studio Core:

**Em desenvolvimento**

---

# Próxima etapa

Depois da documentação, o projeto deverá entrar na fase de implementação.

A ordem recomendada é:

```text
1. Estrutura base do plugin
2. Estrutura dos serviços
3. Primeiro configurador
4. Integração com WooCommerce
5. Carrinho
6. Checkout
7. Mercado Pago
8. Projetos
9. Área do cliente
10. Entregas
11. Revisões
12. Pedidos personalizados
13. Melhorias visuais
14. Testes completos
```

Não avançar para funcionalidades complexas antes de estabelecer uma base funcional e segura.
