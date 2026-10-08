
---

## Cenário de teste: Consulta e Filtragem de Presenças de Clientes

### Caso de Teste 01: Consultar presenças por nome do cliente e intervalo de datas

| ID | Descrição |
| --- | --- |
| **CT-01** | Validar a busca de registros de presença informando o nome do cliente e um intervalo de datas customizado.

 |

| **Pré-condições** |
| --- |
| O usuário deve estar autenticado no sistema SiFit e na tela de **Presenças**.

 |

| **Passos** |
| --- |
| **DADO** que o usuário está na tela de **Presenças**<br> |
| **QUANDO** preencher o campo "Buscar por cliente..." com o nome ou parte do nome do cliente (ex: "eletroft")

 |
| **E** definir o intervalo nos campos "DE" e "ATÉ"

 |
| **E** clicar no botão **Buscar**<br> |
| **ENTÃO** o sistema deve atualizar os cards de resumo e apresentar os registros de presença correspondentes no intervalo pesquisado.

 |

| **Critérios de Aceitação** |
| --- |
| * Se nenhum registro for localizado, deve ser exibida a mensagem de feedback *"Nenhuma presença encontrada"*.

 |
| * Os cards superiores ("Total no período", "Acesso devedor", "Visita por dia", "Total no período") devem recalcular seus valores conforme a busca.

 |

---

### Caso de Teste 02: Utilizar filtros rápidos de período (Hoje, Esta semana, Este mês)

| ID | Descrição |
| --- | --- |
| **CT-02** | Validar o preenchimento automático das datas ao acionar os atalhos de período rápido.

 |

| **Pré-condições** |
| --- |
| O usuário está na tela de **Presenças**.

 |

| **Passos** |
| --- |
| **DADO** que o usuário está na tela de consulta de presenças

 |
| **QUANDO** clicar no botão atalho **Este mês** (ou "Hoje" / "Esta semana")

 |
| **ENTÃO** o sistema deve ajustar automaticamente os campos de data "DE" e "ATÉ" para cobrir o período selecionado

 |
| **E** recalcular os dados de presenças exibidos nos cards e na listagem.

 |

---

### Caso de Teste 03: Limpeza da busca e reexibição dos dados gerais

| ID | Descrição |
| --- | --- |
| **CT-03** | Validar a atualização dos resultados ao apagar o termo inserido no campo de busca.

 |

| **Pré-condições** |
| --- |
| Uma busca por cliente já foi realizada na tela.

 |

| **Passos** |
| --- |
| **DADO** que o usuário realizou uma pesquisa por cliente

 |
| **QUANDO** limpar o texto do campo "Buscar por cliente..."

 |
| **E** clicar novamente em **Buscar**<br> |
| **ENTÃO** o sistema deve listar os registros globais de presença do período selecionado sem restringir por cliente.

 |

https://jam.dev/c/a7f07a05-3bae-44dc-a449-dcd92293b1ea
