# Pedix API - Compliance & Quality Assurance

## Sobre o Projeto

O projeto Pedix API é uma solução backend composta por duas APIs integradas, voltadas para o gerenciamento operacional de atendimentos em restaurante.

A aplicação contempla funcionalidades como autenticação, clientes, mesas, comandas, pedidos, itens de pedido, pagamentos, cardápio, categorias, avaliações e relatórios.

Esta entrega de Compliance & Quality Assurance documenta e evidencia:

- Plano de testes manuais no Azure Boards;
- Testes automatizados de API no Postman;
- Evidências da execução dos testes;
- Organização da entrega no GitHub;
- Vídeo demonstrativo da configuração e execução.

---

## Integrantes

| Nome | RM | Responsabilidade |
|---|---|---|
| Maria Eduarda Araujo Penas | RM560944 | Evidências, GitHub, README, vídeo e organização final da entrega |
| Alane Rocha da Sila | RM561052 | Automação de testes com Postman |
| Anna Beatriz de Araujo Bonfim | RM559561 | Planejamento de testes manuais no Azure Boards |

---

## Parte A - Plano de Testes Manuais

O planejamento dos testes manuais foi realizado no Azure Boards, contemplando os principais fluxos do sistema.

Foram organizados:

- Test Plan;
- Test Suites;
- Casos de teste;
- Dados de entrada controlados;
- Dados de saída esperados;
- Procedimentos de execução passo a passo.

Os testes manuais foram planejados para validar as funcionalidades principais do sistema, de acordo com as tarefas e entregas realizadas durante as sprints.

### Link do Azure Boards

> O professor precisa estar adicionado como membro da organização/projeto no Azure DevOps para conseguir acessar e corrigir os testes.

https://dev.azure.com/RM561052/Pedix-Compliance-QA

---

## Parte B - Testes Automatizados

A automação foi realizada utilizando Postman, pois o projeto é composto por APIs e serviços backend.

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

## Tecnologias Utilizadas

- Azure Boards
- GitHub
- Postman
- Azure App Service
- .NET 8 / ASP.NET Core Web API
- Java / Spring Boot
- Oracle Database
- MongoDB
- REST API
- JSON

---

## APIs Publicadas

### API C# - Primária

```text
https://pedix-api-dotnet-bge2dyd6gudpapem.brazilsouth-01.azurewebsites.net
```
---

### API JAVA - Secundária

```text
https://pedix-api-aab0evapangybdh7.eastus-01.azurewebsites.net
```