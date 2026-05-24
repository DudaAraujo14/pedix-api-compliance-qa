# Pedix API - Compliance & Quality Assurance

<div align="center">

# 🍽️ Pedix API

### Entrega de Compliance & Quality Assurance

Documentação, evidências e automação de testes para validação do sistema **Pedix**, uma solução backend para gerenciamento operacional de atendimentos em restaurante.

</div>

---

## 📌 Sobre o Projeto

O **Pedix API** é uma solução backend composta por duas APIs integradas, voltadas para o gerenciamento de operações em restaurante.

A aplicação contempla funcionalidades como:

- Autenticação de usuários;
- Controle de clientes;
- Gestão de mesas;
- Gestão de comandas;
- Criação e acompanhamento de pedidos;
- Itens de pedido;
- Pagamentos;
- Cardápio;
- Categorias;
- Avaliações;
- Relatórios.

Esta entrega de **Compliance & Quality Assurance** tem como objetivo documentar e evidenciar o planejamento dos testes manuais e a execução de testes automatizados da aplicação.

---

## 🎯 Objetivo da Entrega

A entrega foi organizada para atender aos requisitos obrigatórios da disciplina, contemplando:

- Plano de testes manuais no **Azure Boards**;
- Testes automatizados de API no **Postman**;
- Evidências da execução dos testes;
- Organização da documentação no **GitHub**;
- Vídeo demonstrativo da configuração e execução dos testes;
- Rastreabilidade entre testes manuais, automação e evidências.

---

## 👥 Integrantes

| Nome | RM | Responsabilidade |
|---|---:|---|
| **Maria Eduarda Araujo Penas** | RM560944 | Evidências, GitHub, README, vídeo e organização final da entrega |
| **Alane Rocha da Sila** | RM561052 | Automação de testes com Postman |
| **Anna Beatriz de Araujo Bonfim** | RM559561 | Planejamento de testes manuais no Azure Boards |

---

## 🧪 Parte A - Plano de Testes Manuais

O planejamento dos testes manuais foi realizado no **Azure Boards**, contemplando os principais fluxos de sistema da aplicação Pedix.

Foram organizados:

- **Test Plan**;
- **Test Suites**;
- **Casos de teste**;
- **Dados de entrada controlados**;
- **Dados de saída esperados**;
- **Procedimentos de execução passo a passo**.

Os testes manuais foram planejados para validar funcionalidades principais do sistema, respeitando o plano de release, as tarefas realizadas nas sprints e os principais fluxos operacionais da aplicação.

### 🔗 Link do Azure Boards

> O professor precisa estar adicionado como membro da organização/projeto no Azure DevOps para conseguir acessar e corrigir os testes manuais.

```text
https://dev.azure.com/RM561052/Pedix-Compliance-QA
```

---

## ✅ Casos de Teste Utilizados no Azure Boards

Para a demonstração da entrega, foram selecionados testes representativos do fluxo principal da aplicação, cobrindo autenticação e operação de pedidos.

| ID | Caso de Teste | Objetivo | Entrada Controlada | Saída Esperada |
|---|---|---|---|---|
| **CT-AUTH-001** | Login do Cliente com credenciais válidas | Validar autenticação de cliente no sistema | Email e senha válidos de cliente | Status HTTP 200 e token de autenticação retornado |
| **CT-AUTH-002** | Login do Garçom com credenciais válidas | Validar autenticação de garçom no sistema | Email e senha válidos de garçom | Status HTTP 200 e token de autenticação retornado |
| **CT-PED-001** | Adicionar item ao pedido | Validar inclusão de item em um pedido existente | ID do pedido, ID do item do cardápio, quantidade e preço | Item adicionado ao pedido com sucesso |
| **CT-PED-003** | Enviar pedido para a cozinha | Validar envio do pedido para fluxo de preparo | ID do pedido e alteração de status | Pedido atualizado/enviado para a cozinha |
| **CT000** | Validar disponibilidade da API C# | Validar se a API C# está online | GET `/api/health` | Status HTTP 200 e campo `status` igual a `up` |

---

## 📋 Detalhamento dos Testes Manuais

### CT-AUTH-001 - Login do Cliente com credenciais válidas

| Step | Action | Expected Result |
|---:|---|---|
| 1 | Abrir o Postman | Postman carregado corretamente |
| 2 | Criar uma requisição POST para o endpoint de login da API | Endpoint de autenticação configurado |
| 3 | Informar as credenciais válidas do cliente no Body da requisição | Email e senha preenchidos corretamente |
| 4 | Clicar em Send | Requisição enviada para a API |
| 5 | Verificar o status da resposta | API retorna Status HTTP 200 OK |
| 6 | Validar o corpo da resposta | Token de autenticação retornado |
| 7 | Confirmar o perfil do usuário autenticado | Usuário autenticado como Cliente |

---

### CT-AUTH-002 - Login do Garçom com credenciais válidas

| Step | Action | Expected Result |
|---:|---|---|
| 1 | Abrir o Postman | Postman carregado corretamente |
| 2 | Criar uma requisição POST para o endpoint de login da API | Endpoint de autenticação configurado |
| 3 | Informar as credenciais válidas do garçom no Body da requisição | Email e senha preenchidos corretamente |
| 4 | Clicar em Send | Requisição enviada para a API |
| 5 | Verificar o status da resposta | API retorna Status HTTP 200 OK |
| 6 | Validar o corpo da resposta | Token de autenticação retornado |
| 7 | Confirmar o perfil do usuário autenticado | Usuário autenticado como Garçom |

---

### CT-PED-001 - Adicionar item ao pedido

| Step | Action | Expected Result |
|---:|---|---|
| 1 | Abrir o Postman | Postman carregado corretamente |
| 2 | Selecionar a requisição de adicionar item ao pedido | Endpoint de item do pedido configurado |
| 3 | Informar o ID do pedido, ID do item do cardápio, quantidade e preço | Dados de entrada preenchidos corretamente |
| 4 | Clicar em Send | Requisição enviada para a API |
| 5 | Verificar o status da resposta | API retorna Status HTTP 200 OK ou 201 Created |
| 6 | Validar o corpo da resposta | Item adicionado ao pedido com sucesso |
| 7 | Consultar os itens do pedido | Item aparece vinculado ao pedido informado |

---

### CT-PED-003 - Enviar pedido para a cozinha

| Step | Action | Expected Result |
|---:|---|---|
| 1 | Abrir o Postman | Postman carregado corretamente |
| 2 | Selecionar a requisição de atualização/envio do pedido | Endpoint do pedido configurado |
| 3 | Informar o ID do pedido que será enviado para a cozinha | Pedido selecionado corretamente |
| 4 | Informar o novo status do pedido como enviado/em preparo | Status preenchido corretamente |
| 5 | Clicar em Send | Requisição enviada para a API |
| 6 | Verificar o status da resposta | API retorna Status HTTP 200 OK |
| 7 | Consultar o pedido atualizado | Pedido aparece com status atualizado para cozinha/em preparo |

---

### CT000 - Validar disponibilidade da API C#

| Step | Action | Expected Result |
|---:|---|---|
| 1 | Abrir o Postman | Postman carregado corretamente |
| 2 | Criar uma requisição GET para `https://pedix-api-dotnet-bge2dyd6gudpapem.brazilsouth-01.azurewebsites.net/api/health` | Endpoint configurado |
| 3 | Clicar em Send | Requisição enviada para a API |
| 4 | Verificar o retorno da resposta | Status HTTP 200 OK |
| 5 | Validar o campo `status` no JSON de resposta | Campo `status` retorna `up` |

---

## 🤖 Parte B - Testes Automatizados

A automação foi realizada utilizando **Postman**, pois o projeto é composto por APIs e serviços backend.

A collection foi organizada por módulos funcionais, contemplando:

- Health Check das APIs;
- Autenticação;
- Clientes;
- Mesas;
- Comandas;
- Pedidos;
- Itens de pedido;
- Pagamentos;
- Categorias;
- Cardápio;
- Avaliações;
- Relatórios.

Os testes automatizados validam:

- Status HTTP esperado;
- Retorno de dados;
- Estrutura JSON;
- Campos obrigatórios;
- Tempo de resposta;
- Disponibilidade dos serviços.

---

## 🧾 Testes Realizados no Postman

| Módulo | Requisição | Método | Endpoint | Validações |
|---|---|---:|---|---|
| **Health** | Health API C# | GET | `/api/health` | Status 200 e API online |
| **Health** | Health API Java | GET | `/api/health` | Status 200 e API online |
| **Auth** | Login | POST | `/api/auth/login` | Status 200, token JWT existente e token não vazio |
| **Clientes** | Listar Clientes | GET | `/api/clientes` | Status 200, lista retornada e estrutura de dados |
| **Mesas** | Listar Mesas | GET | `/api/Mesas` | Status 200, paginação, lista e campos obrigatórios |
| **Comandas** | Listar Comandas | GET | `/api/Comandas` | Status 200, paginação, lista e campos obrigatórios |
| **Pedidos** | Listar Pedidos | GET | `/api/pedidos` | Status 200, paginação, lista e campos obrigatórios |
| **Pedidos** | Atualizar Status do Pedido | PUT | `/api/pedidos/{id}/status` | Status 200 e alteração de status |
| **Pedido Itens** | Adicionar Item ao Pedido | POST | `/api/pedido-itens` | Status 200/201 e item vinculado ao pedido |
| **Pagamentos** | Listar Pagamentos | GET | `/api/pagamentos` | Status 200, paginação, lista e campos obrigatórios |
| **Categorias** | Listar Categorias | GET | `/api/categorias-cardapio` | Status 200, lista retornada e nome da categoria |
| **Categorias** | Criar Categoria | POST | `/api/categorias-cardapio` | Status 200/201, ID retornado e nome validado |
| **Cardápio** | Listar Itens Cardápio | GET | `/api/item-cardapio` | Status 200 e lista retornada |
| **Avaliações** | Listar Avaliações | GET | `/api/avaliacoes` | Status 200, nota válida e comentário retornado |
| **Relatórios** | Listar Relatórios | GET | `/api/relatorios` | Status 200, tipo e título retornados |

---

## 🧪 Exemplo de Script de Validação no Postman

```javascript
pm.test("API online", function () {
    pm.response.to.have.status(200);
});

pm.test("Resposta possui status UP", function () {
    const jsonData = pm.response.json();
    pm.expect(jsonData.status.toLowerCase()).to.eql("up");
});
```

Outro exemplo utilizado para autenticação:

```javascript
pm.test("Login realizado com sucesso", function () {
    pm.response.to.have.status(200);
});

pm.test("Token JWT retornado", function () {
    const jsonData = pm.response.json();
    pm.expect(jsonData.token).to.exist;
});

pm.test("Token não está vazio", function () {
    const jsonData = pm.response.json();
    pm.expect(jsonData.token).to.not.be.empty;
});
```

---

## 🛠️ Tecnologias Utilizadas

<div align="center">

| Tecnologia | Uso no Projeto |
|---|---|
| ![Azure Boards](https://img.shields.io/badge/Azure%20Boards-0078D4?style=for-the-badge&logo=azuredevops&logoColor=white) | Planejamento e registro dos testes manuais |
| ![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white) | Versionamento e entrega do repositório |
| ![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white) | Automação e execução dos testes de API |
| ![Azure](https://img.shields.io/badge/Azure%20App%20Service-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white) | Hospedagem das APIs |
| ![.NET](https://img.shields.io/badge/.NET%208-512BD4?style=for-the-badge&logo=dotnet&logoColor=white) | API primária em C# |
| ![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white) | API secundária |
| ![Spring Boot](https://img.shields.io/badge/Spring%20Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white) | Estrutura da API Java |
| ![Oracle](https://img.shields.io/badge/Oracle-F80000?style=for-the-badge&logo=oracle&logoColor=white) | Banco de dados relacional |
| ![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white) | Banco de dados NoSQL |
| ![JSON](https://img.shields.io/badge/JSON-000000?style=for-the-badge&logo=json&logoColor=white) | Formato de troca de dados |
| ![REST API](https://img.shields.io/badge/REST%20API-02569B?style=for-the-badge) | Comunicação entre cliente e backend |

</div>

---

## 🌐 APIs Publicadas

### API C# - Primária

```text
https://pedix-api-dotnet-bge2dyd6gudpapem.brazilsouth-01.azurewebsites.net
```

Health Check:

```text
https://pedix-api-dotnet-bge2dyd6gudpapem.brazilsouth-01.azurewebsites.net/api/health
```

---

### API Java - Secundária

```text
https://pedix-api-aab0evapangybdh7.eastus-01.azurewebsites.net
```

Health Check:

```text
https://pedix-api-aab0evapangybdh7.eastus-01.azurewebsites.net/api/health
```

---

## 📁 Estrutura do Repositório

```text
pedix-api-compliance-qa
├── README.md
├── docs
│   ├── evidencias-azure-boards.md
│   ├── plano-testes-manuais.md
│   └── roteiro-video.md
├── postman
│   ├── Pedix API - QA.postman_collection.json
│   └── Pedix APIs.postman_environment.json
├── prints
│   ├── collections-organizadas.png
│   ├── health-dotnet-api.png
│   ├── health-java-api.png
│   └── runner-execucao-testes.png
└── video
    └── link-video.txt
```

---

## ▶️ Como Executar os Testes Automatizados

1. Abrir o **Postman**.
2. Importar a collection localizada em:

```text
postman/Pedix API - QA.postman_collection.json
```

3. Importar o environment localizado em:

```text
postman/Pedix APIs.postman_environment.json
```

4. Selecionar o environment:

```text
Pedix APIs
```

5. Conferir as variáveis de ambiente:

```text
javaBaseUrl
 dotnetBaseUrl
```

6. Abrir o **Postman Runner**.
7. Selecionar a collection **Pedix API - QA**.
8. Executar os testes.
9. Validar se os testes retornam sucesso.

---

## 🖼️ Evidências da Automação

### Collection organizada no Postman

![Collection organizada](prints/collections-organizadas.png)

### Health Check da API C#

![Health C#](prints/health-dotnet-api.png)

### Health Check da API Java

![Health Java](prints/health-java-api.png)

### Execução pelo Postman Runner

![Runner Postman](prints/runner-execucao-testes.png)

---

## 🎥 Vídeo de Demonstração

O vídeo apresenta:

- Organização do repositório GitHub;
- Estrutura da branch `develop`;
- Link e estrutura do Azure Boards;
- Casos de teste manuais selecionados;
- Collection Postman;
- Environment utilizado;
- Scripts de validação;
- Execução automatizada dos testes;
- Evidências dos testes passando.

Link do vídeo:

```text
COLE_AQUI_O_LINK_DO_VIDEO
```

---

## ✅ Critérios de Validação

A entrega atende aos seguintes critérios:

- Testes manuais planejados no Azure Boards;
- Testes com dados de entrada controlados;
- Saídas esperadas documentadas;
- Procedimentos de teste descritos passo a passo;
- Automação de testes de API com Postman;
- Mais de quatro casos automatizados;
- Evidências visuais da execução;
- Repositório organizado na branch `develop`;
- Vídeo demonstrativo da configuração e execução.

---

## 🏁 Conclusão

A entrega contempla os requisitos obrigatórios de **Compliance & Quality Assurance**, incluindo o planejamento de testes manuais no **Azure Boards**, a automação dos testes com **Postman**, as evidências da execução e a documentação organizada no **GitHub**.

O repositório foi estruturado para garantir clareza, rastreabilidade e facilidade de correção, conectando os testes manuais, a automação e as evidências em uma entrega única e profissional.

