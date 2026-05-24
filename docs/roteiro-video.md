# Roteiro do Vídeo - Compliance & Quality Assurance

## Objetivo do Vídeo

Este roteiro orienta a gravação do vídeo demonstrativo da entrega de **Compliance & Quality Assurance** do projeto **Pedix API**.

O vídeo deve mostrar:

- organização do repositório GitHub;
- branch `develop`;
- documentação da entrega;
- Azure Boards com testes manuais;
- Postman com collection, environment e scripts;
- execução dos testes automatizados;
- evidências dos testes passando.

---

## Duração Recomendada

O vídeo pode ter entre **4 e 7 minutos**.

Não é necessário mostrar todos os testes. O ideal é demonstrar os principais fluxos de forma clara e objetiva.

---

## 1. Abertura

Fala sugerida:

> Olá, professor. Este vídeo apresenta a entrega de Compliance & Quality Assurance do projeto Pedix API.  
> A entrega contempla o plano de testes manuais no Azure Boards, os testes automatizados no Postman e a organização das evidências no GitHub, conforme solicitado no enunciado.

---

## 2. Explicação Rápida do Projeto

Fala sugerida:

> O Pedix é um sistema voltado para atendimento em restaurante, com funcionalidades como autenticação de usuários, cardápio, pedidos, mesas, comandas, pagamentos e acompanhamento de status do pedido.

---

## 3. Mostrar o GitHub

Acessar o repositório no GitHub e mostrar a branch `develop`.

Itens para mostrar:

- `README.md`;
- pasta `docs`;
- pasta `postman`;
- pasta `prints`;
- pasta `video`.

Fala sugerida:

> O repositório foi organizado na branch develop, conforme exigido na entrega.  
> Aqui temos o README com a descrição do projeto, os integrantes, o link do Azure Boards, a explicação dos testes automatizados, as evidências e o link do vídeo.  
> Também foram separadas as pastas docs, postman, prints e video para facilitar a correção.

---

## 4. Mostrar o README

Mostrar rapidamente as seções principais:

- Sobre o projeto;
- Integrantes;
- Parte A - Plano de testes manuais;
- Parte B - Testes automatizados;
- Tecnologias utilizadas;
- APIs publicadas;
- Evidências;
- Link do vídeo.

Fala sugerida:

> O README centraliza as informações principais da entrega, incluindo o link do Azure Boards, os testes utilizados, as tecnologias e as evidências de execução.

---

## 5. Mostrar o Azure Boards

Acessar o projeto:

```text
https://dev.azure.com/RM561052/Pedix-Compliance-QA
```

Mostrar os casos de teste escolhidos:

```text
CT-AUTH-001 - Login do Cliente com credenciais válidas
CT-AUTH-002 - Login do Garçom com credenciais válidas
CT-PED-001 - Adicionar item ao pedido
CT-PED-003 - Enviar pedido para a cozinha
CT000 - Validar disponibilidade da API C#
```

Fala sugerida:

> Na Parte A, os testes manuais foram cadastrados no Azure Boards.  
> Cada caso de teste possui passos de execução, dados de entrada e resultado esperado.  
> Para a demonstração, escolhemos casos que representam o fluxo principal da aplicação: login do cliente, login do garçom, adicionar item ao pedido e enviar pedido para a cozinha.

---

## 6. Explicar Action e Expected Result

Abrir um caso de teste e mostrar a aba **Steps**.

Fala sugerida:

> Aqui podemos ver o procedimento manual do teste.  
> Na coluna Action estão os passos que o testador deve executar.  
> Na coluna Expected Result está o resultado esperado para cada etapa.  
> Dessa forma, o teste fica padronizado e pode ser reproduzido por outra pessoa.

---

## 7. Explicar Por Que Esses Testes Foram Escolhidos

Fala sugerida:

> Esses testes foram escolhidos porque representam o fluxo principal da aplicação.  
> Primeiro o usuário acessa o sistema, depois o pedido é montado com itens e, por fim, o pedido é enviado para a cozinha.  
> Assim conseguimos validar autenticação, operação do pedido e mudança de status dentro do sistema.

---

## 8. Mostrar o Postman

Abrir o Postman e mostrar a collection:

```text
Pedix API - QA
```

Mostrar a organização:

```text
01 - Health
02 - C# | API Primária - Fluxo Operacional
03 - JAVA | API Secundária - Suporte e Gestão
```

Fala sugerida:

> Na Parte B, a automação foi feita no Postman, porque o projeto é composto por APIs.  
> A collection foi organizada por módulos, separando Health Check, API C# primária e API Java secundária.

---

## 9. Mostrar o Environment

Mostrar o environment:

```text
Pedix APIs
```

Variáveis importantes:

```text
dotnetBaseUrl
javaBaseUrl
```

Fala sugerida:

> O environment Pedix APIs centraliza as URLs publicadas no Azure.  
> Assim, as requisições usam variáveis como dotnetBaseUrl e javaBaseUrl, evitando repetir a URL manualmente em cada endpoint.

---

## 10. Mostrar os Scripts de Validação

Abrir uma requisição que tenha scripts de teste.

Fala sugerida:

> Em cada requisição automatizada foram adicionadas validações usando scripts do Postman.  
> Esses scripts verificam, por exemplo, se o status HTTP está correto, se o JSON retornou os campos esperados e se o tempo de resposta está adequado.

Exemplo de validação:

```javascript
pm.test("Status code é 200", function () {
    pm.response.to.have.status(200);
});
```

---

## 11. Executar o Runner

Abrir o Runner do Postman, selecionar a collection e o environment.

Fala sugerida antes da execução:

> Agora estou executando a collection pelo Runner do Postman.  
> O objetivo é validar de forma automatizada os endpoints principais do sistema.

Após finalizar:

> A execução foi concluída com os testes aprovados.  
> Aqui conseguimos visualizar a quantidade de testes executados, os testes que passaram, a ausência de falhas e o tempo médio de resposta.

---

## 12. Mostrar as Evidências no GitHub

Voltar ao GitHub e mostrar a pasta `prints`.

Fala sugerida:

> Além da execução no Postman, também foram adicionadas evidências visuais no repositório, como prints da collection, health checks e execução do Runner.

---

## 13. Encerramento

Fala sugerida:

> Com isso, a entrega atende aos requisitos obrigatórios da atividade: plano de testes manuais no Azure Boards, testes automatizados no Postman, evidências organizadas no GitHub e vídeo demonstrativo da configuração e execução.  
> O professor também terá acesso ao link do Azure Boards e ao repositório na branch develop para correção.

Frase final opcional:

> A entrega está organizada para garantir rastreabilidade entre os testes manuais, a automação no Postman e as evidências versionadas no GitHub.

---

## Checklist Antes de Gravar

| Item | Conferido |
|---|---|
| GitHub aberto na branch develop | ☐ |
| README atualizado | ☐ |
| Azure Boards aberto | ☐ |
| Casos de teste preenchidos | ☐ |
| Postman aberto | ☐ |
| Environment selecionado | ☐ |
| Collection funcionando | ☐ |
| Runner pronto para executar | ☐ |
| Microfone testado | ☐ |
| Vídeo de teste de 20 segundos realizado | ☐ |

---

## Checklist Depois de Gravar

| Item | Conferido |
|---|---|
| Vídeo salvo corretamente | ☐ |
| Áudio funcionando | ☐ |
| Vídeo enviado ao YouTube ou Drive | ☐ |
| Link configurado como público ou não listado | ☐ |
| Link adicionado no README | ☐ |
| Link adicionado em `video/link-video.txt` | ☐ |
| Alterações commitadas na branch develop | ☐ |
| Link final da branch develop entregue | ☐ |