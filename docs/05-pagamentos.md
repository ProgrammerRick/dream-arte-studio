# Dream Arte Studio — Pagamentos

Este documento define como os pagamentos da plataforma Dream Arte Studio deverão funcionar.

A infraestrutura de pagamento será baseada em WooCommerce + Mercado Pago.

---

# 1. Arquitetura de pagamento

Responsabilidades:

### WooCommerce

Responsável por:

* Carrinho
* Checkout
* Pedido
* Status do pedido
* Valor do pedido
* Registro da transação
* Integração com o gateway

### Mercado Pago

Responsável por:

* Processamento do pagamento
* Pix
* Cartão de crédito
* Comunicação do resultado do pagamento com o WooCommerce

### Dream Arte Studio Core

Responsável por:

* Receber a configuração do serviço
* Validar opções
* Recalcular preço
* Criar/associar projetos
* Reagir à confirmação do pagamento
* Associar pedido aos projetos
* Atualizar informações específicas da plataforma

---

# 2. Métodos de pagamento

Métodos planejados:

* Pix
* Cartão de crédito

Outros métodos não fazem parte da primeira versão.

---

# 3. Mercado Pago

O Mercado Pago será utilizado através da integração disponível para WooCommerce.

Configuração atual planejada:

* Mercado Pago Checkout Transparente
* Mercado Pago Checkout Transparente PIX

O processamento deverá permanecer dentro da infraestrutura segura do Mercado Pago.

---

# 4. Cartão de crédito

O cliente poderá pagar utilizando cartão de crédito através do Mercado Pago.

A Dream Arte Studio não deverá:

* Armazenar número do cartão
* Armazenar código de segurança
* Armazenar dados completos do cartão
* Criar processamento próprio de cartão

Esses dados deverão ser tratados pelo Mercado Pago.

---

# 5. Pix

O Pix será disponibilizado através do Mercado Pago.

O fluxo será:

```text
Cliente finaliza pedido
        ↓
Escolhe Pix
        ↓
Mercado Pago gera cobrança
        ↓
Cliente realiza pagamento
        ↓
Mercado Pago processa
        ↓
Mercado Pago confirma pagamento
        ↓
WooCommerce recebe atualização
        ↓
Pedido é atualizado
        ↓
Dream Arte Studio Core processa o pedido
```

Enquanto o pagamento não for confirmado, o pedido não deverá ser tratado como pago.

---

# 6. Expiração do Pix

A configuração atual do Pix utiliza prazo de expiração de:

**30 minutos**

Esse prazo poderá ser alterado posteriormente nas configurações do Mercado Pago.

O sistema não deve considerar o pedido pago apenas porque uma cobrança Pix foi criada.

O pagamento precisa ser efetivamente confirmado.

---

# 7. Status do pagamento

O sistema deverá distinguir status do pagamento de status do projeto.

Exemplos de pagamento:

* Aguardando pagamento
* Aprovado
* Recusado
* Cancelado
* Estornado
* Expirado

Os status exatos disponíveis deverão respeitar os estados fornecidos pelo Mercado Pago/WooCommerce.

---

# 8. Status do pedido

O WooCommerce continuará sendo responsável pelo estado comercial do pedido.

O Dream Arte Studio Core poderá reagir às mudanças de status.

Exemplo:

```text
Pedido criado
↓
Aguardando pagamento
↓
Pagamento aprovado
↓
Pedido processado
↓
Produção iniciada
```

Não alterar o status do pedido de forma arbitrária sem considerar o estado real do pagamento.

---

# 9. Regra fundamental

**Pagamento aprovado é o gatilho para iniciar o trabalho pago.**

Antes da confirmação:

* Não considerar o pedido pago
* Não iniciar automaticamente a produção
* Não liberar entrega
* Não liberar arquivos finais

Depois da confirmação:

* Registrar pagamento aprovado
* Ativar/criar projetos
* Notificar administrador
* Notificar cliente
* Permitir início da produção

---

# 10. Segurança do preço

O cliente poderá configurar um serviço no frontend.

O frontend poderá calcular:

```text
pacote + adicionais = total
```

Porém, esse cálculo não será considerado confiável.

Antes de criar o pedido:

```text
Frontend
   ↓
Envia opções
   ↓
Servidor
   ↓
Valida opções
   ↓
Recalcula preço
   ↓
Confirma total
   ↓
WooCommerce cria pedido
```

O preço final enviado ao WooCommerce deverá ser definido pelo servidor.

---

# 11. Não confiar no frontend

O usuário não poderá modificar o preço apenas alterando:

* JavaScript
* HTML
* Campos escondidos
* Requisições do navegador
* Parâmetros enviados pelo frontend

O servidor deverá possuir uma fonte confiável dos preços.

---

# 12. Fonte dos preços

Os preços dos serviços e adicionais deverão ser definidos no backend.

A estrutura deverá permitir:

* Pacotes
* Adicionais
* Preços
* Regras
* Ativação/desativação de opções

O frontend deverá consultar essa estrutura em vez de possuir preços independentes que possam ficar diferentes do backend.

---

# 13. Exemplo de cálculo

Exemplo:

```text
Landing Page Profissional
R$ 149,90

Seção adicional
R$ 15,00

Copy
R$ 30,00

TOTAL
R$ 194,90
```

O frontend mostra:

**R$ 194,90**

O servidor calcula novamente:

**R$ 194,90**

Somente então o pedido pode ser criado.

---

# 14. Carrinho

O carrinho poderá conter vários serviços.

Exemplo:

```text
Logo Profissional        R$ 79,90
5 Posts                  R$ 49,90
Landing Page             R$ 149,90

Total                    R$ 279,70
```

O WooCommerce deverá registrar o total do pedido.

Cada item deverá manter informações suficientes para identificar sua configuração.

---

# 15. Dados da configuração

A configuração escolhida pelo cliente deverá ser associada ao item/pedido.

Exemplo:

```text
Serviço: Landing Page
Pacote: Profissional
Seção adicional: Sim
Copy: Sim
Total: R$ 194,90
```

Essas informações serão necessárias para a produção.

---

# 16. Pedido pago

Depois que o pagamento for confirmado:

1. WooCommerce atualiza o pedido.
2. Dream Arte Studio Core identifica a confirmação.
3. O sistema cria ou ativa os projetos.
4. Cada projeto recebe suas informações.
5. O administrador recebe uma notificação.
6. O cliente recebe uma confirmação.
7. O projeto pode entrar em produção.

---

# 17. Evitar duplicação

O sistema deverá evitar criar dois projetos para o mesmo item devido a:

* Reenvio de webhook
* Atualização repetida do pedido
* Recarregamento da página
* Eventos duplicados
* Processamento repetido

Antes de criar um projeto, o Dream Arte Studio Core deverá verificar se aquele projeto já foi criado.

---

# 18. Webhooks / notificações de pagamento

A confirmação do pagamento deverá utilizar os mecanismos oficiais da integração Mercado Pago/WooCommerce.

Quando houver um evento de pagamento:

1. Validar o evento.
2. Identificar o pedido.
3. Confirmar o estado do pagamento.
4. Atualizar o pedido.
5. Executar as ações necessárias.

Não confiar apenas em uma mensagem enviada pelo navegador do cliente.

---

# 19. Cliente fecha a página

Se o cliente fechar o navegador depois de iniciar um Pix:

O pedido deverá continuar existindo.

Quando o pagamento for confirmado posteriormente, o WooCommerce/Mercado Pago deverá atualizar o pedido.

O cliente não precisa permanecer na página até o pagamento ser confirmado.

---

# 20. Pagamento recusado

Se o cartão for recusado:

* O pedido não deverá ser considerado pago.
* O cliente deverá receber uma mensagem clara.
* O cliente poderá tentar novamente quando permitido.
* Nenhum projeto pago deverá ser liberado indevidamente.

---

# 21. Pix expirado

Se o Pix expirar sem pagamento:

* O pedido não deverá ser tratado como pago.
* O cliente deverá visualizar o estado correto.
* Poderá existir uma opção para tentar novamente, conforme o comportamento permitido pela integração.

---

# 22. Estorno/cancelamento

Se um pagamento já aprovado for posteriormente estornado ou cancelado:

O sistema deverá atualizar o estado correspondente.

O Dream Arte Studio Core não deverá manter automaticamente um projeto como "pago" se o estado financeiro deixar de representar um pagamento válido.

Qualquer regra de reembolso deverá ser definida comercialmente antes de implementar automações financeiras.

---

# 23. Checkout

O checkout deverá ser visualmente personalizado.

Evitar a aparência padrão do WooCommerce quando possível.

O cliente deverá visualizar:

* Dados pessoais
* Resumo dos serviços
* Total
* Forma de pagamento
* Informações importantes
* Botão para finalizar pagamento

---

# 24. Não exigir cadastro antes do checkout

O cliente não precisa criar uma conta antes de comprar.

O checkout deverá coletar os dados necessários.

Depois da compra, o sistema poderá criar a conta do cliente.

---

# 25. Conta do cliente

Quando um novo cliente realizar uma compra, o sistema poderá criar automaticamente uma conta.

A conta permitirá acessar:

* Projetos
* Pedidos
* Entregas
* Arquivos
* Revisões
* Favoritos
* Perfil

---

# 26. Notificações após pagamento

Após pagamento aprovado:

### Cliente

Receber confirmação de que o pagamento foi aprovado.

### Dream Arte

Receber aviso de novo pedido pago.

A notificação deverá conter informações úteis para identificar:

* Cliente
* Pedido
* Serviços
* Valor
* Projetos

---

# 27. Produção

A produção somente deverá começar automaticamente quando:

* O pagamento estiver confirmado
* O pedido estiver em estado válido
* Os dados necessários estiverem disponíveis

Se faltarem informações, o projeto poderá ficar:

**Aguardando cliente**

---

# 28. Ambiente de testes

Durante o desenvolvimento, utilizar o ambiente de testes do Mercado Pago quando disponível.

O objetivo é testar:

* Pix
* Cartão
* Aprovação
* Recusa
* Expiração
* Atualização de pedido
* Criação de projeto
* Notificações

Não utilizar pagamentos reais durante os testes.

---

# 29. Produção

Somente depois de testar o fluxo completo deverá ser utilizado o modo de produção.

Antes de mudar para produção, verificar:

* Checkout
* Pix
* Cartão
* Webhooks
* Status do pedido
* Criação de projetos
* Notificações
* Segurança
* Valores
* Área do cliente

---

# 30. Regra para o desenvolvimento

Nenhum código próprio deverá tentar substituir o processamento do Mercado Pago.

O sistema próprio deve cuidar da lógica da plataforma.

O Mercado Pago deve cuidar do processamento do pagamento.

O WooCommerce deve cuidar da estrutura comercial do pedido.

A divisão de responsabilidades deve permanecer clara:

```text
Dream Arte Studio Core
        ↓
Configuração e projetos

WooCommerce
        ↓
Carrinho, checkout e pedidos

Mercado Pago
        ↓
Processamento financeiro
```

---

# 31. Objetivo final

O cliente deverá perceber apenas uma experiência simples:

```text
Escolher serviço
      ↓
Configurar
      ↓
Ver preço
      ↓
Pagar
      ↓
Pedido confirmado
      ↓
Acompanhar projeto
      ↓
Receber entrega
```

Toda a complexidade técnica deverá permanecer no backend.
