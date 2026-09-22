# Dream Arte Studio — Arquitetura do Projeto

## 1. Visão geral

A Dream Arte Studio será uma plataforma própria para venda e gerenciamento de serviços digitais.

O objetivo é permitir que o cliente:

1. Entre no site.
2. Escolha um serviço.
3. Configure o serviço conforme suas necessidades.
4. Veja o preço atualizado automaticamente.
5. Adicione o serviço ao projeto/carrinho.
6. Finalize o pedido.
7. Pague por Pix ou cartão.
8. Acompanhe o andamento do pedido.
9. Receba os arquivos finais pela própria plataforma.

A plataforma também terá uma área administrativa para a Dream Arte gerenciar pedidos, projetos, clientes, pagamentos, arquivos, revisões e solicitações.

---

## 2. Tecnologias principais

### WordPress

Responsável pela estrutura principal do site, usuários, páginas, banco de dados e administração.

### WooCommerce

Responsável pela infraestrutura de pedidos, carrinho, checkout e integração com pagamentos.

### Mercado Pago

Responsável pelo processamento dos pagamentos.

Métodos planejados:

* Pix
* Cartão de crédito

Os dados do cartão não serão armazenados nem processados pelo código próprio da Dream Arte.

### Elementor Free

Responsável pela construção visual das páginas.

O projeto deve funcionar com Elementor Free, utilizando HTML, CSS e JavaScript personalizados quando necessário.

### Dream Arte Studio Core

Plugin próprio da Dream Arte Studio.

Esse plugin será o núcleo personalizado da plataforma.

Responsabilidades previstas:

* Configuradores de serviços
* Opções dos serviços
* Cálculo de preços
* Validação dos preços no servidor
* Campos personalizados dos pedidos
* Integração com WooCommerce
* Criação e gerenciamento de projetos
* Status dos projetos
* Área do cliente
* Favoritos
* Entrega de arquivos
* Controle de downloads
* Revisões
* Solicitação de informações ao cliente
* Pedidos personalizados
* Orçamentos
* Notificações
* Integrações necessárias entre o frontend e WooCommerce

---

## 3. Princípio importante de segurança

O preço mostrado no navegador através de JavaScript é apenas uma interface para o cliente.

O servidor deverá recalcular e validar o preço antes de criar ou finalizar o pedido.

Nunca confiar somente no preço enviado pelo navegador.

As opções escolhidas pelo cliente também deverão ser validadas no servidor.

---

## 4. Fluxo principal do cliente

### Página inicial

O cliente conhece a Dream Arte Studio e seus serviços.

↓

### Serviços

O cliente visualiza os serviços disponíveis.

↓

### Página individual do serviço

Cada serviço terá sua própria página e configurador.

↓

### Configurador

O cliente escolhe:

* Pacote
* Tipo
* Estilo
* Formato
* Quantidade
* Opções adicionais
* Informações necessárias para produção
* Arquivos ou referências, quando necessário

As opções variam conforme o serviço.

↓

### Resumo

O cliente visualiza:

* Serviço escolhido
* Opções
* Adicionais
* Valor final
* Prazo estimado
* Informações importantes

↓

### Meu Projeto / Carrinho

O cliente pode continuar comprando outros serviços ou finalizar o pedido.

↓

### Checkout

O cliente informa os dados necessários.

O sistema deverá permitir:

* Nome
* E-mail
* WhatsApp
* CPF, quando necessário para pagamento
* Outros dados necessários ao pedido

O cadastro não deverá ser obrigatório antes da compra.

↓

### Pagamento

O cliente paga através do Mercado Pago:

* Pix
* Cartão de crédito

↓

### Pedido aprovado

O WooCommerce registra o pedido.

O Dream Arte Studio Core identifica o pedido e cria ou associa o projeto correspondente.

↓

### Produção

A Dream Arte começa a trabalhar no projeto.

↓

### Aguardando cliente

Quando for necessário receber uma informação, aprovação ou arquivo do cliente, o projeto poderá ficar aguardando resposta.

↓

### Revisão

O cliente poderá solicitar as revisões incluídas no serviço.

↓

### Entrega

Os arquivos finais ficam disponíveis para o cliente na área do cliente.

↓

### Projeto concluído

O projeto passa para o estado de concluído/entregue.

---

## 5. Pedido x Projeto

Esses dois conceitos devem ser tratados separadamente.

### Pedido

Representa a transação comercial.

É controlado principalmente pelo WooCommerce.

Um pedido pode conter vários serviços.

### Projeto

Representa o trabalho que precisa ser produzido.

É controlado pelo Dream Arte Studio Core.

Exemplo:

Um cliente compra:

* 1 Logo
* 5 Posts
* 1 Landing Page

Isso pode gerar:

**1 pedido**

contendo

**3 projetos**

Cada projeto poderá ter seu próprio:

* Status
* Configuração
* Prazo
* Arquivos
* Revisões
* Comunicação
* Entrega

---

## 6. Status dos projetos

Os status planejados são:

### Aguardando pagamento

O pedido ainda não foi pago.

### Pagamento aprovado

O pagamento foi confirmado.

### Em produção

A Dream Arte está trabalhando no projeto.

### Aguardando cliente

É necessária alguma informação, arquivo, aprovação ou resposta do cliente.

### Em revisão

O projeto está passando por alterações solicitadas pelo cliente.

### Entregue

Os arquivos finais foram disponibilizados.

### Concluído

O projeto foi finalizado.

### Cancelado

O projeto foi cancelado.

---

## 7. Área do cliente

O cliente deverá possuir uma área própria.

Possíveis seções:

* Visão geral
* Meus projetos
* Pedidos
* Projetos em produção
* Aguardando minha resposta
* Entregues
* Downloads
* Revisões
* Dados pessoais
* Favoritos

O cliente deverá conseguir visualizar claramente o estado de cada projeto.

---

## 8. Entrega de arquivos

Os arquivos finais deverão ser protegidos.

Um cliente não poderá acessar arquivos pertencentes a outro cliente apenas conhecendo uma URL.

O sistema deverá verificar:

1. Se o usuário está autenticado.
2. Se o usuário é proprietário do projeto/pedido.
3. Se o arquivo pertence àquele projeto.
4. Se o download é permitido.

Os arquivos deverão ser disponibilizados somente para o cliente autorizado.

---

## 9. Favoritos

A plataforma deverá possuir uma área de favoritos.

O cliente poderá salvar serviços que deseja contratar posteriormente.

Exemplo:

* Landing Page
* Logo
* Loja Virtual

Os favoritos não representam um pedido nem um pagamento.

---

## 10. Pedido personalizado

Além dos serviços com preço definido, haverá uma opção:

**Pedido personalizado**

O cliente poderá informar:

* O que precisa
* Descrição do projeto
* Categoria
* Prazo desejado
* Arquivos
* Referências

Categorias:

* Design
* Música
* Vídeo
* Website
* Redes sociais
* Material gráfico
* IA
* Outro

Nesse caso, o sistema inicialmente deverá funcionar através de solicitação de orçamento.

Depois que a Dream Arte definir o valor, poderá ser criado um pedido para pagamento.

---

## 11. Notificações

O sistema deverá prever notificações para eventos importantes.

Exemplos:

* Pedido recebido
* Pagamento aprovado
* Projeto iniciado
* Informação necessária
* Projeto em revisão
* Projeto entregue
* Novo arquivo disponível
* Pedido personalizado recebido

E-mail poderá ser utilizado para notificações automáticas.

O WhatsApp poderá ser utilizado como canal de comunicação e aviso, mas o site deverá continuar sendo a fonte principal das informações do projeto.

---

## 12. Painel administrativo

A Dream Arte deverá possuir uma área administrativa para visualizar:

* Vendas
* Novos pedidos
* Pagamentos
* Projetos em produção
* Projetos aguardando cliente
* Projetos em revisão
* Projetos entregues
* Clientes
* Arquivos
* Revisões
* Pedidos personalizados

Ao abrir um pedido, o administrador deverá conseguir visualizar as informações necessárias para executar o trabalho.

---

## 13. Estrutura planejada de páginas

Página inicial:

`/`

Serviços:

`/servicos/`

Música personalizada:

`/servicos/musica-personalizada/`

Imagem personalizada:

`/servicos/imagem-personalizada/`

Posts:

`/servicos/posts/`

Logo:

`/servicos/logo/`

Convite:

`/servicos/convite/`

Flyer e cartão:

`/servicos/flyer-cartao/`

Templates:

`/servicos/templates/`

Landing Page:

`/servicos/landing-page/`

Site institucional:

`/servicos/site/`

Loja Virtual:

`/servicos/loja-virtual/`

Pedido personalizado:

`/pedido-personalizado/`

Favoritos:

`/favoritos/`

Meu Projeto:

`/meu-projeto/`

Minha Conta:

`/minha-conta/`

---

## 14. Estrutura do projeto no GitHub

A estrutura planejada é:

```text
dream-arte-studio/
├── README.md
├── docs/
│   ├── 01-arquitetura.md
│   ├── 02-servicos-e-precos.md
│   ├── 03-fluxo-do-cliente.md
│   ├── 04-area-do-cliente.md
│   ├── 05-pagamentos.md
│   ├── 06-entregas-e-downloads.md
│   ├── 07-regras-do-sistema.md
│   └── 08-identidade-visual.md
├── frontend/
│   ├── home/
│   ├── servicos/
│   ├── carrinho/
│   ├── checkout/
│   └── conta/
├── plugin/
│   └── dream-arte-studio-core/
└── assets/
    ├── images/
    ├── icons/
    └── fonts/
```

---

## 15. Princípio visual

A plataforma não deverá parecer uma loja WooCommerce genérica.

O WooCommerce ficará responsável pela infraestrutura comercial, enquanto a interface visual será personalizada.

Objetivos visuais:

* Premium
* Moderna
* Profissional
* Organizada
* Viva
* Boa hierarquia visual
* Animações suaves
* Responsiva
* Excelente experiência no celular
* Identidade visual Dream Arte
* Navegação simples

O design deverá priorizar clareza e facilidade de compra.

---

## 16. Regra para desenvolvimento

Antes de criar uma nova funcionalidade, verificar:

1. Se ela já existe.
2. Em qual parte da arquitetura ela pertence.
3. Se deve ficar no frontend, no plugin ou no WooCommerce.
4. Se precisa de validação no servidor.
5. Se afeta pedidos existentes.
6. Se afeta segurança.
7. Se funciona no celular.

Evitar criar soluções duplicadas ou colocar toda a lógica em uma única página HTML.

O projeto deverá ser modular e organizado para facilitar manutenção e futuras alterações.

---

## 17. Estado atual

O projeto está em fase de construção.

Já definidos:

* WordPress
* Elementor Free
* WooCommerce
* Mercado Pago
* Pix
* Cartão
* Plugin próprio Dream Arte Studio Core
* Estrutura geral da plataforma
* Fluxo do cliente
* Área do cliente
* Conceito de pedido e projeto
* Serviços principais
* Modelo de configuradores

Ainda precisam ser desenvolvidos:

* Configuradores
* Produtos/base do WooCommerce
* Integração completa com o plugin
* Carrinho personalizado
* Área do cliente
* Sistema de projetos
* Entrega de arquivos
* Revisões
* Pedidos personalizados
* Notificações
* Painel administrativo personalizado
* Testes completos de pagamento e fluxo
* Interface final

Este documento é uma referência arquitetural do projeto e deve ser atualizado quando decisões estruturais importantes forem alteradas.
