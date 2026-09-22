# Plano de Desenvolvimento — Dream Arte Studio

## Objetivo

Desenvolver a plataforma Dream Arte Studio de forma modular, organizada e segura.

O projeto será desenvolvido por etapas. Cada etapa será dividida em componentes menores para facilitar testes, manutenção e integração com WordPress e Elementor Free.

---

## Regra principal de desenvolvimento

Nenhuma etapa deve tentar construir a plataforma inteira de uma vez.

Cada etapa deve:

1. Ter um objetivo claro.
2. Ser dividida em componentes.
3. Ser testada antes da próxima etapa.
4. Evitar alterações desnecessárias em componentes já aprovados.
5. Manter frontend, backend e integrações separados.
6. Preservar a identidade visual definida em `docs/08-identidade-visual.md`.

---

## Estrutura do desenvolvimento

### Etapa 1 — Base do Frontend

Criar a base visual da plataforma.

Componentes:

- Header
- Navegação
- Identidade da marca
- Base tipográfica
- Variáveis de cores
- Container principal
- Responsividade
- Botões
- Estados de hover
- Base para animações
- Footer

O frontend deve ser compatível com Elementor Free.

Os componentes visuais devem ser independentes para que possam ser inseridos em widgets HTML separados quando necessário.

---

### Etapa 2 — Página Inicial

Construir a Home da Dream Arte Studio.

Componentes:

- Hero
- Apresentação da plataforma
- Serviços
- Diferenciais
- Como funciona
- Projetos/portfólio
- FAQ
- CTA
- Footer

---

### Etapa 3 — Página de Serviços

Criar a página que apresenta todos os serviços disponíveis.

Serviços:

1. Música personalizada
2. Imagem personalizada
3. Post para Instagram/WhatsApp
4. Logo
5. Convite
6. Flyer/Cartão
7. Template
8. Landing Page
9. Site
10. Loja Virtual
11. Pedido personalizado

---

### Etapa 4 — Páginas Individuais dos Serviços

Cada serviço terá sua própria página.

Estrutura geral:

- Apresentação
- Benefícios
- Exemplos
- Pacotes
- Preços
- Prazo
- O que está incluído
- Adicionais
- CTA para configurar o pedido

---

### Etapa 5 — Configuradores

Criar os configuradores específicos de cada serviço.

Cada configurador deverá:

- apresentar as opções;
- permitir seleção;
- calcular o preço em tempo real;
- mostrar resumo do pedido;
- permitir anexos quando necessário;
- validar campos obrigatórios;
- enviar os dados para o sistema.

O preço exibido no navegador nunca será considerado confiável sozinho.

O servidor deverá recalcular e validar o valor antes de criar o pedido.

---

### Etapa 6 — Carrinho / Meu Projeto

Criar a experiência personalizada de carrinho.

Objetivos:

- permitir vários serviços no mesmo pedido;
- mostrar cada projeto separadamente;
- mostrar valores;
- permitir revisar configurações;
- permitir remover itens;
- permitir voltar para editar.

A interface não deve parecer um WooCommerce padrão.

---

### Etapa 7 — Checkout

Integrar o fluxo de checkout com WooCommerce.

Informações:

- Nome
- E-mail
- WhatsApp
- Dados necessários para o pedido

O cliente poderá finalizar sem precisar criar manualmente uma conta antes da compra.

---

### Etapa 8 — Pagamentos

Integrar o checkout com Mercado Pago.

Métodos:

- Pix
- Cartão de crédito

O processamento dos dados do cartão deverá permanecer sob responsabilidade do Mercado Pago.

Nenhum dado sensível do cartão deverá ser armazenado pelo Dream Arte Studio.

---

### Etapa 9 — Dream Arte Studio Core

Desenvolver o plugin próprio da plataforma.

Responsabilidades principais:

- Configuradores
- Opções dos serviços
- Regras de preço
- Validação dos pedidos
- Campos personalizados
- Integração com WooCommerce
- Status dos projetos
- Área administrativa
- Dados dos projetos
- Entregas
- Downloads
- Notificações

---

### Etapa 10 — Área do Cliente

Criar a área onde o cliente poderá:

- visualizar pedidos;
- acompanhar projetos;
- verificar status;
- responder solicitações;
- acessar entregas;
- baixar arquivos;
- consultar histórico.

---

### Etapa 11 — Área Administrativa

Criar o painel interno da Dream Arte Studio.

Informações principais:

- Novos pedidos
- Pagamentos
- Projetos em produção
- Aguardando cliente
- Em revisão
- Entregues
- Cancelados
- Faturamento

---

### Etapa 12 — Entregas e Downloads

Criar sistema de entrega dos arquivos.

Requisitos:

- arquivos protegidos;
- acesso somente ao cliente autorizado;
- controle de propriedade;
- downloads registrados;
- possibilidade de múltiplos arquivos por projeto.

---

### Etapa 13 — Pedido Personalizado

Criar fluxo para trabalhos que não possuem preço automático.

O cliente poderá:

- escolher categoria;
- explicar o que precisa;
- enviar arquivos;
- informar prazo desejado;
- solicitar orçamento.

Nesse caso, o pedido não terá pagamento automático antes da aprovação do orçamento.

---

### Etapa 14 — Favoritos

Criar sistema de favoritos para serviços e conteúdos selecionados pelo cliente.

---

### Etapa 15 — Notificações

Criar notificações relacionadas a:

- novo pedido;
- pagamento aprovado;
- alteração de status;
- solicitação ao cliente;
- projeto entregue.

---

### Etapa 16 — Segurança

Revisar:

- validação no servidor;
- permissões;
- autenticação;
- acesso aos projetos;
- downloads;
- uploads;
- dados do cliente;
- valores dos pedidos;
- integração com WooCommerce;
- proteção contra manipulação de preços.

---

### Etapa 17 — Testes

Testar separadamente:

- desktop;
- tablet;
- celular;
- formulários;
- configuradores;
- cálculos;
- carrinho;
- checkout;
- Pix;
- cartão;
- criação de pedidos;
- notificações;
- área do cliente;
- downloads;
- permissões.

---

## Regras para desenvolvimento com IA

A IA deverá desenvolver o projeto de forma incremental.

Não gerar uma plataforma inteira em um único bloco de código.

Quando uma etapa possuir muitas partes, dividi-la em componentes menores.

### Frontend

O código visual deverá ser organizado para funcionar com Elementor Free.

Sempre que possível:

- HTML separado por componente;
- CSS organizado por componente;
- JavaScript separado por funcionalidade;
- evitar conflitos entre componentes;
- evitar CSS global desnecessário;
- evitar dependências desnecessárias.

### Backend

O backend deverá permanecer separado do frontend.

O plugin Dream Arte Studio Core será responsável pelas regras do sistema.

### Preços

Nunca confiar somente no JavaScript do frontend.

Os valores deverão ser recalculados e validados no servidor.

### Pagamentos

Nunca criar processamento próprio de cartão.

Utilizar a integração oficial do Mercado Pago através do WooCommerce.

### WordPress

O código deverá respeitar boas práticas do WordPress e WooCommerce.

### Elementor Free

Não depender de recursos exclusivos do Elementor Pro.

---

## Ordem de trabalho

A ordem inicial será:

1. Documentação
2. Estrutura do projeto
3. Base visual
4. Home
5. Serviços
6. Páginas individuais
7. Configuradores
8. Carrinho
9. Checkout
10. Pagamentos
11. Plugin Core
12. Área do cliente
13. Área administrativa
14. Entregas
15. Pedido personalizado
16. Favoritos
17. Notificações
18. Segurança
19. Testes
20. Publicação

---

## Regra de aprovação

Uma etapa somente será considerada concluída depois de ser testada e aprovada.

Depois da aprovação, a próxima etapa será iniciada sem alterar desnecessariamente o que já foi aprovado.
