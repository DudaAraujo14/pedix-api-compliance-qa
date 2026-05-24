# Evidências - Azure Boards

## Objetivo

Este documento apresenta as evidências da Parte A da entrega de **Compliance & Quality Assurance**, referente ao planejamento dos testes manuais no **Azure Boards**.

O objetivo é demonstrar que os testes foram organizados em nível de sistema, com casos planejados, dados de entrada, dados de saída esperados e procedimentos de execução.

---

## Link do Projeto no Azure Boards

```text
https://dev.azure.com/RM561052/Pedix-Compliance-QA
```

---

## Estrutura Utilizada no Azure Boards

A estrutura de QA foi organizada com os seguintes elementos:

| Item | Descrição |
|---|---|
| Test Plan | Plano principal de testes manuais do projeto Pedix |
| Test Suites | Agrupamento dos testes por funcionalidade ou fluxo do sistema |
| Test Cases | Casos de teste manuais cadastrados no Azure Boards |
| Steps | Procedimentos de execução de cada teste |
| Expected Result | Resultado esperado para cada etapa |
| Parameter Values | Dados controlados utilizados nos testes |

---

## Casos de Teste Utilizados na Demonstração

Para o vídeo de apresentação, foram selecionados testes que representam o fluxo principal da aplicação:

| ID | Caso de Teste | Objetivo |
|---|---|---|
| CT-AUTH-001 | Login do Cliente com credenciais válidas | Validar autenticação do cliente no sistema |
| CT-AUTH-002 | Login do Garçom com credenciais válidas | Validar autenticação do garçom no sistema |
| CT-PED-001 | Adicionar item ao pedido | Validar inclusão de item em um pedido |
| CT-PED-003 | Enviar pedido para a cozinha | Validar envio do pedido para preparo |
| CT000 | Validar disponibilidade da API C# | Validar se a API C# está online |

---

## Evidência 1 - Casos de Teste Cadastrados

Os casos de teste foram cadastrados no Azure Boards como **Test Cases**, seguindo o padrão de nomenclatura definido para a entrega.

Exemplos:

```text
CT-AUTH-001 - Login do Cliente com credenciais válidas
CT-AUTH-002 - Login do Garçom com credenciais válidas
CT-PED-001 - Adicionar item ao pedido
CT-PED-003 - Enviar pedido para a cozinha
CT000 - Validar disponibilidade da API C#
```

---

## Evidência 2 - Procedimentos de Teste

Cada caso de teste contém passos manuais preenchidos na aba **Steps**.

Cada step possui:

- ação que deve ser executada pelo testador;
- resultado esperado;
- dados de entrada controlados quando necessário;
- validação do comportamento esperado do sistema.

Exemplo de estrutura:

| Step | Action | Expected Result |
|---|---|---|
| 1 | Abrir o Postman | Postman carregado corretamente |
| 2 | Criar a requisição para o endpoint definido | Endpoint configurado |
| 3 | Informar os dados de entrada | Dados preenchidos corretamente |
| 4 | Clicar em Send | Requisição enviada para a API |
| 5 | Verificar o retorno | Status HTTP esperado retornado |
| 6 | Validar o corpo da resposta | Dados retornados conforme esperado |

---

## Evidência 3 - Dados Controlados

Os testes utilizaram dados controlados para garantir previsibilidade nos resultados.

Exemplos de dados utilizados:

| Funcionalidade | Dados de Entrada | Saída Esperada |
|---|---|---|
| Login Cliente | Email e senha válidos de cliente | Status 200 e token retornado |
| Login Garçom | Email e senha válidos de garçom | Status 200 e token retornado |
| Adicionar item ao pedido | ID do pedido, ID do item, quantidade e preço | Item vinculado ao pedido |
| Enviar pedido para cozinha | ID do pedido e novo status | Pedido atualizado para preparo |
| Health Check | GET `/api/health` | Status 200 e API online |

---

## Evidência 4 - Rastreabilidade com a Automação

Os casos manuais selecionados no Azure Boards também possuem equivalência com os testes automatizados no Postman.

| Azure Boards | Postman | Validação |
|---|---|---|
| CT-AUTH-001 | Login do Cliente | Status 200 e token |
| CT-AUTH-002 | Login do Garçom | Status 200 e token |
| CT-PED-001 | Adicionar item ao pedido | Status 200/201 e item criado |
| CT-PED-003 | Atualizar/Enviar pedido | Status 200 e status atualizado |
| CT000 | Health API C# | Status 200 e API online |

---

## Observação sobre Correção

Para que a correção seja possível, o professor deve possuir acesso ao projeto no Azure DevOps.

Apenas disponibilizar o link pode não ser suficiente caso o usuário não esteja como membro da organização ou do projeto.

---

## Conclusão

As evidências do Azure Boards demonstram que a Parte A da entrega foi estruturada com testes manuais planejados, contendo entrada controlada, saída esperada e procedimento de execução.

Essa organização garante rastreabilidade entre o planejamento manual, os testes automatizados no Postman e as evidências documentadas no GitHub.
