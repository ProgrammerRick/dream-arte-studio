# Dream Arte Studio — Fluxo do Cliente

Este documento define a jornada do cliente dentro da plataforma Dream Arte Studio.

O objetivo é criar uma experiência simples, clara e profissional, desde a escolha do serviço até a entrega final.

---

# 1. Jornada principal

Fluxo geral:

```text
Página inicial
      ↓
Serviços
      ↓
Escolha do serviço
      ↓
Configuração
      ↓
Resumo do projeto
      ↓
Meu Projeto / Carrinho
      ↓
Checkout
      ↓
Pagamento
      ↓
Pedido aprovado
      ↓
Projeto criado
      ↓
Produção
      ↓
Revisões / informações
      ↓
Entrega
      ↓
Download
      ↓
Projeto concluído
```

---

# 2. Página inicial

A página inicial deve apresentar:

* Identidade da Dream Arte Studio
* Principais serviços
* Benefícios
* Como funciona
* Portfólio/demonstrações
* Perguntas frequentes
* Chamada para ação

O usuário deverá conseguir chegar aos serviços rapidamente.

A interface deve ser responsiva e funcionar principalmente bem no celular.

---

# 3. Página de serviços

URL:

`/servicos/`

Deve apresentar todos os serviços disponíveis.

Serviços:

1. Música personalizada
2. Imagem personalizada
3. Posts
4. Logo
5. Convite
6. Flyer/Cartão
7. Template
8. Landing Page
9. Site institucional
10. Loja Virtual
11. Pedido personalizado

Cada serviço deverá possuir:

* Nome
* Imagem/visual
* Descrição curta
* Preço inicial, quando aplicável
* Principais características
* Botão para conhecer/configurar

---

# 4. Página individual do serviço

Cada serviço terá uma página própria.

Exemplos:

`/servicos/musica-personalizada/`

`/servicos/logo/`

`/servicos/landing-page/`

`/servicos/loja-virtual/`

A página deverá explicar o serviço e apresentar o configurador.

---

# 5. Configurador

O configurador é uma das partes principais da plataforma.

Ele deve permitir que o cliente escolha as características do serviço.

As opções devem variar de acordo com cada serviço.

Exemplo:

```text
Serviço
↓
Pacote
↓
Opções
↓
Adicionais
↓
Informações
↓
Resumo
```

O preço deverá ser atualizado automaticamente conforme o cliente seleciona as opções.

---

# 6. Preço

O cliente deverá visualizar o preço de forma clara.

Exemplo:

```text
Landing Page Profissional     R$ 149,90
Seção adicional               R$  15,00
Copy personalizada            R$  30,00
----------------------------------------
Total                         R$ 194,90
```

O total deve atualizar imediatamente quando uma opção for adicionada ou removida.

---

# 7. Validação do preço

O JavaScript poderá calcular e mostrar o preço no navegador.

Porém, esse valor não será considerado confiável para fins de pagamento.

Quando o cliente enviar a configuração:

1. O servidor recebe as opções.
2. O Dream Arte Studio Core valida cada opção.
3. O servidor calcula novamente o preço.
4. O servidor verifica se as opções são válidas.
5. Somente então o pedido poderá ser criado.

Nunca confiar somente no preço enviado pelo frontend.

---

# 8. Informações do projeto

Dependendo do serviço, o cliente poderá precisar fornecer informações.

Exemplos:

### Música

* História
* Nomes
* Mensagem
* Estilo
* Clima
* Destinatário
* Referências

### Logo

* Nome da marca
* Segmento
* Preferências
* Cores
* Referências

### Landing Page

* Nome da empresa/projeto
* Objetivo
* Textos
* Imagens
* WhatsApp
* Links
* Referências

### Loja Virtual

* Informações da empresa
* Produtos
* Categorias
* Imagens
* Dados de contato
* Configurações necessárias

Os campos devem aparecer conforme o serviço selecionado.

Não mostrar campos desnecessários.

---

# 9. Upload de arquivos

Quando o serviço permitir ou exigir referências, o cliente poderá enviar arquivos.

Exemplos:

* Imagens
* Logos existentes
* Textos
* Documentos
* Referências visuais

O sistema deverá:

* Validar o tipo do arquivo
* Validar o tamanho
* Associar o arquivo ao projeto correto
* Impedir acesso de outros clientes
* Armazenar as informações necessárias no projeto

---

# 10. Resumo antes da compra

Antes de adicionar ao carrinho, mostrar:

* Nome do serviço
* Pacote
* Opções escolhidas
* Adicionais
* Informações principais
* Prazo estimado
* Valor final

Botão principal:

**Adicionar ao meu projeto**

Também poderá existir:

**Continuar escolhendo serviços**

---

# 11. Meu Projeto / Carrinho

A área de carrinho deverá ter uma aparência personalizada.

Evitar apresentar o carrinho como uma página WooCommerce genérica.

O cliente poderá ter vários serviços no mesmo pedido.

Exemplo:

```text
Meu projeto

Logo Profissional
R$ 79,90

5 Posts
R$ 49,90

Landing Page Profissional
R$ 149,90

----------------------
Total: R$ 279,70
```

Cada item poderá ser editado ou removido antes do checkout.

---

# 12. Favoritos

O cliente poderá salvar serviços para contratar depois.

Exemplo:

```text
❤️ Landing Page
❤️ Logo
❤️ Loja Virtual
```

O favorito não gera pedido nem cobrança.

O cliente poderá remover o favorito ou iniciar a configuração do serviço.

---

# 13. Checkout

O checkout deverá ser simples e personalizado.

O cliente deverá informar os dados necessários.

Dados principais:

* Nome
* E-mail
* WhatsApp
* CPF, quando necessário
* Dados adicionais exigidos pelo pagamento

O cliente não deverá ser obrigado a criar uma conta antes de comprar.

---

# 14. Criação da conta

O sistema poderá criar automaticamente uma conta para um novo cliente durante ou após a compra.

O objetivo é evitar uma etapa desnecessária antes do pagamento.

Clientes que já possuem conta poderão entrar normalmente.

---

# 15. Pagamento

O pagamento será realizado através do Mercado Pago integrado ao WooCommerce.

Métodos:

* Pix
* Cartão de crédito

O código próprio da Dream Arte não deverá armazenar dados de cartão.

O Mercado Pago deverá cuidar do processamento dos dados sensíveis do cartão.

---

# 16. Pedido aguardando pagamento

Depois que o cliente confirmar a compra, o pedido poderá ficar:

**Aguardando pagamento**

Isso é especialmente importante para Pix.

Enquanto o pagamento não for confirmado, o pedido não deverá ser considerado pago.

---

# 17. Pagamento aprovado

Quando o Mercado Pago confirmar o pagamento:

1. WooCommerce atualiza o pedido.
2. Dream Arte Studio Core identifica o pagamento.
3. O projeto correspondente é criado/ativado.
4. O cliente recebe uma confirmação.
5. O administrador recebe uma notificação.
6. O projeto fica disponível para produção.

---

# 18. Criação do projeto

Um pedido pode possuir vários serviços.

Exemplo:

```text
Pedido #105

├── Projeto 1 — Logo
├── Projeto 2 — 5 Posts
└── Projeto 3 — Landing Page
```

Cada projeto deverá guardar sua própria configuração.

---

# 19. Produção

Quando a Dream Arte começar o trabalho:

Status:

**Em produção**

O cliente deverá conseguir visualizar:

* Serviço
* Status
* Data do pedido
* Informações enviadas
* Prazo
* Histórico básico
* Arquivos relacionados, quando houver

---

# 20. Aguardando cliente

Se faltar uma informação, o administrador poderá alterar o projeto para:

**Aguardando cliente**

Exemplos:

* Falta uma foto
* Falta um texto
* É necessária uma aprovação
* É necessário escolher uma opção
* É necessário corrigir alguma informação

O cliente deverá visualizar claramente o que precisa fazer.

Exemplo:

```text
Precisamos de uma informação sua

Envie a foto que deseja utilizar na página.

[Enviar arquivo]
```

Depois que o cliente responder, o projeto poderá voltar para:

**Em produção**

---

# 21. Revisões

Os serviços possuem diferentes quantidades de revisões incluídas.

O sistema deverá registrar:

* Quantidade de revisões incluídas
* Revisões utilizadas
* Revisões restantes
* Solicitações de revisão

Exemplo:

```text
Revisões incluídas: 2
Utilizadas: 1
Restantes: 1
```

Se o cliente ultrapassar o limite, poderá existir uma cobrança adicional conforme as regras do serviço.

---

# 22. Entrega

Quando o trabalho estiver finalizado:

Status:

**Entregue**

O cliente deverá receber uma notificação.

A área do projeto deverá apresentar:

* Arquivos finais
* Instruções
* Informações importantes
* Data de entrega

---

# 23. Download

Os arquivos finais devem ser protegidos.

Antes de permitir o download, o sistema deverá verificar:

1. Usuário autenticado.
2. Usuário proprietário do projeto.
3. Arquivo pertencente ao projeto.
4. Arquivo liberado para download.

Nunca disponibilizar arquivos privados através de URLs públicas sem controle de acesso.

---

# 24. Projeto concluído

Depois da entrega, o projeto poderá ser marcado como:

**Concluído**

O cliente continuará podendo acessar:

* Projeto
* Pedido
* Arquivos
* Histórico
* Informações da entrega

---

# 25. Comunicação

Inicialmente, a comunicação poderá utilizar o WhatsApp como canal principal.

Porém, informações importantes do projeto deverão permanecer registradas na plataforma.

Exemplos:

* Status
* Arquivos
* Revisões
* Solicitações
* Entregas

O objetivo é evitar que informações importantes fiquem somente em conversas externas.

---

# 26. Notificações

O sistema deverá prever notificações para eventos importantes.

Exemplos:

### Cliente

* Pedido recebido
* Pagamento aprovado
* Projeto iniciado
* Informação necessária
* Revisão solicitada
* Projeto entregue
* Novo arquivo disponível

### Administrador

* Novo pedido
* Pagamento aprovado
* Novo pedido personalizado
* Resposta do cliente
* Upload de arquivo
* Solicitação de revisão

---

# 27. Pedido personalizado

O pedido personalizado possui um fluxo diferente.

```text
Pedido personalizado
↓
Cliente descreve necessidade
↓
Envia referências
↓
Dream Arte analisa
↓
Dream Arte define orçamento
↓
Cliente recebe proposta
↓
Cliente aprova
↓
Pedido de pagamento
↓
Pagamento
↓
Projeto
```

Não deve existir cobrança automática antes da definição do orçamento.

---

# 28. Cancelamento

O sistema deverá permitir que pedidos/projetos sejam marcados como cancelados quando aplicável.

O comportamento financeiro deverá respeitar o status do pagamento e as regras definidas pela Dream Arte.

Não implementar reembolso automático sem uma regra comercial definida.

---

# 29. Experiência no celular

A plataforma deve ser pensada primeiro para uma boa experiência em dispositivos móveis.

Os configuradores devem:

* Ser fáceis de tocar
* Ter campos grandes o suficiente
* Não exigir zoom
* Mostrar o preço claramente
* Manter o resumo acessível
* Evitar excesso de informações na mesma tela

O checkout também deve ser simples no celular.

---

# 30. Objetivo da experiência

A experiência ideal deve ser:

```text
Escolher
   ↓
Configurar
   ↓
Ver preço
   ↓
Pagar
   ↓
Acompanhar
   ↓
Receber
```

O cliente não deve precisar entender WooCommerce, WordPress ou a estrutura técnica por trás da plataforma.

A tecnologia deve ficar em segundo plano.

A interface deve parecer uma plataforma própria da Dream Arte Studio.
