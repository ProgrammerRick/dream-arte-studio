# Dream Arte Studio — Regras do Sistema

Este documento define as regras gerais que deverão ser respeitadas pelo sistema Dream Arte Studio.

Essas regras devem orientar o desenvolvimento do frontend, backend e do plugin Dream Arte Studio Core.

---

# 1. Princípio geral

A plataforma deve ser modular, segura e organizada.

Cada tecnologia deverá possuir uma responsabilidade clara.

```text id="5q6e1u"
WordPress
↓
Base da plataforma

WooCommerce
↓
Carrinho, checkout e pedidos

Mercado Pago
↓
Processamento de pagamentos

Dream Arte Studio Core
↓
Lógica personalizada da plataforma

Elementor Free
↓
Construção visual
```

---

# 2. Regra de segurança

Toda informação enviada pelo navegador deve ser considerada não confiável.

Isso inclui:

* Preços
* IDs
* Quantidades
* Opções
* Status
* Permissões
* URLs
* Dados enviados por formulários

O servidor deverá validar tudo que for necessário.

---

# 3. Preços

O preço oficial deve existir no backend.

O frontend poderá calcular e mostrar o preço para proporcionar uma experiência rápida.

Porém:

**O preço enviado pelo frontend nunca deve ser considerado definitivo.**

O servidor deverá:

1. Receber as opções.
2. Validar as opções.
3. Consultar os preços oficiais.
4. Recalcular o total.
5. Criar o pedido usando o valor validado.

---

# 4. Manipulação de preço

Não permitir que o cliente altere o preço através de:

* DevTools
* JavaScript
* HTML
* Campos ocultos
* Requisições HTTP
* Parâmetros modificados
* Cookies
* Local Storage

O preço deverá ser determinado no servidor.

---

# 5. Usuários

Existirão principalmente dois tipos de usuários:

### Cliente

Pode:

* Comprar serviços
* Ver seus pedidos
* Ver seus projetos
* Enviar arquivos
* Solicitar revisões
* Responder solicitações
* Baixar entregas
* Gerenciar favoritos
* Gerenciar seus dados permitidos

### Administrador

Pode:

* Gerenciar pedidos
* Gerenciar projetos
* Gerenciar clientes
* Alterar status
* Adicionar arquivos
* Liberar entregas
* Gerenciar revisões
* Gerenciar pedidos personalizados
* Visualizar informações administrativas

---

# 6. Permissões

Nunca confiar somente no frontend para controlar permissões.

Exemplo:

Esconder um botão não significa impedir a ação.

O servidor deverá verificar se o usuário possui permissão antes de:

* Ver projeto
* Editar projeto
* Baixar arquivo
* Enviar revisão
* Alterar informações
* Alterar status
* Acessar informações privadas

---

# 7. Propriedade dos dados

Cada recurso privado deverá possuir uma relação clara com seu proprietário.

Exemplo:

```text id="h7v4jp"
Usuário
↓
Pedido
↓
Projeto
↓
Arquivo
```

O sistema deverá conseguir verificar essa relação.

---

# 8. Clientes não podem acessar outros clientes

Um cliente não poderá:

* Ver pedidos de outro cliente
* Ver projetos de outro cliente
* Ver arquivos de outro cliente
* Baixar arquivos de outro cliente
* Ver informações pessoais de outro cliente
* Alterar dados de outro cliente

Essas restrições deverão ser aplicadas no servidor.

---

# 9. Administrador

As funcionalidades administrativas deverão exigir autenticação e permissão adequada.

Não utilizar somente URLs escondidas como mecanismo de segurança.

---

# 10. Pedidos

O WooCommerce será responsável pelos pedidos comerciais.

Um pedido poderá conter vários serviços.

Exemplo:

```text id="j3q2h1"
Pedido #105

├── Logo
├── 5 Posts
└── Landing Page
```

---

# 11. Projetos

Cada serviço comprado poderá gerar um projeto.

Um pedido pode possuir vários projetos.

Cada projeto deverá possuir:

* Identificador
* Pedido relacionado
* Cliente
* Serviço
* Configuração
* Status
* Datas
* Prazo
* Revisões
* Arquivos
* Histórico

---

# 12. Pedido não é projeto

Não tratar pedido e projeto como a mesma coisa.

### Pedido

Representa a compra/transação.

### Projeto

Representa o trabalho que será produzido.

Essa separação deve permanecer durante toda a arquitetura.

---

# 13. Status

Os status do projeto são diferentes dos status financeiros.

Status planejados do projeto:

* Aguardando pagamento
* Pagamento aprovado
* Em produção
* Aguardando cliente
* Em revisão
* Entregue
* Concluído
* Cancelado

O sistema não deverá misturar automaticamente estados financeiros e estados de produção sem uma regra definida.

---

# 14. Pagamento

O pagamento será processado pelo Mercado Pago através da integração com WooCommerce.

Não criar processamento próprio de cartão.

Não armazenar dados completos do cartão.

---

# 15. Confirmação de pagamento

O projeto somente deverá ser considerado pago quando o sistema receber uma confirmação válida do pagamento.

Não considerar pago apenas porque:

* O cliente clicou em pagar
* O checkout foi aberto
* Um Pix foi gerado
* O cliente voltou para o site
* O navegador informou sucesso

A confirmação deverá vir do fluxo confiável da integração.

---

# 16. Webhooks

Eventos externos de pagamento poderão ser enviados mais de uma vez.

O sistema deverá ser preparado para isso.

Operações importantes deverão ser idempotentes.

Exemplo:

Se o mesmo evento de pagamento for processado duas vezes, o sistema não deverá:

* Criar dois projetos
* Criar duas entregas
* Enviar várias ações duplicadas
* Duplicar informações

---

# 17. Carrinho

O cliente poderá adicionar vários serviços.

Cada item deverá preservar sua configuração.

Exemplo:

```text id="xw4a1c"
Item:
Landing Page Profissional

Configuração:
- Profissional
- Seção adicional
- Copy

Preço validado:
R$ 194,90
```

---

# 18. Configuradores

Cada serviço poderá possuir seu próprio configurador.

Não criar um configurador gigante com todas as opções de todos os serviços misturadas.

A estrutura deverá ser modular.

Exemplo:

```text id="f5qv73"
Configurador de Música
Configurador de Logo
Configurador de Posts
Configurador de Landing Page
Configurador de Loja
```

Cada um utiliza regras próprias.

---

# 19. Opções inválidas

O servidor deverá rejeitar combinações inválidas.

Exemplo:

Se determinado adicional só existir para um pacote específico, o servidor deverá verificar isso.

Não confiar no fato de o frontend esconder a opção.

---

# 20. Campos obrigatórios

Os campos obrigatórios deverão ser definidos por serviço.

Exemplo:

Uma música poderá exigir:

* Objetivo
* Estilo
* Clima
* Destinatário
* Descrição

Enquanto uma imagem poderá exigir informações diferentes.

O servidor deverá validar os campos necessários.

---

# 21. Uploads

Arquivos enviados pelo cliente deverão ser validados.

Verificar:

* Tamanho
* Tipo
* Permissão
* Projeto relacionado

Não confiar somente na extensão do arquivo.

---

# 22. Segurança de arquivos

Arquivos privados não deverão ser públicos simplesmente por possuírem uma URL.

O acesso deverá passar por uma verificação de autorização.

---

# 23. Revisões

Cada projeto deverá possuir controle de revisões.

O sistema deverá saber:

* Quantas revisões estão incluídas
* Quantas foram utilizadas
* Quantas restam
* Quais solicitações foram feitas

---

# 24. Revisão adicional

Quando o limite for atingido, o sistema poderá oferecer revisão adicional paga.

Exemplo:

```text id="h7f1zi"
Revisões incluídas: 2
Utilizadas: 2

Revisão adicional:
R$ 10,00
```

O valor deverá ser validado no servidor.

---

# 25. Aguardando cliente

Quando a Dream Arte precisar de uma ação do cliente, o projeto poderá entrar em:

**Aguardando cliente**

Deverá existir uma solicitação registrada.

Exemplo:

```text id="2o8wpr"
Precisamos de uma informação

Envie a imagem principal do projeto.
```

---

# 26. Histórico

Alterações importantes deverão ser registradas.

Exemplos:

* Projeto criado
* Pagamento aprovado
* Produção iniciada
* Arquivo enviado
* Cliente respondeu
* Revisão solicitada
* Entrega liberada

---

# 27. Notificações

Notificações deverão ser disparadas somente quando houver um evento válido.

Evitar notificações duplicadas.

---

# 28. E-mail

O e-mail poderá ser utilizado para eventos importantes.

Exemplos:

* Pedido recebido
* Pagamento aprovado
* Projeto iniciado
* Informação necessária
* Entrega disponível

---

# 29. WhatsApp

O WhatsApp poderá ser utilizado como canal complementar.

Não depender exclusivamente dele para armazenar informações importantes do projeto.

A plataforma deverá continuar sendo a fonte principal.

---

# 30. Pedido personalizado

Pedidos personalizados não possuem preço automático.

Fluxo:

```text id="4j1o3b"
Solicitação
↓
Análise
↓
Orçamento
↓
Aprovação
↓
Pagamento
↓
Projeto
```

Não cobrar automaticamente antes da definição do orçamento.

---

# 31. Cancelamento

Cancelamentos deverão respeitar regras comerciais e o estado do pedido.

Não implementar reembolso automático sem uma regra comercial definida.

---

# 32. Dados financeiros

Informações financeiras devem permanecer vinculadas ao WooCommerce e Mercado Pago.

O Dream Arte Studio Core deverá consumir as informações necessárias sem tentar substituir o sistema financeiro.

---

# 33. Logs

O sistema poderá registrar eventos técnicos importantes.

Exemplos:

* Erro de integração
* Falha no processamento
* Evento de pagamento
* Criação de projeto
* Upload
* Download
* Alteração de status

Os logs não devem expor dados sensíveis desnecessariamente.

---

# 34. Nonces e proteção de requisições

Ações realizadas através de AJAX, REST API ou formulários deverão utilizar mecanismos adequados de proteção.

Quando aplicável:

* Nonces
* Verificação de capacidade
* Autenticação
* Sanitização
* Validação

---

# 35. Sanitização

Dados recebidos pelo sistema deverão ser tratados adequadamente antes de serem armazenados.

Textos, campos, IDs e outros valores deverão utilizar as funções apropriadas do WordPress/PHP.

---

# 36. Escape

Dados exibidos no frontend deverão ser escapados adequadamente para evitar problemas de segurança.

Não inserir conteúdo recebido do usuário diretamente no HTML sem tratamento.

---

# 37. SQL

Quando houver consultas personalizadas ao banco de dados, utilizar mecanismos seguros de consulta.

Não concatenar diretamente dados fornecidos pelo usuário em SQL.

---

# 38. REST API / AJAX

Caso o sistema utilize AJAX ou REST API:

* Validar autenticação
* Validar permissões
* Validar nonce quando aplicável
* Validar dados recebidos
* Recalcular preços no servidor
* Retornar somente dados necessários

---

# 39. Erros

As mensagens exibidas ao cliente devem ser claras.

Evitar mostrar:

* Stack traces
* Caminhos internos do servidor
* SQL
* Informações técnicas desnecessárias
* Dados sensíveis

O administrador poderá receber informações técnicas adicionais através de logs.

---

# 40. Experiência do usuário

Erros devem ser apresentados de forma compreensível.

Exemplo:

Em vez de:

```text id="4l0vjy"
Fatal error / invalid nonce / exception
```

Mostrar:

```text id="e8w2rx"
Não foi possível concluir esta ação.

Tente novamente.
```

---

# 41. Responsividade

Toda funcionalidade deverá funcionar em:

* Celular
* Tablet
* Notebook
* Desktop

A experiência mobile é prioridade.

---

# 42. Performance

Evitar:

* Scripts desnecessários
* Bibliotecas duplicadas
* Consultas excessivas ao banco
* Imagens exageradamente pesadas
* Código repetido

Carregar recursos somente quando necessários.

---

# 43. Código modular

Não colocar toda a plataforma em um único arquivo gigante.

O Dream Arte Studio Core deverá possuir estrutura organizada.

Exemplo:

```text id="3p3m3g"
dream-arte-studio-core/
├── dream-arte-studio-core.php
├── includes/
├── admin/
├── frontend/
├── services/
├── projects/
├── orders/
├── payments/
├── client-area/
├── deliveries/
├── revisions/
└── assets/
```

A estrutura poderá mudar durante a implementação, desde que continue organizada.

---

# 44. Compatibilidade

O plugin deverá ser desenvolvido considerando:

* WordPress
* WooCommerce
* Elementor Free
* Mercado Pago

Evitar depender de Elementor Pro quando não for necessário.

---

# 45. Elementor

O Elementor será principalmente responsável pela apresentação visual das páginas.

A lógica crítica do sistema deverá permanecer no plugin/backend.

Não colocar regras importantes somente em widgets HTML/JavaScript.

---

# 46. WooCommerce

WooCommerce deverá continuar sendo utilizado para:

* Produtos/base comercial
* Carrinho
* Checkout
* Pedidos
* Status financeiros
* Integração com gateway

Não substituir o WooCommerce sem necessidade.

---

# 47. Mercado Pago

Mercado Pago deverá cuidar do processamento financeiro.

O código próprio não deverá:

* Processar cartão
* Armazenar cartão
* Simular aprovação
* Considerar Pix pago sem confirmação

---

# 48. Fonte única da verdade

Evitar manter a mesma informação crítica em vários lugares diferentes.

Exemplo:

O preço oficial deve possuir uma fonte confiável.

O status do pagamento deve vir da integração comercial.

O projeto deve possuir seu próprio estado de produção.

---

# 49. Alterações futuras

Antes de alterar uma regra estrutural:

1. Verificar a documentação.
2. Verificar dependências.
3. Verificar se existem pedidos/projetos afetados.
4. Atualizar os documentos do projeto.
5. Depois implementar.

---

# 50. Regra para o Claude

Antes de desenvolver qualquer funcionalidade, o Claude deverá:

1. Ler o README.
2. Ler os documentos relevantes em `docs/`.
3. Entender a arquitetura existente.
4. Verificar o código já criado.
5. Não recriar funcionalidades que já existem.
6. Não alterar arquitetura sem necessidade.
7. Explicar alterações importantes.
8. Manter compatibilidade com a estrutura existente.
9. Priorizar segurança no backend.
10. Testar as funcionalidades implementadas.

---

# 51. Regra de desenvolvimento incremental

Não tentar construir toda a plataforma de uma vez.

O projeto deverá ser desenvolvido por etapas.

Cada etapa deverá:

* Ter objetivo definido
* Ter arquivos específicos
* Ser implementada
* Ser testada
* Ser corrigida
* Ser documentada quando necessário

Somente depois avançar para a próxima etapa.

---

# 52. Objetivo final

A Dream Arte Studio deve funcionar como uma plataforma própria de serviços digitais.

Para o cliente:

```text id="m7azlq"
Escolher
↓
Configurar
↓
Comprar
↓
Pagar
↓
Acompanhar
↓
Revisar
↓
Receber
```

Para a Dream Arte:

```text id="g0r1ph"
Receber pedido
↓
Confirmar pagamento
↓
Produzir
↓
Solicitar informações
↓
Revisar
↓
Entregar
↓
Concluir
```

Toda a estrutura deve ser segura, modular e preparada para futuras melhorias.
