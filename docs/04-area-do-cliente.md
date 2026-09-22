# Dream Arte Studio — Área do Cliente

Este documento define a estrutura e o funcionamento da área exclusiva do cliente.

A área do cliente será integrada ao WordPress/WooCommerce e terá funcionalidades próprias desenvolvidas pelo plugin Dream Arte Studio Core.

---

# 1. Objetivo

A área do cliente será o espaço onde o cliente poderá acompanhar tudo relacionado aos seus pedidos e projetos.

O cliente deverá conseguir:

* Ver seus pedidos
* Ver seus projetos
* Acompanhar o status
* Enviar informações
* Enviar arquivos
* Solicitar revisões
* Baixar arquivos entregues
* Atualizar seus dados
* Ver notificações
* Acessar favoritos

A experiência deve ser simples e visual.

---

# 2. Acesso

Página:

`/minha-conta/`

O cliente poderá:

* Entrar em uma conta existente
* Criar uma conta
* Recuperar senha

Não exigir cadastro antes da compra.

Quando um novo cliente comprar, a plataforma poderá criar sua conta automaticamente usando os dados informados no checkout.

---

# 3. Dashboard

Após fazer login, o cliente verá um painel inicial.

Estrutura sugerida:

```text
Olá, Luiz 👋

Acompanhe seus projetos e pedidos.

┌────────────────────┐
│ Projetos ativos    │
│        2           │
└────────────────────┘

┌────────────────────┐
│ Aguardando você    │
│        1           │
└────────────────────┘

┌────────────────────┐
│ Entregues          │
│        5           │
└────────────────────┘
```

Abaixo poderão aparecer:

* Projetos recentes
* Pedidos recentes
* Avisos importantes
* Atalhos

---

# 4. Menu da área do cliente

O menu poderá conter:

* Visão geral
* Meus projetos
* Meus pedidos
* Aguardando você
* Entregas
* Favoritos
* Notificações
* Meu perfil
* Sair

No celular, o menu deverá ser adaptado para facilitar a navegação.

---

# 5. Meus projetos

Página:

`/minha-conta/projetos/`

Mostrar todos os projetos pertencentes ao cliente.

Cada projeto deverá apresentar:

* Nome do serviço
* Número do projeto
* Status
* Data do pedido
* Prazo
* Progresso
* Ação para abrir o projeto

Exemplo:

```text
Landing Page
Projeto #203

● Em produção

Prazo estimado:
28/09/2026

[Ver projeto]
```

---

# 6. Status visual

Os status deverão ser fáceis de entender.

### Aguardando pagamento

O pagamento ainda não foi confirmado.

### Pagamento aprovado

Pagamento confirmado e pedido recebido.

### Em produção

A Dream Arte está trabalhando no projeto.

### Aguardando você

É necessária uma ação do cliente.

### Em revisão

Alterações/revisões estão sendo processadas.

### Entregue

O projeto foi entregue e os arquivos estão disponíveis.

### Concluído

O projeto foi finalizado.

### Cancelado

O projeto foi cancelado.

---

# 7. Aguardando você

Essa será uma área importante.

Página:

`/minha-conta/aguardando/`

Quando existir alguma pendência do cliente, mostrar claramente.

Exemplo:

```text
⚠ Precisamos de uma informação

Landing Page

Precisamos da imagem principal que será utilizada no projeto.

[Enviar imagem]
```

Outro exemplo:

```text
Sua aprovação é necessária

Logo

Escolha uma das opções apresentadas.

[Ver opções]
```

O cliente deverá entender imediatamente o que precisa fazer.

---

# 8. Página individual do projeto

Ao clicar em um projeto, o cliente verá uma página detalhada.

Exemplo:

```text
Landing Page
Projeto #203

Status
● Em produção

Prazo
28/09/2026

Pedido
#105

Valor
R$ 194,90
```

Abaixo:

* Detalhes do serviço
* Configuração escolhida
* Informações enviadas
* Arquivos enviados
* Revisões
* Solicitações
* Entregas
* Histórico

---

# 9. Informações do projeto

O cliente poderá consultar as informações que enviou durante a compra.

Exemplo:

```text
Serviço:
Landing Page

Pacote:
Profissional

Adicionais:
Copy personalizada
Seção adicional

WhatsApp:
(XX) XXXXX-XXXX
```

Essas informações não deverão ser facilmente alteráveis depois que a produção começar.

Quando uma alteração afetar o trabalho, deverá existir um fluxo apropriado para atualização.

---

# 10. Arquivos enviados pelo cliente

O cliente poderá visualizar os arquivos que enviou.

Exemplo:

```text
Arquivos enviados

logo.png
foto-principal.jpg
referencia.pdf
```

Cada arquivo deverá estar associado ao projeto correto.

---

# 11. Arquivos entregues

Quando a Dream Arte liberar a entrega, o cliente verá:

```text
Sua entrega está pronta! 🎉

Arquivos finais:

Landing-page-final.zip
Imagens.zip
Manual.pdf

[Baixar arquivos]
```

Os arquivos deverão permanecer protegidos.

---

# 12. Proteção dos arquivos

Nenhum cliente poderá acessar arquivos de outro cliente.

Antes de liberar um download, o sistema deverá verificar:

* Usuário autenticado
* Proprietário do projeto
* Arquivo pertence ao projeto
* Arquivo está liberado
* Usuário possui permissão

O plugin Dream Arte Studio Core deverá controlar essa autorização.

---

# 13. Revisões

A página do projeto deverá mostrar as revisões.

Exemplo:

```text
Revisões

Incluídas: 2
Utilizadas: 1
Restantes: 1
```

O cliente poderá solicitar uma revisão quando o projeto estiver em um estado que permita revisão.

---

# 14. Solicitar revisão

O cliente poderá clicar:

**Solicitar revisão**

E preencher:

* O que deseja alterar?
* Descrição
* Arquivo de referência, se necessário

Exemplo:

```text
O que deseja alterar?

"Gostaria de trocar a imagem principal e deixar o título maior."

[Enviar solicitação]
```

A solicitação deverá ficar registrada no projeto.

---

# 15. Limite de revisões

Cada serviço terá uma quantidade de revisões definida no pacote contratado.

O sistema deverá impedir que o cliente utilize gratuitamente mais revisões do que o pacote permite.

Caso exista revisão adicional disponível para compra:

```text
Você já utilizou suas revisões incluídas.

Revisão adicional:
R$ 10,00

[Adicionar revisão]
```

O preço deverá ser validado no servidor.

---

# 16. Histórico

Cada projeto deverá possuir um histórico básico.

Exemplo:

```text
21/09 — Pagamento aprovado
21/09 — Projeto criado
22/09 — Produção iniciada
24/09 — Arquivo solicitado
24/09 — Cliente enviou arquivo
25/09 — Produção retomada
27/09 — Projeto entregue
```

O histórico ajuda o cliente e a Dream Arte a entenderem o andamento do projeto.

---

# 17. Notificações

O cliente deverá possuir uma área de notificações.

Exemplos:

* Pagamento aprovado
* Projeto iniciado
* Informação necessária
* Nova mensagem/solicitação
* Revisão recebida
* Projeto entregue
* Novo arquivo disponível

As notificações poderão ser marcadas como lidas.

---

# 18. E-mails

Eventos importantes poderão gerar e-mails automáticos.

Exemplos:

### Pagamento

"Seu pagamento foi aprovado."

### Produção

"Seu projeto entrou em produção."

### Pendência

"Precisamos de uma informação para continuar seu projeto."

### Entrega

"Seu projeto está pronto para download."

Os textos finais dos e-mails serão definidos posteriormente.

---

# 19. Pedidos

Página:

`/minha-conta/pedidos/`

Mostrar os pedidos feitos pelo cliente.

Cada pedido deverá apresentar:

* Número
* Data
* Valor
* Status
* Projetos relacionados
* Ação para visualizar

Exemplo:

```text
Pedido #105

21/09/2026

R$ 279,70

Pagamento aprovado

3 projetos

[Ver pedido]
```

---

# 20. Relação entre pedidos e projetos

Um pedido poderá conter vários projetos.

Exemplo:

```text
Pedido #105
R$ 279,70

├── Logo Profissional
│   └── Projeto #201
│
├── 5 Posts
│   └── Projeto #202
│
└── Landing Page
    └── Projeto #203
```

O cliente poderá visualizar o pedido e entrar individualmente em cada projeto.

---

# 21. Entregas

Página:

`/minha-conta/entregas/`

Mostrar projetos que possuem arquivos finais disponíveis.

Exemplo:

```text
Suas entregas

Logo — Entregue
[Ver arquivos]

Posts — Entregue
[Ver arquivos]

Landing Page — Entregue
[Ver arquivos]
```

---

# 22. Favoritos

Página:

`/favoritos/`

O cliente poderá visualizar os serviços salvos.

Exemplo:

```text
Meus favoritos

❤️ Landing Page
A partir de R$ 99,90

❤️ Logo
A partir de R$ 49,90

❤️ Loja Virtual
A partir de R$ 249,90
```

A partir dessa página poderá iniciar a configuração de um serviço.

---

# 23. Perfil

Página:

`/minha-conta/perfil/`

Dados possíveis:

* Nome
* E-mail
* WhatsApp
* CPF, quando aplicável
* Senha

O cliente poderá atualizar os dados permitidos.

Dados relacionados a pedidos antigos não deverão ser alterados de maneira que prejudique o histórico financeiro.

---

# 24. Segurança

A área do cliente deverá exigir autenticação.

Todas as ações deverão verificar a propriedade do recurso.

Exemplos:

Um cliente não pode:

* Ver projeto de outro cliente
* Baixar arquivo de outro cliente
* Alterar pedido de outro cliente
* Solicitar revisão em projeto de outro cliente
* Acessar informações privadas de outro cliente

Essas verificações deverão acontecer no servidor.

---

# 25. Responsividade

A área do cliente deverá funcionar corretamente em:

* Celular
* Tablet
* Notebook
* Desktop

No celular:

* Cards devem se adaptar
* Botões devem ser fáceis de tocar
* Menu deve ser simples
* Informações importantes devem aparecer primeiro
* Arquivos devem ser fáceis de acessar

---

# 26. Aparência

A área do cliente deverá seguir a identidade visual da Dream Arte Studio.

Características:

* Moderna
* Premium
* Limpa
* Organizada
* Roxo/lilás como identidade
* Fundo claro ou escuro conforme o design definido
* Cards modernos
* Ícones claros
* Animações discretas
* Boa hierarquia visual

Não deve parecer o painel padrão do WordPress.

Também não deve parecer uma instalação padrão do WooCommerce.

---

# 27. Experiência ideal

O cliente deve conseguir abrir a área e entender rapidamente:

**O que comprei?**

**Em que etapa está?**

**Preciso fazer alguma coisa?**

**Quando ficará pronto?**

**Onde estão meus arquivos?**

A interface deverá responder essas perguntas sem exigir conhecimento técnico.

---

# 28. Princípio geral

A área do cliente deve funcionar como um pequeno painel de projetos.

O cliente não precisa conhecer:

* WordPress
* WooCommerce
* Elementor
* Mercado Pago
* Estrutura interna do plugin

Essas tecnologias devem ficar ocultas da experiência do cliente.

Para o cliente, existe apenas:

**Meu pedido → Meu projeto → Meu andamento → Minha entrega.**
