
---

# Cenário de Testes: Gestão de Clientes (RF07)

**Descrição:** Validação do módulo de Gestão de Clientes na plataforma SIFIT, englobando a atualização de dados cadastrais, ações no perfil do aluno, agendamento de avaliações, tratamento de exceções em pesquisas e exclusões, e validação de rotas da aplicação.

---

## Caso de Teste 01: Atualização de Dados Cadastrais do Cliente

| ID | Descrição |
| --- | --- |
| RF03-CT01 | Validar o preenchimento e salvamento das informações de endereço, aplicativo e responsável do cliente. |

| **Pré-condições** |
| --- |
| Usuário autenticado no sistema SIFIT com permissão de edição de cadastros. |

| **Passos** |
| --- |
| **DADO** que o usuário acessa o formulário de edição/cadastro do cliente<br>

<br>

<br>**QUANDO** preencher os campos de endereço (Bairro: "bairro da Catarina" e Complemento: "Casa da Catarina")<br>

<br>

<br>**E** informar o código do leitor biométrico ("123456")<br>

<br>

<br>**E** configurar os dados de acesso ao aplicativo (E-mail: "catarina@gmail.com" e Senha)<br>

<br>

<br>**E** preencher os dados do responsável e informações adicionais (Telefone: "(44) 99885-9666", Profissão: "Professor universitário", CPF, Estado Civil: "Solteiro" e Profissão Secundária: "Doceira")<br>

<br>

<br>**E** clicar no botão de salvar<br>

<br>

<br>**ENTÃO** os dados cadastrais do cliente devem ser atualizados e salvos com sucesso no sistema. |

| **Critérios de aceitação** |
| --- |
| Todos os campos informados (endereço, biometria, acesso ao aplicativo e dados pessoais/responsável) devem ser persistidos sem erros. |

---

## Caso de Teste 02: Ações no Perfil do Aluno e Agendamento de Avaliação

| ID | Descrição |
| --- | --- |
| RF03-CT02 | Verificar a navegação no perfil do aluno, disparo de mensagens via WhatsApp, verificação de pagamentos, presenças e agendamento de avaliação. |

| **Pré-condições** |
| --- |
| Existir o aluno "Guilherma Morangona" previamente cadastrado na base de dados. |

| **Passos** |
| --- |
| **DADO** que o usuário acessa a listagem de clientes e seleciona o aluno "Guilherma Morangona" para visualizar seu perfil<br>

<br>

<br>**QUANDO** clicar no botão "Enviar mensagem" para gerar o modelo via WhatsApp<br>

<br>

<br>**E** acionar a opção "Agendar avaliação", selecionando a personal responsável ("Gabriella"), a data ("05/09/2026") e o horário ("07:30")<br>

<br>

<br>**E** consultar as opções de "Registrar pagamento", "Histórico de presenças" e o painel "Inteligência Sifit"<br>

<br>

<br>**ENTÃO** o agendamento da avaliação física deve ser confirmado com sucesso e as modais e painéis de suporte do perfil devem responder e exibir as métricas corretamente. |

| **Critérios de aceitação** |
| --- |
| O agendamento da avaliação física deve ser salvo e o perfil do aluno deve carregar todas as ações e indicadores sem falhas. |

---

## Caso de Teste 03: Tentativa de Exclusão de Cliente (Validação de Falha/Bug)

| ID | Descrição |
| --- | --- |
| RF03-CT03 | Validar a funcionalidade de exclusão de registro de cliente diretamente pela listagem e tratar erros de servidor. |

| **Pré-condições** |
| --- |
| Existir a cliente "Catarina Resende" cadastrada e visível na tabela de clientes. |

| **Passos** |
| --- |
| **DADO** que o usuário acessa a listagem de clientes<br>

<br>

<br>**QUANDO** localizar a cliente "Catarina Resende" na tabela<br>

<br>

<br>**E** clicar no ícone de exclusão/deletar registro<br>

<br>

<br>**ENTÃO** o sistema deve solicitar confirmação e remover o registro do banco de dados ou tratar a exceção reportando o modal de aviso: "Erro no servidor - Erro interno inesperado". |

| **Critérios de aceitação** |
| --- |
| O registro deve ser removido com sucesso ou, em caso de exceção no servidor, exibir uma mensagem de erro amigável ao usuário. |

---

## Caso de Teste 04: Pesquisa de Clientes com Filtros Avançados (Validação de Falha/Bug)

| ID | Descrição |
| --- | --- |
| RF03-CT04 | Validar a consulta de clientes utilizando filtros combinados por código de biometria e nome. |

| **Pré-condições** |
| --- |
| Estar na tela de listagem de clientes do módulo SIFIT. |

| **Passos** |
| --- |
| **DADO** que o usuário acessa a tela de listagem de clientes<br>

<br>

<br>**QUANDO** preencher o campo de código/biometria com "200306"<br>

<br>

<br>**E** preencher o campo de nome com "Guilherma Morangona"<br>

<br>

<br>**E** clicar no botão "Buscar"<br>

<br>

<br>**ENTÃO** o sistema deve filtrar e retornar apenas o registro correspondente aos parâmetros ou tratar a falha exibindo o alerta de "Erro no servidor - Erro interno inesperado". |

| **Critérios de aceitação** |
| --- |
| A busca combinada deve filtrar com precisão os registros cadastrados na listagem sem ocasionar falhas internas no servidor. |

---

## Caso de Teste 05: Validação de Mapeamento de Rotas / Navegação (Validação de Falha/Bug)

| ID | Descrição |
| --- | --- |
| RF03-CT05 | Validar o direcionamento e carregamento correto de páginas e submenus no módulo de clientes. |

| **Pré-condições** |
| --- |
| Usuário autenticado na plataforma SIFIT. |

| **Passos** |
| --- |
| **DADO** que o usuário navega entre os menus e visões da aplicação no módulo de clientes<br>

<br>

<br>**QUANDO** acessar os links e submenus do módulo<br>

<br>

<br>**ENTÃO** a aplicação deve carregar corretamente as visões solicitadas sem redirecionar para a tela de erro 404 ("This Page Does Not Exist"). |

| **Critérios de aceitação** |
| --- |
| Todas as rotas do módulo de clientes devem estar corretamente mapeadas, garantindo que o usuário não seja redirecionado para páginas inexistentes (404). |


https://jam.dev/c/493528c5-fa47-42ad-835a-0f6499a5c6ea
https://jam.dev/c/2aa6309a-66ea-49fa-bfc8-368289cb5e89
https://jam.dev/c/00b55482-263c-4d73-a02b-6cc3d1de0fb1
