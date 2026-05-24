# Plano de Testes Manuais - Pedix API

## Objetivo

Este documento descreve o plano de testes manuais da aplicação **Pedix API**, elaborado para validação em nível de sistema.

O plano atende à Parte A da entrega de **Compliance & Quality Assurance**, cobrindo as funcionalidades principais do sistema com dados de entrada controlados, saídas esperadas e procedimentos de execução.

---

## Escopo dos Testes

Os testes manuais contemplam os principais fluxos funcionais da aplicação:

- autenticação de usuários;
- login por perfil;
- consulta de cardápio;
- criação e manipulação de pedidos;
- envio de pedidos para a cozinha;
- atualização de status;
- atendimento por garçom;
- comandas;
- pagamentos;
- health check da API.

---

## Ambiente de Teste

| Item | Descrição |
|---|---|
| Plataforma de gestão | Azure Boards |
| Ferramenta de apoio | Postman |
| API principal | Pedix API C# |
| API secundária | Pedix API Java |
| Ambiente | Azure App Service |
| Tipo de teste | Manual, funcional e sistêmico |

---

## APIs Utilizadas

### API C# - Primária

```text
https://pedix-api-dotnet-bge2dyd6gudpapem.brazilsouth-01.azurewebsites.net
```

### API Java - Secundária

```text
https://pedix-api-aab0evapangybdh7.eastus-01.azurewebsites.net
```

---

## Critérios de Aceite Gerais

Um teste será considerado aprovado quando:

- o endpoint responder com o status HTTP esperado;
- os dados retornados forem compatíveis com a entrada informada;
- o corpo da resposta estiver no formato esperado;
- os campos obrigatórios estiverem presentes;
- o fluxo funcional for concluído sem erro;
- o comportamento observado for igual ao resultado esperado no Azure Boards.

---

## Casos de Teste Manuais

### CT000 - Validar disponibilidade da API C#

| Campo | Descrição |
|---|---|
| Funcionalidade | Health Check |
| Objetivo | Validar se a API C# está online |
| Método | GET |
| Endpoint | `/api/health` |
| Entrada | Nenhuma |
| Saída esperada | Status HTTP 200 e campo `status` igual a `up` |

| Step | Action | Expected Result |
|---|---|---|
| 1 | Abrir o Postman | Postman carregado corretamente |
| 2 | Criar uma requisição GET para `https://pedix-api-dotnet-bge2dyd6gudpapem.brazilsouth-01.azurewebsites.net/api/health` | Endpoint configurado |
| 3 | Clicar em Send | Requisição enviada para a API |
| 4 | Verificar o retorno da resposta | Status HTTP 200 OK |
| 5 | Validar o campo `status` no JSON de resposta | Campo `status` retorna `up` |

---

### CT-AUTH-001 - Login do Cliente com credenciais válidas

| Campo | Descrição |
|---|---|
| Funcionalidade | Autenticação |
| Objetivo | Validar login de cliente com credenciais válidas |
| Método | POST |
| Endpoint | `/api/auth/login` |
| Entrada | Email e senha de cliente |
| Saída esperada | Status HTTP 200 e token de autenticação retornado |

| Step | Action | Expected Result |
|---|---|---|
| 1 | Abrir o Postman | Postman carregado corretamente |
| 2 | Criar uma requisição POST para o endpoint de login | Endpoint de autenticação configurado |
| 3 | Acessar a aba Body, selecionar raw e JSON | Corpo da requisição preparado |
| 4 | Informar as credenciais válidas do cliente | Email e senha preenchidos corretamente |
| 5 | Clicar em Send | Requisição enviada para a API |
| 6 | Verificar o status da resposta | API retorna Status HTTP 200 OK |
| 7 | Validar o corpo da resposta | Token de autenticação retornado |
| 8 | Confirmar o perfil do usuário autenticado | Usuário autenticado como Cliente |

---

### CT-AUTH-002 - Login do Garçom com credenciais válidas

| Campo | Descrição |
|---|---|
| Funcionalidade | Autenticação |
| Objetivo | Validar login de garçom com credenciais válidas |
| Método | POST |
| Endpoint | `/api/auth/login` |
| Entrada | Email e senha de garçom |
| Saída esperada | Status HTTP 200 e token de autenticação retornado |

| Step | Action | Expected Result |
|---|---|---|
| 1 | Abrir o Postman | Postman carregado corretamente |
| 2 | Criar uma requisição POST para o endpoint de login | Endpoint de autenticação configurado |
| 3 | Acessar a aba Body, selecionar raw e JSON | Corpo da requisição preparado |
| 4 | Informar as credenciais válidas do garçom | Email e senha preenchidos corretamente |
| 5 | Clicar em Send | Requisição enviada para a API |
| 6 | Verificar o status da resposta | API retorna Status HTTP 200 OK |
| 7 | Validar o corpo da resposta | Token de autenticação retornado |
| 8 | Confirmar o perfil do usuário autenticado | Usuário autenticado como Garçom |

---

### CT-PED-001 - Adicionar item ao pedido

| Campo | Descrição |
|---|---|
| Funcionalidade | Pedido |
| Objetivo | Validar inclusão de item em um pedido |
| Método | POST |
| Endpoint | `/api/pedido-itens` |
| Entrada | ID do pedido, ID do item, quantidade e preço |
| Saída esperada | Status HTTP 200/201 e item vinculado ao pedido |

| Step | Action | Expected Result |
|---|---|---|
| 1 | Abrir o Postman | Postman carregado corretamente |
| 2 | Selecionar a requisição de adicionar item ao pedido | Endpoint de item do pedido configurado |
| 3 | Informar o ID do pedido, ID do item do cardápio, quantidade e preço | Dados de entrada preenchidos corretamente |
| 4 | Clicar em Send | Requisição enviada para a API |
| 5 | Verificar o status da resposta | API retorna Status HTTP 200 OK ou 201 Created |
| 6 | Validar o corpo da resposta | Item adicionado ao pedido com sucesso |
| 7 | Consultar os itens do pedido | Item aparece vinculado ao pedido informado |

---

### CT-PED-003 - Enviar pedido para a cozinha

| Campo | Descrição |
|---|---|
| Funcionalidade | Pedido |
| Objetivo | Validar envio do pedido para a cozinha |
| Método | PUT |
| Endpoint | Endpoint de atualização/status do pedido |
| Entrada | ID do pedido e novo status |
| Saída esperada | Status HTTP 200 e pedido atualizado |

| Step | Action | Expected Result |
|---|---|---|
| 1 | Abrir o Postman | Postman carregado corretamente |
| 2 | Selecionar a requisição de atualização ou envio do pedido | Endpoint do pedido configurado |
| 3 | Informar o ID do pedido que será enviado para a cozinha | Pedido selecionado corretamente |
| 4 | Informar o novo status do pedido como enviado ou em preparo | Status preenchido corretamente |
| 5 | Clicar em Send | Requisição enviada para a API |
| 6 | Verificar o status da resposta | API retorna Status HTTP 200 OK |
| 7 | Consultar o pedido atualizado | Pedido aparece com status atualizado para cozinha ou preparo |

---

## Dados de Entrada Controlados

Os dados utilizados devem ser previamente definidos para evitar variação no resultado dos testes.

| Dado | Exemplo |
|---|---|
| Email cliente | Cliente previamente cadastrado na base |
| Email garçom | Garçom previamente cadastrado na base |
| Senha | Senha válida para o usuário |
| Pedido ID | Pedido existente ou criado durante o teste |
| Item Cardápio ID | Item existente no cardápio |
| Quantidade | 1 |
| Status Pedido | Em Preparo / Pronto / Enviado |

---

## Riscos e Observações

| Risco | Impacto | Mitigação |
|---|---|---|
| Dados inexistentes na base | Teste pode falhar | Utilizar dados controlados e previamente cadastrados |
| API fora do ar | Health Check falha | Validar disponibilidade antes da execução |
| Token expirado | Endpoints autenticados podem falhar | Realizar novo login antes dos testes |
| Mudança de status inválida | API pode recusar atualização | Utilizar status aceitos pelo backend |

---

## Conclusão

O plano de testes manuais cobre os fluxos essenciais da aplicação Pedix API e permite validar o comportamento do sistema de ponta a ponta.

Os casos selecionados para demonstração representam autenticação, operação de pedido e avanço do fluxo operacional do restaurante.
