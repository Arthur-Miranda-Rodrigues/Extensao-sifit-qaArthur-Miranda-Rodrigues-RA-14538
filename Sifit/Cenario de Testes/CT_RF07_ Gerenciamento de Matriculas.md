
---

# Cenário de Testes: Gerenciamento de Matrículas (RF05)

**Descrição:** Validação do módulo de gerenciamento de matrículas na operação da academia, englobando consultas por código e período, cadastro com validações de campos obrigatórios, edição de observações e tratamento de falhas na exclusão do registro.

---

## Caso de Teste 01: Visualização e Edição de Observação da Matrícula

| ID | Descrição |
| --- | --- |
| RF05-CT01 | Verificar se é possível abrir os detalhes de uma matrícula existente, alterar o campo de observação e salvar as alterações. |

| **Pré-condições** |
| --- |
| Estar autenticado no sistema SIFIT e navegar até a tela de Matrículas. |

| **Passos** |
| --- |
| **DADO** que o usuário acessa o menu "Operação da Academia > Matrículas"<br>

<br>

<br>**QUANDO** localizar a matrícula com código 237 (Cliente: Rafaela Andrade) e clicar no ícone de visualização/edição<br>

<br>

<br>**E** habilitar o modo de edição no modal "Visualizar Matrícula"<br>

<br>

<br>**E** digitar "lesão" no campo "Observação"<br>

<br>

<br>**E** clicar em "Salvar" e, em seguida, em "Fechar"<br>

<br>

<br>**ENTÃO** o modal deve permitir a atualização da observação e manter as alterações salvas ao retornar à listagem. |

| **Critérios de aceitação** |
| --- |
| A alteração do campo "Observação" deve ser persistida com sucesso e refletida nos detalhes do registro. |

---

## Caso de Teste 02: Pesquisa de Matrícula por Código

| ID | Descrição |
| --- | --- |
| RF05-CT02 | Validar a funcionalidade de filtro da listagem de matrículas utilizando o código do registro. |

| **Pré-condições** |
| --- |
| Estar autenticado no sistema SIFIT e na tela de Matrículas. |

| **Passos** |
| --- |
| **DADO** que o usuário está na tela de Matrículas<br>

<br>

<br>**QUANDO** introduzir o valor "239" no campo "Código"<br>

<br>

<br>**E** clicar no botão "Buscar"<br>

<br>

<br>**ENTÃO** a tabela deve filtrar e exibir apenas a matrícula correspondente ao código 239 (Cliente: Marcelo Zand). |

| **Critérios de aceitação** |
| --- |
| O filtro por código deve retornar exclusivamente o registro exato correspondente ao termo pesquisado. |

---

## Caso de Teste 03: Validação de Obrigatoriedade de Cliente ao Cadastrar Matrícula

| ID | Descrição |
| --- | --- |
| RF05-CT03 | Garantir que o sistema não permita salvar uma nova matrícula sem selecionar um cliente associado. |

| **Pré-condições** |
| --- |
| Estar na tela de Matrículas do SIFIT. |

| **Passos** |
| --- |
| **DADO** que o usuário clica no botão "Cadastrar Matrícula"<br>

<br>

<br>**QUANDO** preencher os campos obrigatórios de pagamento, valores e datas (Taxa de Matrícula: 30, Valor Parcela: 150,00, Desconto: 30, Valor Total: 120,00, Observação: "Exercícios")<br>

<br>

<br>**E** deixar o campo "Cliente / Código" em branco<br>

<br>

<br>**E** clicar no botão "Salvar"<br>

<br>

<br>**ENTÃO** o sistema deve interromper a gravação e exibir o modal de alerta: "Aviso: Selecione o cliente!". |

| **Critérios de aceitação** |
| --- |
| A tentativa de salvar uma matrícula sem cliente deve ser bloqueada, exibindo mensagem de aviso apropriada. |

---

## Caso de Teste 04: Filtro de Matrículas por Período de Datas

| ID | Descrição |
| --- | --- |
| RF05-CT04 | Testar a filtragem das matrículas com base em um intervalo personalizado de Data Inicial e Data Final. |

| **Pré-condições** |
| --- |
| Existirem registros de matrículas cadastrados em diferentes datas. |

| **Passos** |
| --- |
| **DADO** que o usuário está na tela principal de Matrículas<br>

<br>

<br>**QUANDO** abrir os filtros avançados de data<br>

<br>

<br>**E** definir a Data Inicial como "02/06/2026" e a Data Final como "30/09/2026"<br>

<br>

<br>**E** clicar no botão "Buscar"<br>

<br>

<br>**ENTÃO** a listagem deve recarregar e apresentar apenas os registros cujas datas estejam estritamente dentro do período especificado. |

| **Critérios de aceitação** |
| --- |
| A tabela de matrículas deve atualizar exibindo somente as matrículas compreendidas no intervalo selecionado. |

---

## Caso de Teste 05: Exclusão de Matrícula do Sistema (Validação de Falha/Bug)

| ID | Descrição |
| --- | --- |
| RF05-CT05 | Validar a funcionalidade de remoção/cancelamento de uma matrícula através do ícone de lixeira na listagem e tratar erros de servidor. |

| **Pré-condições** |
| --- |
| Existir uma matrícula ativa cadastrada na tabela (ex.: Código 241 ou 240). |

| **Passos** |
| --- |
| **DADO** que o usuário localiza uma matrícula ativa na tabela<br>

<br>

<br>**QUANDO** clicar no ícone de Lixeira ("Excluir") na linha do registro<br>

<br>

<br>**E** confirmar a ação no modal de confirmação clicando em "Confirmar"<br>

<br>

<br>**ENTÃO** o sistema deve processar a exclusão ou tratar a falha capturada exibindo a mensagem "Erro no servidor - Erro interno inesperado". |

| **Critérios de aceitação** |
| --- |
| A exclusão deve ser finalizada no banco de dados ou, no caso de exceção de backend, reportada claramente via modal de erro ao usuário. |

https://jam.dev/c/ae4c0d91-1381-4ac0-8558-b009894c4724 
