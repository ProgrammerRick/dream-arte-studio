# Dream Arte Studio — Entregas e Downloads

Este documento define como os arquivos dos projetos serão enviados, armazenados, disponibilizados e baixados pelos clientes.

O sistema deverá priorizar segurança, organização e facilidade de uso.

---

# 1. Objetivo

Depois que um projeto estiver pronto, a Dream Arte deverá conseguir disponibilizar os arquivos finais ao cliente através da plataforma.

O cliente deverá conseguir:

* Visualizar que a entrega está pronta
* Ver os arquivos
* Baixar os arquivos
* Identificar qual arquivo pertence ao projeto
* Acessar novamente os arquivos posteriormente

---

# 2. Fluxo de entrega

Fluxo:

```text
Dream Arte finaliza projeto
        ↓
Administrador adiciona arquivos
        ↓
Arquivos ficam associados ao projeto
        ↓
Administrador libera a entrega
        ↓
Projeto muda para "Entregue"
        ↓
Cliente recebe notificação
        ↓
Cliente acessa o projeto
        ↓
Visualiza os arquivos
        ↓
Baixa os arquivos
```

---

# 3. Upload pelo administrador

O administrador deverá conseguir adicionar arquivos dentro do projeto.

Exemplo:

```text
Projeto #203
Landing Page

Adicionar arquivos:

[Selecionar arquivos]
```

Depois do upload, os arquivos deverão ser associados automaticamente ao projeto correto.

---

# 4. Informações do arquivo

Cada arquivo poderá possuir:

* Nome
* Tipo
* Tamanho
* Data de envio
* Projeto relacionado
* Categoria
* Status
* Disponibilidade para o cliente

Exemplo:

```text
Landing-page-final.zip
24 MB
Entrega final
Disponível
```

---

# 5. Categorias de arquivos

Os arquivos poderão ser classificados como:

* Arquivo final
* Prévia
* Referência
* Documento
* Fonte/editável, quando permitido
* Material adicional
* Outro

A categoria ajudará a organizar a entrega.

---

# 6. Arquivos finais

Os arquivos finais somente deverão ficar disponíveis para o cliente quando a Dream Arte liberar a entrega.

Antes disso, o arquivo poderá permanecer privado para uso administrativo.

---

# 7. Proteção dos arquivos

Arquivos de clientes não deverão ser disponibilizados como arquivos públicos sem controle de acesso.

O sistema deverá verificar a autorização antes de liberar um download.

Fluxo:

```text
Cliente solicita download
        ↓
Servidor identifica usuário
        ↓
Servidor identifica arquivo
        ↓
Servidor identifica projeto
        ↓
Verifica proprietário do projeto
        ↓
Verifica autorização
        ↓
Download permitido
```

---

# 8. Regra de propriedade

Um cliente somente poderá acessar arquivos de projetos pertencentes à própria conta.

Nunca permitir acesso simplesmente porque o usuário conhece ou adivinha uma URL.

O servidor deverá verificar a propriedade.

---

# 9. Usuário não autenticado

Usuários não autenticados não deverão conseguir acessar arquivos privados de clientes.

Se tentarem acessar um arquivo protegido:

```text
Acesso não autorizado.
Faça login para continuar.
```

Caso o usuário esteja autenticado, mas não seja proprietário:

```text
Você não tem permissão para acessar este arquivo.
```

---

# 10. Downloads

O cliente poderá clicar em:

**Baixar**

O sistema deverá verificar a autorização antes de iniciar o download.

Depois da autorização, o servidor poderá entregar o arquivo.

---

# 11. Nomes dos arquivos

Sempre que possível, utilizar nomes organizados.

Exemplo:

```text
dream-arte-logo-final.png
dream-arte-logo-final-transparente.png
landing-page-final.zip
posts-instagram-final.zip
```

Evitar nomes confusos como:

```text
final2.png
final-final-agora-vai.png
arquivo123.zip
```

---

# 12. Arquivos compactados

Quando houver muitos arquivos, poderá ser utilizado um arquivo ZIP.

Exemplo:

```text
Entrega Landing Page.zip

├── imagens/
├── documentos/
├── arquivos-finais/
└── instrucoes.txt
```

O formato dependerá do projeto.

---

# 13. Entrega de sites

Para serviços como:

* Landing Page
* Site institucional
* Loja Virtual

A entrega poderá ocorrer diretamente no ambiente de hospedagem do cliente.

Nesse caso, a plataforma poderá registrar:

* Data de publicação
* URL do projeto
* Informações importantes
* Arquivos complementares

Não é obrigatório que todo projeto de site seja entregue como arquivo ZIP.

---

# 14. Entrega de arquivos editáveis

Arquivos editáveis somente deverão ser entregues quando:

1. O pacote contratado incluir esse material.
2. A Dream Arte tiver direito de fornecê-lo.
3. Os recursos utilizados permitirem esse tipo de entrega.

Não entregar arquivos de terceiros que não possam ser redistribuídos.

---

# 15. Recursos de bancos de materiais

Quando forem utilizados recursos de bibliotecas como Freepik ou Envato Elements, as condições de licença deverão ser respeitadas.

A Dream Arte não deverá entregar ao cliente um arquivo original de terceiros quando a licença não permitir sua redistribuição.

Também não deverá prometer direitos que a licença não concede.

---

# 16. Licença e entrega do produto final

O produto final criado pela Dream Arte poderá ser entregue ao cliente dentro das condições permitidas pelas licenças dos recursos utilizados.

Quando necessário, as informações de licenciamento deverão ser registradas no projeto.

---

# 17. Prévia

Antes da entrega final, a Dream Arte poderá disponibilizar uma prévia.

Exemplo:

```text
Prévia disponível

Confira o projeto antes da entrega final.

[Visualizar prévia]
```

A prévia não precisa possuir os mesmos arquivos da entrega final.

---

# 18. Aprovação

Alguns projetos poderão exigir aprovação do cliente.

Exemplo:

```text
Seu projeto está pronto para aprovação.

[Ver projeto]

[Solicitar alteração]

[Aprovar]
```

Depois da aprovação, a Dream Arte poderá liberar os arquivos finais.

---

# 19. Entrega sem aprovação

Projetos que não exigirem aprovação poderão ser entregues diretamente.

Nesse caso:

```text
Projeto finalizado
↓
Entrega liberada
↓
Cliente recebe notificação
```

A necessidade de aprovação dependerá do serviço.

---

# 20. Histórico de entrega

O sistema deverá registrar informações importantes.

Exemplo:

```text
27/09/2026
Entrega criada

27/09/2026
Arquivo adicionado

27/09/2026
Entrega liberada

28/09/2026
Cliente realizou download
```

Isso ajuda a manter um histórico do projeto.

---

# 21. Registro de downloads

O sistema poderá registrar:

* Usuário
* Arquivo
* Projeto
* Data
* Hora

O objetivo é manter um histórico básico de acesso aos arquivos.

Não é necessário criar um sistema complexo de rastreamento.

---

# 22. Reenvio de entrega

Se um arquivo precisar ser substituído:

1. O administrador poderá adicionar uma nova versão.
2. A versão antiga poderá deixar de ficar disponível.
3. O novo arquivo será disponibilizado ao cliente.
4. O histórico poderá registrar a alteração.

Exemplo:

```text
Landing-page-final-v1.zip
Substituído

Landing-page-final-v2.zip
Disponível
```

---

# 23. Versões

Quando necessário, utilizar versões:

```text
v1
v2
v3
```

Isso é especialmente útil durante revisões.

A versão final deverá ser claramente identificada.

---

# 24. Arquivos enviados pelo cliente

Arquivos enviados pelo cliente também deverão ser associados ao projeto correto.

Exemplo:

```text
Projeto #203

Arquivos do cliente:
- logo.png
- fotos.zip
- textos.docx
```

Esses arquivos são diferentes dos arquivos finais produzidos pela Dream Arte.

---

# 25. Separação de arquivos

Sempre distinguir:

### Arquivos do cliente

Enviados pelo cliente para produção.

### Arquivos internos

Utilizados pela Dream Arte durante o trabalho.

### Arquivos de prévia

Utilizados para visualização/aprovação.

### Arquivos finais

Disponibilizados ao cliente após a entrega.

Essa separação evita confusão e reduz o risco de entregar arquivos internos.

---

# 26. Exclusão

Não excluir automaticamente arquivos importantes imediatamente após a entrega.

A política de retenção de arquivos deverá ser definida posteriormente.

Quando uma política de exclusão for criada, ela deverá considerar:

* Segurança
* Espaço de armazenamento
* Necessidade do cliente
* Prazo de retenção
* Possibilidade de recuperação

---

# 27. Tamanho dos arquivos

O sistema deverá possuir limites de upload adequados.

O limite poderá variar conforme:

* Tipo do arquivo
* Serviço
* Configuração do servidor
* Espaço disponível

Não assumir que qualquer tamanho de arquivo será aceito.

---

# 28. Tipos de arquivo

O sistema deverá permitir somente formatos necessários para cada serviço.

Exemplos:

### Imagens

* JPG
* JPEG
* PNG
* WebP

### Documentos

* PDF
* DOCX

### Vídeo

* MP4

### Áudio

* MP3
* WAV, quando necessário

### Compactados

* ZIP

A lista final deverá ser definida na implementação.

---

# 29. Segurança de uploads

Uploads deverão ser tratados com segurança.

O sistema deverá:

* Validar extensão
* Validar MIME type quando possível
* Limitar tamanho
* Evitar execução de arquivos perigosos
* Associar o arquivo ao projeto correto
* Impedir acesso indevido

Nunca confiar somente na extensão informada pelo navegador.

---

# 30. Entrega por link externo

Em determinados projetos, poderá ser necessário utilizar um serviço externo para arquivos muito grandes.

Nesse caso, o sistema poderá armazenar um link de entrega.

Porém, o link deverá ser protegido sempre que o serviço externo permitir.

A Dream Arte não deverá expor publicamente informações privadas do cliente.

---

# 31. Página de entrega

A página de entrega poderá apresentar:

```text
🎉 Projeto entregue!

Seu projeto está pronto.

Projeto:
Landing Page

Data da entrega:
27/09/2026

Arquivos:

┌──────────────────────────┐
│ landing-page-final.zip   │
│ 24 MB                    │
│ Arquivo final            │
│                          │
│ [Baixar]                 │
└──────────────────────────┘
```

---

# 32. Acesso posterior

Depois de receber a entrega, o cliente poderá voltar à área do cliente posteriormente.

Os arquivos continuarão associados ao projeto enquanto estiverem dentro da política de retenção definida pela Dream Arte.

---

# 33. Responsabilidade do sistema

O Dream Arte Studio Core deverá cuidar principalmente de:

* Associação arquivo → projeto
* Permissões
* Status da entrega
* Controle de acesso
* Registro de downloads
* Organização
* Interface da entrega

O armazenamento físico dos arquivos poderá utilizar a infraestrutura do WordPress ou outro sistema definido posteriormente.

---

# 34. Objetivo da experiência

Para o cliente, o processo deve ser simples:

```text
Projeto pronto
↓
Recebe aviso
↓
Abre projeto
↓
Vê arquivos
↓
Baixa
```

A complexidade de segurança e armazenamento deverá ficar no backend.

---

# 35. Regra principal

**Nenhum arquivo privado de cliente deve ficar acessível apenas por conhecer sua URL.**

Toda tentativa de acesso deverá passar pela autorização do servidor.
