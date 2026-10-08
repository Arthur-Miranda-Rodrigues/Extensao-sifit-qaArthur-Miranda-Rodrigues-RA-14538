
---

# Cenário de teste: Gerenciamento de Aulas do SifitBox

## 1. Descrição

Este documento especifica os casos de teste referentes ao **Requisito Funcional 18 (RF18) - Aulas do SifitBox** do módulo **SifitBox > Aulas** do sistema **SiFit**. O objetivo é validar a filtragem e busca de aulas por período de datas, a geração automática de aulas e a apresentação das mensagens de retorno na ausência de registros.

---

## 2. Cenários de Teste

### Cenário 01: Operações e Gestão de Aulas do SifitBox

#### Caso de Teste 01: Filtragem e Pesquisa de Aulas por Período

| ID | Descrição |
| --- | --- |
| **C01-CT01** | Validar o funcionamento do filtro de busca de aulas informando um intervalo de datas.

 |

| **Pré-condições** |
| --- |
| Usuário autenticado no sistema SiFit e localizado na página **SifitBox - Aulas**.

 |

| **Passos** |
| --- |
| **DADO** que o usuário está na tela **SifitBox - Aulas**<br> |
| **QUANDO** alterar a data inicial do filtro de período (ex.: de "05/10/2026" para "31/07/2026")

 |
| **E** mantiver a data final (ex.: "12/10/2026")

 |
| **E** clicar no botão **Buscar**<br> |
| **ENTÃO** o sistema deve realizar a consulta referente ao período selecionado

 |
| **E** exibir a mensagem *"Nenhuma aula encontrada no período."* caso não existam aulas geradas para o intervalo.

 |

| **Critérios de Aceitação** |
| --- |
| * O seletor de datas deve permitir alterar os intervalos de início e fim.

 |
| * A busca deve atualizar a área de listagem e exibir o aviso correspondente quando não houver aulas cadastradas.

 |

---

#### Caso de Teste 02: Geração Automática de Aulas

| ID | Descrição |
| --- | --- |
| **C01-CT02** | Verificar o acionamento da funcionalidade de geração automática de aulas para o SifitBox.

 |

| **Pré-condições** |
| --- |
| Usuário autenticado na tela **SifitBox - Aulas** com permissão para gerenciar aulas.

 |

| **Passos** |
| --- |
| **DADO** que o usuário está na tela **SifitBox - Aulas**<br> |
| **QUANDO** clicar no botão **Gerar aulas** localizado no canto superior direito

 |
| **ENTÃO** o sistema deve processar a rotina de geração de aulas com base nas turmas recorrentes configuradas |
| **E** atualizar a grade com as novas aulas geradas para o período. |

| **Critérios de Aceitação** |
| --- |
| * O botão **Gerar aulas** deve disparar o processo de criação automática de aulas.

 |
| * As aulas recém-geradas devem ficar disponíveis para consulta na listagem principal após a execução. |

https://jam.dev/c/bbbf38d8-b20d-4073-878f-614fa623c189
