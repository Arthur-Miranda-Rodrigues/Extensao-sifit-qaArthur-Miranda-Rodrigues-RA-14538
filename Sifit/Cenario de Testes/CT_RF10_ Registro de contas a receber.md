Aqui está a versão reformulada dos cenários de teste referente ao **RF07 - Registro e Gestão de Contas a Receber**, padronizada no formato **BDD/Gherkin** (mesmo padrão utilizado nas respostas anteriores), mantendo a clareza, rastreabilidade e estrutura técnica para a sua documentação de QA:

---

# Cenario de teste: Registro e Gestão de Contas a Receber

## 1. Descrição

Este documento especifica os casos de teste automatizáveis/executáveis referentes ao **Requisito Funcional 07 (RF07) - Registro e Gestão de Contas a Receber** do sistema **SiFit**. O objetivo é validar a busca por parâmetros, restrições de campos obrigatórios no cadastro, edição de títulos pendentes, exclusão de lançamentos e a consistência dos relatórios/cards financeiros ao aplicar filtros por data e status.

---

## 2. Casos de Teste (BDD / Gherkin)

### Caso de Teste 01: Filtro e Pesquisa por Código ou Cliente

| ID | Descrição |
| --- | --- |
| **CT01** | Validar o funcionamento do filtro de pesquisa por código ou nome na listagem de Contas a Receber. |

| **Pré-condições** |
| --- |
| Usuário autenticado no sistema SiFit e localizado na tela **Contas a Receber**. |

| **Passos** |
| --- |
| **DADO** que o usuário está na listagem de **Contas a Receber** |
| **QUANDO** informar o código do registro (ex.: "1590") ou nome do cliente no campo de busca |
| **E** clicar no botão **Buscar** |
| **ENTÃO** a tabela deve filtrar e exibir apenas os lançamentos correspondentes ao parâmetro informado. |

| **Critérios de Aceitação** |
| --- |
| * Apenas registros correspondentes ao código/termo pesquisado devem ser apresentados na grid. |
| * Se nenhum lançamento for localizado, a tabela deve apresentar o indicador de lista vazia. |

---

### Caso de Teste 02: Validação de Campo Obrigatório (Seleção de Cliente)

| ID | Descrição |
| --- | --- |
| **CT02** | Validar se o sistema impede a criação de uma nova conta a receber quando o cliente não for selecionado. |

| **Pré-condições** |
| --- |
| Modal de cadastro aberta ao clicar no botão **+ Nova Conta**. |

| **Passos** |
| --- |
| **DADO** que o usuário acessou a modal **Cadastrar Conta a Receber** |
| **E** deixa o campo de pesquisa de **Cliente** em branco |
| **QUANDO** preencher o campo **Título** (ex.: "Leo") |
| **E** selecionar **Criar Cópias** como "Sim" |
| **E** informar o **Valor a Receber** (ex.: "200,00") |
| **E** preencher o **Local** (ex.: "Caixa Academia") e a **Observação** (ex.: "Teste 1") |
| **E** clicar no botão **Salvar** |
| **ENTÃO** o sistema deve exibir um alerta com a mensagem *"Selecione o cliente."* |
| **E** impedir o envio do formulário e a criação do registro. |

---

### Caso de Teste 03: Exclusão de Conta a Receber

| ID | Descrição |
| --- | --- |
| **CT03** | Validar a remoção de um lançamento na listagem de Contas a Receber. |

| **Pré-condições** |
| --- |
| Existir ao menos um registro cadastrado na listagem (ex.: código 1590). |

| **Passos** |
| --- |
| **DADO** que o usuário está na listagem de **Contas a Receber** |
| **QUANDO** localizar o registro desejado e clicar no ícone de **Lixeira** na coluna de ações |
| **E** confirmar a ação clicando no botão **Confirmar** dentro do modal *"Deseja deletar esta conta?"* |
| **ENTÃO** a conta deve ser excluída e removida da grade de exibição |
| **E** os valores dos cards financeiros devem ser recalculados. |

---

### Caso de Teste 04: Edição e Atualização de Lançamento Pendente

| ID | Descrição |
| --- | --- |
| **CT04** | Validar a alteração e atualização dos dados de uma conta com status "PENDENTE". |

| **Pré-condições** |
| --- |
| Existir um lançamento cadastrado com o status **PENDENTE** (ex.: 1583 - Marcelo Longo Zandonadi). |

| **Passos** |
| --- |
| **DADO** que o usuário localizou um registro com status **PENDENTE** |
| **QUANDO** clicar no ícone de edição/visualização |
| **E** alterar o **Tipo de Pagamento** para *"Cartão de Débito"* |
| **E** alterar o **Local de Recebimento** para *"Caixa Muay Thai"* |
| **E** clicar no botão **Salvar** |
| **E** confirmar o aviso de caixa não aberto no dia (se exibido) |
| **ENTÃO** as informações do recebimento devem ser salvas com sucesso |
| **E** os novos dados devem ser refletidos na listagem e no resumo financeiro. |

---

### Caso de Teste 05: Aplicação de Filtros Rápidos por Período e Status

| ID | Descrição |
| --- | --- |
| **CT05** | Verificar a atualização dos cards financeiros e da listagem ao utilizar filtros por período e status. |

| **Pré-condições** |
| --- |
| Existirem lançamentos cadastrados em diferentes datas e status (Pendente, Recebido, etc.). |

| **Passos** |
| --- |
| **DADO** que o usuário está no módulo de **Contas a Receber** |
| **QUANDO** acionar um dos botões de atalho de período (**Hoje**, **Ontem**, **Últimos 7 dias** ou **Este mês**) |
| **OU** ajustar manualmente os campos de **Data Inicial** e **Data Final** |
| **E** selecionar um valor no filtro **Status** (ex.: *"Todos"*, *"Pendente"* ou *"Recebido"*) |
| **E** clicar no botão **Buscar** |
| **ENTÃO** a tabela deve filtrar os lançamentos de acordo com os critérios definidos |
| **E** os cards informativos (*Entradas*, *Saídas*, *Líquido*, *Previsto para o mês*, *Recebido no mês*) devem recalcular e apresentar os valores atualizados. |

https://jam.dev/c/aae899c5-f4dc-44b7-a506-01ac1f829a9a

