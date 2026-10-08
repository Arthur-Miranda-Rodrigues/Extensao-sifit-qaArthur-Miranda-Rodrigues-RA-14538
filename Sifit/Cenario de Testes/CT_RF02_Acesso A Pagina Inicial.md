
---

## Cenário 02: Módulo Página Inicial (Dashboard / Home).

### Caso de Teste 01: Visualização dos Indicadores Principais (Cards de Resumo).

| ID | Descrição |
| --- | --- |
| **C02-CT01** | Verificar se a página inicial exibe corretamente os cartões com os dados resumidos e consolidados do sistema (ex.: Total de Alunos, Avaliações Pendentes, Treinos Ativos, etc.). |

| **Pré-condições** |
| --- |
| Utilizador autenticado com sucesso no sistema SIFIT. |

| **Passos** |
| --- |
| **DADO** que o utilizador está autenticado no SIFIT |
| **E** está posicionado na página Inicial / Dashboard |
| **QUANDO** observar a área superior da página onde ficam situados os cards de métricas |
| **ENTÃO** o sistema deve carregar todos os indicadores de contagem corretamente sem erros de leitura e com os totais condizentes com a base de dados |

| **Critérios de aceitação** |
| --- |
| Os cards de contagem e indicadores principais devem exibir as informações consolidadas e corretas no painel inicial. |

| **Evidência** |
| --- |
|    |

---

### Caso de Teste 02: Navegação pelos Atalhos Rápidos da Página Inicial.

| ID | Descrição |
| --- | --- |
| **C02-CT02** | Validar se os botões e atalhos rápidos presentes na página inicial direcionam o utilizador para as respetivas telas operacionais. |

| **Pré-condições** |
| --- |
| O utilizador deve estar visualizando a Página Inicial do sistema. |

| **Passos** |
| --- |
| **DADO** que o utilizador está na Página Inicial |
| **E** localiza os botões ou links de atalho rápido (ex.: *Cadastrar Aluno*, *Agendar Avaliação*, *Criar Treino*) |
| **QUANDO** clicar em um dos atalhos disponíveis (ex.: *Agendar Avaliação*) |
| **ENTÃO** o sistema deve redirecionar o utilizador para a tela correspondente ao atalho clicado de forma rápida e sem erros |

| **Critérios de aceitação** |
| --- |
| Todos os botões de atalho rápido devem realizar o redirecionamento correto para as telas de destino. |

| **Evidência** |
| --- |
|    |

---

### Caso de Teste 03: Exibição da Agenda/Próximas Avaliações do Dia.

| ID | Descrição |
| --- | --- |
| **C02-CT03** | Garantir que o painel de agendamentos do dia/semana exibe corretamente os próximos alunos agendados. |

| **Pré-condições** |
| --- |
| O utilizador deve estar na Página Inicial do sistema SIFIT. |

| **Passos** |
| --- |
| **DADO** que o utilizador acedeu à Página Inicial |
| **QUANDO** verificar a secção de **Próximas Avaliações** ou **Agenda do Dia** |
| **ENTÃO** o sistema deve listar os nomes dos alunos, horários e status (ex.: *Pendente*, *Confirmado*) em ordem cronológica conforme a data atual |

| **Critérios de aceitação** |
| --- |
| A lista de agendamentos deve apresentar apenas os registros referentes ao período atual, ordenados cronologicamente por horário. |

| **Evidência** |
| --- |
|    |

---

### Caso de Teste 04: Acesso e Responsividade do Menu Lateral / Superior.

| ID | Descrição |
| --- | --- |
| **C02-CT04** | Validar o correto funcionamento e recolhimento do menu principal de navegação na Página Inicial. |

| **Pré-condições** |
| --- |
| O utilizador deve estar na Página Inicial do SIFIT. |

| **Passos** |
| --- |
| **DADO** que o utilizador está na Página Inicial |
| **E** clica no botão de alternar/recolher o menu (ícone de três barras / hambúrguer) |
| **QUANDO** a área útil do dashboard for expandida |
| **E** o utilizador clicar novamente para expandir o menu e selecionar um submenu (ex.: *Treinamento > Avaliações*) |
| **ENTÃO** o menu deve alternar o estado de recolhimento suavemente e redirecionar para a funcionalidade selecionada |

| **Critérios de aceitação** |
| --- |
| O menu principal deve recolher/expandir dinamicamente e manter a operabilidade de todos os seus links e submenus. |

| **Evidência** |
| --- |
|    |


https://jam.dev/c/705ba553-9cb5-4090-bb55-f846e1a2ee4e
