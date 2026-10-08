
---

# Cenário de Testes: Gerenciamento de Avaliações Físicas

**Descrição:** Validação do módulo de Avaliações Físicas na plataforma SIFIT, contemplando a consulta de indicadores (KPIs), filtros de busca, cadastro/edição com medições estruturadas (IMC, Circunferências, Subcutâneas e Composição Corporal) e exclusão de registros.

---

## Caso de Teste 01: Filtro e Pesquisa de Avaliações na Listagem Principal

| ID | Descrição |
| --- | --- |
| RF06-CT01 | Verificar a filtragem de avaliações por Código, Nome do aluno e Status na tela principal. |

| **Pré-condições** |
| --- |
| Usuário autenticado como instrutor/personal trainer com acesso ao módulo de Avaliações no SIFIT. |

| **Passos** |
| --- |
| **DADO** que o usuário acessa a tela de "Gerenciamento de Avaliações"<br>

<br>

<br>**QUANDO** consultar os indicadores no topo da tela (Avaliação no Mês, Mês Passado e Média Mensal)<br>

<br>

<br>**ENTÃO** o sistema deve exibir os valores das métricas calculados corretamente.<br>

<br>

<br>**E QUANDO** inserir um filtro por código (ex: #12), por nome do aluno (ex: "Carlos") ou selecionar o status ("REALIZADO" ou "PENDENTE")<br>

<br>

<br>**E** clicar no botão "Buscar"<br>

<br>

<br>**ENTÃO** a tabela deve recarregar exibindo apenas as avaliações que correspondem aos parâmetros informados. |

| **Critérios de aceitação** |
| --- |
| Os indicadores KPIs devem ser exibidos e a tabela de listagem deve filtrar os registros de acordo com os critérios informados. |

---

## Caso de Teste 02: Cadastro e Cálculo Automático de IMC com Recomendações

| ID | Descrição |
| --- | --- |
| RF06-CT02 | Validar o preenchimento da aba IMC, o cálculo automático do índice e a exibição da classificação e dicas personalizadas. |

| **Pré-condições** |
| --- |
| Estar na tela de cadastro ou edição de uma avaliação física. |

| **Passos** |
| --- |
| **DADO** que o usuário acessa a aba "IMC" do formulário de Avaliação<br>

<br>

<br>**QUANDO** preencher os dados do aluno com Idade (ex: 28), Altura (ex: 1,75 m) e Peso (ex: 75 kg)<br>

<br>

<br>**ENTÃO** o sistema deve realizar o cálculo automático do IMC ($kg/m^2$).<br>

<br>

<br>**E** exibir a classificação visual correspondente (Abaixo do Peso, Peso Normal, Sobrepeso ou Obesidade).<br>

<br>

<br>**E** apresentar as dicas e recomendações personalizadas com base no resultado obtido. |

| **Critérios de aceitação** |
| --- |
| O IMC deve ser calculado instantaneamente ao inserir altura e peso, atualizando a faixa de classificação e os conselhos de saúde. |

---

## Caso de Teste 03: Registro de Circunferências Corporais

| ID | Descrição |
| --- | --- |
| RF06-CT03 | Confirmar o preenchimento de medições corporais em centímetros na aba Circunferências. |

| **Pré-condições** |
| --- |
| Estar no formulário de avaliação física na aba "Circunferências". |

| **Passos** |
| --- |
| **DADO** que o usuário acessa a aba "Circunferências"<br>

<br>

<br>**QUANDO** inserir as medições em centímetros ($cm$) para os campos de Ombro, Tórax, Cintura, Quadril, Abdomen, Coxa Direita/Esquerda, Braço Direito/Esquerdo, Antebraço Direito/Esquerdo e Panturrilha Direita/Esquerda<br>

<br>

<br>**ENTÃO** o sistema deve atualizar a Relação Cintura/Quadril (RCQ) e salvar os dados no formulário sem erros de validação. |

| **Critérios de aceitação** |
| --- |
| Todas as medidas de circunferência em $cm$ devem ser aceitas e salvas corretamente na estrutura do registro. |

---

## Caso de Teste 04: Registro de Dobras Cutâneas e Cálculo de Composição Corporal

| ID | Descrição |
| --- | --- |
| RF06-CT04 | Verificar o lançamento das dobras subcutâneas em milímetros e a geração automática dos relatórios de Composição Corporal. |

| **Pré-condições** |
| --- |
| Ter preenchido os dados básicos e de dobras subcutâneas do aluno. |

| **Passos** |
| --- |
| **DADO** que o usuário acessa a aba "Subcutâneas"<br>

<br>

<br>**QUANDO** informar as dobras em milímetros ($mm$) para Bíceps, Tríceps, Subescapular, Supra-ilíaca, Tórax, Axilar Média, Abdominal, Coxa e Panturrilha<br>

<br>

<br>**E** navegar para a aba "Composição Corporal"<br>

<br>

<br>**ENTÃO** o sistema deve apresentar os indicadores calculados automaticamente: Densidade Corporal, % de Gordura, Peso de Gordura, Peso em Excesso, Resultado % de Gordura e a Classificação Visual do aluno. |

| **Critérios de aceitação** |
| --- |
| Os parâmetros de composição corporal (% gordura, massa gorda, etc.) devem ser calculados e apresentados automaticamente a partir do lançamento das dobras subcutâneas. |

---

## Caso de Teste 05: Exclusão de Registro de Avaliação

| ID | Descrição |
| --- | --- |
| RF06-CT05 | Validar a exclusão de uma avaliação física cadastrada mediante confirmação do usuário. |

| **Pré-condições** |
| --- |
| Existir pelo menos uma avaliação cadastrada na tabela principal. |

| **Passos** |
| --- |
| **DADO** que o usuário está na tabela de Gerenciamento de Avaliações<br>

<br>

<br>**QUANDO** clicar no ícone de Caixote do Lixo ("Eliminar") na linha de uma avaliação existente<br>

<br>

<br>**ENTÃO** o sistema deve exibir o modal de confirmação com a mensagem: "Deseja deletar esta avaliação?".<br>

<br>

<br>**E QUANDO** clicar no botão "Confirmar"<br>

<br>

<br>**ENTÃO** a avaliação deve ser removida do banco de dados e a listagem deve ser atualizada. |

| **Critérios de aceitação** |
| --- |
| O sistema deve exigir confirmação em modal antes de deletar a avaliação e remover o registro da listagem ao confirmar. |


https://jam.dev/c/57a0b943-9910-4c6a-b81b-7e0588b11767

https://jam.dev/c/b937fe21-a3f2-4f09-a919-25e532eb80fe
