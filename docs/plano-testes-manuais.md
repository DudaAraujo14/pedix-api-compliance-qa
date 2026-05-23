# Plano de Testes Manuais - Pedix API

## Objetivo

Este documento resume o planejamento dos testes manuais criados no Azure Boards para validação em nível de sistema da aplicação Pedix API.

## Escopo

O plano cobre as funcionalidades principais das APIs do sistema:

- Health Check;
- Autenticação;
- Clientes;
- Mesas;
- Comandas;
- Pedidos;
- Pagamentos;
- Cardápio;
- Categorias;
- Avaliações;
- Relatórios.

---

## Casos de Teste Planejados

| ID | Funcionalidade | Teste Planejado | Entrada Controlada | Saída Esperada | Procedimento |
|---|---|---|---|---|---|
| CT-001 | Health API C# | Validar disponibilidade da API C# | GET /api/health | Status 200 e serviço UP | Executar requisição Health da API C# e validar retorno |
| CT-002 | Health API Java | Validar disponibilidade da API Java | GET /api/health | Status 200 e serviço UP | Executar requisição Health da API Java e validar retorno |
| CT-003 | Autenticação | Validar login de usuário | email: admin@pedix.com / senha: Senha@123 | Status 200 e token JWT retornado | Enviar credenciais válidas e validar token |
| CT-004 | Clientes | Listar clientes cadastrados | GET /api/clientes | Status 200 e lista de clientes | Executar listagem e validar estrutura de resposta |
| CT-005 | Mesas | Listar mesas | GET /api/Mesas | Status 200, paginação e lista de mesas | Executar listagem e validar campos obrigatórios |
| CT-006 | Comandas | Listar comandas | GET /api/Comandas | Status 200, paginação e lista de comandas | Executar listagem e validar campos obrigatórios |
| CT-007 | Pedidos | Listar pedidos | GET /api/pedidos | Status 200, paginação e lista de pedidos | Executar listagem e validar campos obrigatórios |
| CT-008 | Pagamentos | Listar pagamentos | GET /api/pagamentos | Status 200, paginação e lista de pagamentos | Executar listagem e validar campos obrigatórios |
| CT-009 | Categorias | Listar categorias do cardápio | GET /api/categorias-cardapio | Status 200 e lista de categorias | Executar listagem e validar nome da categoria |
| CT-010 | Cardápio | Listar itens do cardápio | GET /api/item-cardapio | Status 200 e lista de itens | Executar listagem e validar retorno dos itens |
| CT-011 | Avaliações | Listar avaliações | GET /api/avaliacoes | Status 200 e lista de avaliações | Executar listagem e validar nota e comentário |
| CT-012 | Relatórios | Listar relatórios | GET /api/relatorios | Status 200 e lista de relatórios | Executar listagem e validar tipo e título |

---

## Critérios de Aceite

Um caso de teste será considerado aprovado quando:

- O endpoint responder com o status HTTP esperado;
- A resposta possuir estrutura compatível com a funcionalidade testada;
- Os campos obrigatórios estiverem presentes;
- Os dados retornados forem compatíveis com a entrada controlada;
- Não ocorrer erro de execução durante o fluxo.