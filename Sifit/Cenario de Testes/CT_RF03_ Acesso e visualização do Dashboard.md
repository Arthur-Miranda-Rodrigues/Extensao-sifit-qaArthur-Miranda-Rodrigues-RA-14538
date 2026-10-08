

---

# Cenário 03: Acesso e visualização do Dashboard.

### Caso de Teste 01: Acesso à tela de Dashboard.

| ID | Descrição |
| --- | --- |
| **C02-CT01** | Verificar a navegação e a exibição correta da tela de Dashboard através do menu lateral do SIFIT. |

| **Pré-condições** |
| --- |
| O usuário deve estar autenticado no sistema. |

| **Passos** |
| --- |
| **DADO** que o usuário está autenticado no sistema |
| **QUANDO** clicar na opção "Dashboard" do menu lateral principal |
| **ENTÃO** a página de Dashboard deve ser carregada exibindo os gráficos, relatórios e o painel de Inteligência Sifit |

| **Critérios de aceitação** |
| --- |
| A tela de Dashboard deve ser exibida corretamente ao ser selecionada no menu. |

---

### Caso de Teste 02: Navegação e interação com a Inteligência Sifit.

| ID | Descrição |
| --- | --- |
| **C02-CT02** | Verificar o acesso à tela "Resultados da Inteligência" através do botão "Ver Inteligência" e a filtragem por período. |

| **Pré-condições** |
| --- |
| O usuário deve estar visualizando a tela de Dashboard. |

| **Passos** |
| --- |
| **DADO** que o usuário está no Dashboard |
| **QUANDO** clicar no botão "Ver Inteligência" no card de Inteligência Sifit |
| **E** selecionar os filtros de período (ex: "Últimos 7 dias", "Últimos 30 dias") |
| **ENTÃO** os dados de automações executadas, relatórios enviados, alunos em risco e demais métricas devem atualizar conforme o período selecionado |

| **Critérios de aceitação** |
| --- |
| O painel "Resultados da Inteligência" deve carregar e permitir a alternância de filtros temporal de forma funcional. |

---

### Caso de Teste 03: Interação com os gráficos interativos do Dashboard.

| ID | Descrição |
| --- | --- |
| **C02-CT03** | Verificar se os elementos gráficos do Dashboard respondem à passagem do cursor (*hover*) mostrando os detalhes das métricas. |

| **Pré-condições** |
| --- |
| O usuário deve estar na tela de Dashboard. |

| **Passos** |
| --- |
| **DADO** que o usuário está visualizando a tela de Dashboard |
| **QUANDO** passar o cursor sobre as barras dos gráficos de clientes, gráfico de rosca de pagamentos ou modalidades |
| **ENTÃO** o sistema deve exibir os balões de informação (*tooltips*) com os valores e categorias correspondentes |

| **Critérios de aceitação** |
| --- |
| Todos os gráficos interativos devem exibir os valores de cada seção ao passar o mouse sobre eles. |


https://jam.dev/c/5c1713ea-159f-4087-9e02-38767a30c1e6 
