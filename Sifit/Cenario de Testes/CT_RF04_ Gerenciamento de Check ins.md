

# Cenário de Testes: Gerenciamento de Check-ins (RF04)

**Descrição:** Validação do módulo de gerenciamento de check-ins, englobando a navegação entre unidades, realização de entrada manual de alunos, tratamento de exceções no check-in por código/biometria e navegação entre abas de status.

---

## Caso de Teste 01: Seleção e Troca de Unidade Operacional

| ID | Descrição |
| --- | --- |
| RF04-CT01 | Verificar a alternância de dados e métricas ao selecionar diferentes unidades no cabeçalho superior. |

| **Pré-condições** |
| --- |
| Usuário autenticado na plataforma com acesso a múltiplas unidades. |

| **Passos** |
| --- |
| **DADO** que o usuário está logado e acessa o menu lateral "Check-in"<br>

<br>

<br>**QUANDO** clicar no seletor de unidade localizado no topo da tela (ex: "Unidade Centro")<br>

<br>

<br>**E** selecionar outra unidade disponível (ex: "Unidade Sul" ou "Unidade Norte")<br>

<br>

<br>**ENTÃO** os dados de métricas (Check-ins hoje, Presentes agora, Meta do dia, Média diária) e a listagem de clientes devem atualizar de acordo com a unidade selecionada. |

| **Critérios de aceitação** |
| --- |
| As métricas e a tabela de clientes devem refletir exclusivamente as informações relativas à unidade recém-selecionada. |

---

## Caso de Teste 02: Registro de Entrada Manual de Cliente

| ID | Descrição |
| --- | --- |
| RF04-CT02 | Confirmar o registro manual de presença para alunos através da busca por nome, código ou CPF. |

| **Pré-condições** |
| --- |
| Cliente cadastrado e ativo no sistema. |

| **Passos** |
| --- |
| **DADO** que o usuário está na tela de Check-ins<br>

<br>

<br>**QUANDO** clicar no botão "+ Check-in manual"<br>

<br>

<br>**E** selecionar a aba "Cliente existente" no modal "Entrada manual"<br>

<br>

<br>**E** digitar o nome, CPF ou código do cliente no campo de busca (ex: "Rodolfo")<br>

<br>

<br>**E** confirmar os dados exibidos no resultado do cliente encontrado<br>

<br>

<br>**E** clicar em "Registrar entrada"<br>

<br>

<br>**ENTÃO** o registro deve ser processado com sucesso e o cliente deve passar a ser listado na tabela de check-ins da página principal com status "Pendente" ou "Ativo". |

| **Critérios de aceitação** |
| --- |
| O sistema deve validar a busca do cliente e salvar o registro manual de entrada na lista principal com o status correspondente. |

---

## Caso de Teste 03: Entrada Rápida com Código Inválido / Não Encontrado

| ID | Descrição |
| --- | --- |
| RF04-CT03 | Validar a mensagem de erro ao tentar realizar o check-in rápido utilizando um código ou biometria não associado à empresa/unidade. |

| **Pré-condições** |
| --- |
| Estar na tela inicial do módulo de Check-ins. |

| **Passos** |
| --- |
| **DADO** que o usuário está no painel lateral de Entrada rápida<br>

<br>

<br>**QUANDO** inserir no campo "Código do cliente" um número de biometria ou identificador cadastrado em outra unidade ou inexistente (ex: 123456)<br>

<br>

<br>**E** clicar no botão "Realizar check-in"<br>

<br>

<br>**ENTÃO** o sistema deve exibir um modal de alerta com a mensagem: "Não foi possível concluir - Cliente não encontrado para esta empresa." |

| **Critérios de aceitação** |
| --- |
| A tentativa de check-in com identificador inválido/não pertencente à unidade deve ser bloqueada e notificada adequadamente. |

---

## Caso de Teste 04: Filtro por Abas de Status de Presença

| ID | Descrição |
| --- | --- |
| RF04-CT04 | Validar a filtragem dos registros através das abas de navegação da listagem principal. |

| **Pré-condições** |
| --- |
| Existirem registros com diferentes estados de presença cadastrados no dia. |

| **Passos** |
| --- |
| **DADO** que o usuário está na tela de Check-ins<br>

<br>

<br>**QUANDO** alternar entre as abas de navegação ("Todos", "Presentes agora", "Não compareceram" e "Check-in pendente")<br>

<br>

<br>**ENTÃO** a tabela de resultados deve recarregar e exibir exclusivamente os registros correspondentes ao filtro/aba selecionado. |

| **Critérios de aceitação** |
| --- |
| Os dados exibidos na tabela devem respeitar estritamente o filtro de status da aba ativa. |
https://jam.dev/c/014ff3c9-66c7-4a8d-9d1d-488ef529f977 
