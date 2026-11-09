## Declaração de tarefa 3.3: Descrever o processo de treinamento e ajuste fino dos FMs

### 1️⃣ Principais elementos do treinamento de um FM

<h3><strong style='color: skyblue'>O que é treinamento de um modelo de base?</strong></h3>

<p align="justify">O treinamento é o processo pelo qual um modelo aprende padrões, relações e representações a partir de grandes conjuntos de dados. Durante esse processo, seus parâmetros (pesos) são ajustados para melhorar sua capacidade de executar determinadas tarefas.</p>

<p align="justify">Um modelo de base (Foundation Model — FM) é treinado com grandes volumes de dados e pode ser adaptado posteriormente para diferentes aplicações, sem precisar desenvolver um modelo completamente novo.</p>

**Principais etapas e métodos:**

- Pré-treinamento (Pre-training).
- Ajuste fino (Fine-tuning).
- Pré-treinamento contínuo (Continued Pre-training).
- Destilação (Distillation).

<h3><strong style='color: skyblue'>Pré-treinamento (Pre-training)</strong></h3>

<p align="justify">É a etapa inicial em que o modelo aprende padrões gerais a partir de grandes volumes de dados. O objetivo é desenvolver conhecimentos e capacidades que possam ser utilizados em diferentes tarefas.</p>

**Características:**
- Utiliza grandes conjuntos de dados.
- Geralmente utiliza dados não rotulados.
- Exige grande capacidade computacional.
- Aprende padrões linguísticos, relações e estruturas.
- Produz um modelo de base que pode ser posteriormente adaptado.

**Exemplo:**

Um modelo é treinado com grandes quantidades de textos disponíveis publicamente para aprender:
- Gramática e linguagem.
- Relações entre palavras.
- Conhecimentos gerais.
- Estruturas de texto.
- Padrões de comunicação.

> **DECORA:** Pré-treinamento = ensinar conhecimentos e capacidades gerais ao modelo.

<h3><strong style='color: skyblue'>Ajuste fino (Fine-tuning)</strong></h3>

<p align="justify">É o processo de continuar o treinamento de um modelo já pré-treinado utilizando dados específicos para melhorar seu desempenho em determinadas tarefas ou aplicações.</p>

<p align="justify">Diferentemente do pré-treinamento, o ajuste fino parte de um modelo que já possui conhecimentos gerais. Durante o processo, seus parâmetros podem ser ajustados para especializá-lo.</p>

**Características:**
- Parte de um modelo pré-treinado.
- Utiliza dados mais específicos.
- Pode utilizar dados rotulados.
- Ajusta os pesos do modelo.
- Especializa o comportamento para determinadas tarefas.
- Geralmente exige menos recursos do que treinar um modelo do zero.

**Exemplo:**

Uma empresa utiliza um modelo de linguagem geral e realiza ajuste fino com exemplos de atendimento bancário.

O modelo passa a apresentar melhor desempenho em:
- Classificação de solicitações bancárias.
- Respostas padronizadas.
- Linguagem financeira.
- Procedimentos específicos da instituição.

> **DECORA:** Fine-tuning = especializar um modelo que já foi treinado.

<h3><strong style='color: skyblue'>Pré-treinamento contínuo (Continued Pre-training)</strong></h3>

<p align="justify">É a continuação do treinamento de um modelo de base já pré-treinado, utilizando dados adicionais, geralmente não rotulados, para ampliar ou aprofundar seu conhecimento em determinado domínio.</p>

<p align="justify">É especialmente útil quando o modelo precisa compreender vocabulário, conceitos e padrões de uma área específica, sem necessariamente receber exemplos explícitos de perguntas e respostas.</p>

**Características:**
- Parte de um modelo pré-treinado.
- Utiliza dados adicionais, geralmente não rotulados.
- Continua ajustando os parâmetros do modelo.
- Amplia o conhecimento sobre determinado domínio.
- Pode utilizar documentos técnicos, científicos ou empresariais.

**Exemplo:**

Uma instituição financeira possui milhares de documentos técnicos, relatórios e materiais sobre o mercado financeiro.

O modelo recebe esses dados adicionais para desenvolver maior familiaridade com:
- Terminologia financeira.
- Produtos bancários.
- Operações de crédito.
- Conceitos econômicos.
- Documentação específica do setor.

> **DECORA:** Continued Pre-training = continuar ensinando conhecimentos ao modelo utilizando novos dados, geralmente não rotulados.

<h3><strong style='color: skyblue'>Destilação de modelos (Model Distillation)</strong></h3>

<p align="justify">É uma técnica que transfere conhecimento de um modelo maior e mais complexo, chamado professor (Teacher), para um modelo menor, chamado aluno (Student).</p>

<p align="justify">O objetivo é produzir um modelo mais eficiente, com menor custo de inferência, menor latência e menor necessidade de memória, preservando o máximo possível da capacidade relevante do modelo original.</p>

**Como funciona:**

```text
      MODELO PROFESSOR
       (Teacher Model)
       Maior e complexo
              |
              v
    Gera respostas e sinais
       de treinamento
              |
              v
       MODELO ALUNO
       (Student Model)
       Menor e eficiente
              |
              v
    Aprende as capacidades
      relevantes do professor
              |
              v
     Inferência mais rápida
       e potencialmente
       mais econômica
```

**Características:**
- O modelo professor fornece o conhecimento.
- O modelo aluno aprende a reproduzir capacidades relevantes.
- Pode utilizar respostas geradas pelo professor.
- Pode reduzir custos de execução.
- Pode diminuir latência e consumo de memória.
- O modelo aluno pode perder parte das capacidades do professor.

**Exemplo:**

Uma empresa utiliza um modelo grande para responder dúvidas técnicas. Entretanto, o custo de execução é elevado.

A empresa utiliza a destilação para transferir conhecimentos relevantes para um modelo menor, que passa a atender perguntas recorrentes com menor custo.

**Na AWS:**
- Amazon Bedrock Model Distillation.
- Amazon SageMaker AI também oferece recursos relacionados à destilação.

> **DECORA:** Distillation = Professor grande ensina Aluno menor, buscando reduzir custo e latência.

<h3><strong style='color: skyblue'>Comparação dos elementos de treinamento</strong></h3>

| Método | Objetivo | Dados utilizados |
|---|---|---|
| Pré-treinamento | Desenvolver capacidades gerais. | Grandes volumes de dados, geralmente não rotulados. |
| Ajuste fino | Especializar o modelo em tarefas. | Exemplos específicos, geralmente rotulados. |
| Pré-treinamento contínuo | Ampliar conhecimentos de um domínio. | Dados adicionais, geralmente não rotulados. |
| Destilação | Transferir conhecimento para um modelo menor. | Respostas e sinais de treinamento do professor. |

> **PEGADINHA:** Pré-treinamento contínuo não é a mesma coisa que ajuste fino supervisionado. O primeiro normalmente utiliza dados não rotulados para ampliar conhecimentos; o segundo utiliza exemplos rotulados para ensinar tarefas e comportamentos específicos.

---

### 2️⃣ Métodos de ajuste fino de um FM

<h3><strong style='color: skyblue'>Ajuste de instruções (Instruction Tuning)</strong></h3>

<p align="justify">É uma forma de ajuste fino supervisionado em que o modelo recebe exemplos de instruções e suas respectivas respostas desejadas. O objetivo é ensiná-lo a seguir melhor comandos e executar tarefas de acordo com as expectativas dos usuários.</p>

**Características:**
- Utiliza pares de instrução e resposta.
- Normalmente utiliza dados rotulados.
- Ensina o modelo a seguir instruções.
- Melhora a capacidade de executar tarefas específicas.
- Ajusta os parâmetros do modelo.

**Exemplo:**

```text
Instrução:
Resuma o seguinte relatório em três tópicos.

Entrada:
[Texto do relatório]

Resposta esperada:
- Crescimento de 15% nas vendas.
- Redução de 8% nos custos.
- Aumento da satisfação dos clientes.
```

Após receber muitos exemplos semelhantes, o modelo aprende a seguir instruções e produzir respostas no formato desejado.

**Aplicações:**
- Assistentes virtuais.
- Classificação de documentos.
- Resumo de relatórios.
- Respostas padronizadas.
- Extração de informações.

> **DECORA:** Instruction Tuning = ensinar o modelo a seguir instruções por meio de exemplos de entrada e saída.

<h3><strong style='color: skyblue'>Adaptação para domínios específicos (Domain Adaptation)</strong></h3>

<p align="justify">É o processo de adaptar um modelo de base para compreender melhor a linguagem, os conceitos, os padrões e as características de um domínio específico.</p>

<p align="justify">O modelo pode ter conhecimentos gerais, mas apresentar dificuldades com terminologias e particularidades de determinados setores.</p>

**Exemplos de domínios:**
- Saúde.
- Direito.
- Finanças.
- Engenharia.
- Tecnologia.
- Telecomunicações.

**Exemplo prático:**

Um modelo geral precisa ser utilizado em uma empresa de tecnologia que trabalha com infraestrutura de Big Data.

A adaptação pode melhorar sua compreensão de termos como:
- HDFS.
- YARN.
- Kerberos.
- Hive.
- Impala.
- Kafka.

**Possíveis abordagens:**
- Pré-treinamento contínuo com documentos do domínio.
- Ajuste fino supervisionado com exemplos especializados.
- Aprendizado por transferência.

> **DECORA:** Domain Adaptation = adaptar o modelo ao vocabulário e às necessidades de uma área específica.

<h3><strong style='color: skyblue'>Aprendizado por transferência (Transfer Learning)</strong></h3>

<p align="justify">É uma abordagem em que conhecimentos aprendidos por um modelo em uma tarefa ou conjunto de dados são aproveitados para outra tarefa relacionada.</p>

<p align="justify">Em vez de começar do zero, utiliza-se um modelo que já aprendeu representações úteis e adapta-se esse conhecimento ao novo problema.</p>

**Características:**
- Reutiliza conhecimentos previamente aprendidos.
- Reduz a necessidade de treinamento do zero.
- Pode diminuir custos e tempo de desenvolvimento.
- É frequentemente utilizado como base para ajuste fino.
- Pode exigir menos dados do que treinar um modelo completamente novo.

**Exemplo:**

Um modelo treinado para reconhecer objetos em imagens pode ser adaptado para identificar equipamentos industriais.

Ele já possui conhecimentos sobre:
- Formas.
- Texturas.
- Contornos.
- Características visuais.

O aprendizado por transferência aproveita essas capacidades para a nova tarefa.

> **DECORA:** Transfer Learning = aproveitar o conhecimento de um modelo existente em uma nova tarefa relacionada.

<h3><strong style='color: skyblue'>Pré-treinamento contínuo como método de adaptação</strong></h3>

<p align="justify">O pré-treinamento contínuo também pode ser utilizado como método de personalização de um FM. Ele amplia o conhecimento do modelo por meio de dados adicionais do domínio desejado.</p>

**Exemplo:**

Um modelo geral recebe documentos técnicos de uma empresa para aprender terminologias e padrões específicos de sua área de atuação.

**Diferença importante:**

- Instruction Tuning: ensina como responder a instruções.
- Domain Adaptation: adapta o conhecimento e o comportamento a um domínio.
- Transfer Learning: reutiliza conhecimentos de um modelo pré-treinado.
- Continued Pre-training: continua o treinamento com dados adicionais, geralmente não rotulados.

<h3><strong style='color: skyblue'>Comparação dos métodos</strong></h3>

| Método | Principal objetivo | Exemplo |
|---|---|---|
| Instruction Tuning | Melhorar o cumprimento de instruções. | Ensinar a gerar respostas padronizadas. |
| Domain Adaptation | Especializar o modelo em uma área. | Adaptar para linguagem médica. |
| Transfer Learning | Reutilizar conhecimentos existentes. | Adaptar um modelo visual para outra tarefa. |
| Continued Pre-training | Ampliar conhecimentos com novos dados. | Ensinar terminologia financeira. |

> **PEGADINHA:** Transfer Learning é uma abordagem mais ampla de reutilização de conhecimento. Fine-tuning é uma das formas de adaptar um modelo utilizando treinamento adicional.

---

### 3️⃣ Preparação dos dados para ajuste fino de um FM

<h3><strong style='color: skyblue'>Importância da preparação dos dados</strong></h3>

<p align="justify">A qualidade dos dados utilizados no treinamento influencia diretamente o desempenho do modelo. Dados incorretos, inconsistentes, desatualizados ou pouco representativos podem prejudicar o aprendizado e gerar respostas inadequadas.</p>

<p align="justify">Antes de iniciar o ajuste fino, é necessário selecionar, organizar, limpar, validar e preparar os conjuntos de dados de acordo com o modelo e a tarefa desejada.</p>

> **DECORA:** Qualidade dos dados é fundamental para a qualidade do modelo. Mais dados não significam necessariamente melhores resultados.

<h3><strong style='color: skyblue'>Curadoria de dados (Data Curation)</strong></h3>

<p align="justify">É o processo de selecionar, organizar, limpar e validar os dados que serão utilizados no treinamento.</p>

**Atividades:**
- Remover registros duplicados.
- Corrigir erros e inconsistências.
- Eliminar informações irrelevantes.
- Identificar dados desatualizados.
- Remover conteúdo inadequado.
- Verificar a qualidade das informações.
- Padronizar formatos.

**Exemplo:**

Uma empresa pretende ajustar um modelo com históricos de atendimento.

Durante a curadoria, identifica:
- Chamados duplicados.
- Respostas incorretas.
- Registros incompletos.
- Informações desatualizadas.
- Mensagens sem relação com o objetivo do treinamento.

Esses registros devem ser corrigidos ou removidos conforme critérios definidos.

> **DECORA:** Data Curation = selecionar, limpar, organizar e validar os dados.

<h3><strong style='color: skyblue'>Governança de dados (Data Governance)</strong></h3>

<p align="justify">É o conjunto de políticas, processos e controles que garantem que os dados sejam utilizados de maneira segura, adequada, rastreável e em conformidade com as regras da organização e com as exigências legais.</p>

**Aspectos importantes:**
- Privacidade.
- Segurança.
- Controle de acesso.
- Qualidade dos dados.
- Rastreabilidade.
- Conformidade regulatória.
- Gerenciamento de informações sensíveis.
- Direitos de uso e propriedade dos dados.

**Exemplo:**

Uma instituição financeira pretende utilizar históricos de atendimento para ajustar um modelo.

Antes do treinamento, deve avaliar:
- Se possui autorização para utilizar os dados.
- Se existem informações pessoais desnecessárias.
- Se os dados precisam ser anonimizados ou mascarados.
- Quem pode acessar os conjuntos de treinamento.
- Onde os dados serão armazenados.

**Na AWS:**
- Amazon S3: armazenamento dos conjuntos de dados.
- AWS IAM: controle de acesso.
- AWS KMS: gerenciamento de chaves de criptografia.
- AWS CloudTrail: registro de atividades e auditoria.

> **DECORA:** Data Governance = garantir o uso correto, seguro e controlado dos dados.

<h3><strong style='color: skyblue'>Tamanho do conjunto de dados (Dataset Size)</strong></h3>

<p align="justify">A quantidade de dados utilizada no ajuste fino influencia o aprendizado do modelo. É importante ter dados suficientes para representar as tarefas desejadas, mas também manter qualidade e diversidade.</p>

**Conjunto muito pequeno:**
- Pode não representar adequadamente a tarefa.
- Pode limitar a capacidade de generalização.
- Pode aumentar o risco de overfitting.

**Conjunto muito grande:**
- Pode aumentar custos de treinamento.
- Pode aumentar o tempo de processamento.
- Pode incluir dados redundantes ou de baixa qualidade.

**Boa prática:**
- Utilizar quantidade adequada ao modelo e à tarefa.
- Priorizar qualidade e diversidade.
- Avaliar resultados com dados de validação.
- Seguir os limites e requisitos do modelo escolhido.

> **DECORA:** O objetivo não é ter o maior conjunto de dados, mas um conjunto suficiente, relevante e de qualidade.

<h3><strong style='color: skyblue'>Rotulagem de dados (Data Labeling)</strong></h3>

<p align="justify">É o processo de associar informações ou respostas esperadas aos dados utilizados no treinamento supervisionado.</p>

<p align="justify">Os rótulos indicam ao modelo qual resultado é esperado para determinada entrada.</p>

**Exemplo de classificação:**

| Entrada | Rótulo |
|---|---|
| "O serviço está indisponível." | Crítico |
| "O sistema apresenta lentidão." | Alto |
| "Solicito acesso ao sistema." | Médio |
| "Preciso atualizar meu cadastro." | Baixo |

**Exemplo de ajuste fino supervisionado:**

```text
Entrada:
O usuário informa que não consegue acessar
o sistema de autenticação.

Saída esperada:
Categoria: Autenticação
Prioridade: Alta
Ação: Verificar o serviço de autenticação.
```

**Boas práticas:**
- Utilizar rótulos corretos.
- Manter consistência entre os exemplos.
- Evitar ambiguidades.
- Definir critérios claros de classificação.
- Revisar os dados rotulados.

> **DECORA:** Labeling = associar uma entrada ao resultado ou à categoria esperada.

<h3><strong style='color: skyblue'>Representatividade dos dados (Data Representativeness)</strong></h3>

<p align="justify">Significa garantir que os dados utilizados no treinamento representem adequadamente as situações que o modelo encontrará em produção.</p>

<p align="justify">Um conjunto de dados pouco representativo pode fazer o modelo apresentar bom desempenho em situações conhecidas, mas falhar quando receber entradas diferentes.</p>

**Exemplo:**

Uma empresa deseja treinar um assistente para atender clientes de diferentes regiões.

Se os dados contiverem apenas exemplos de clientes de uma única região, o modelo poderá apresentar dificuldades com:
- Diferentes formas de expressão.
- Variações linguísticas.
- Diferentes perfis de usuários.
- Situações pouco frequentes.

**Boas práticas:**
- Incluir diferentes cenários.
- Representar diferentes perfis de usuários.
- Considerar casos comuns e casos extremos.
- Evitar vieses nos dados.
- Incluir exemplos variados e realistas.

> **DECORA:** Representatividade = os dados precisam refletir as situações reais que o modelo enfrentará.

<h3><strong style='color: skyblue'>Conjuntos de treinamento, validação e teste</strong></h3>

<p align="justify">Os dados podem ser separados em conjuntos com finalidades diferentes. Essa divisão permite treinar o modelo e verificar se ele consegue generalizar para dados que não foram utilizados diretamente no treinamento.</p>

| Conjunto | Finalidade |
|---|---|
| Treinamento (Training) | Ensinar o modelo e ajustar seus parâmetros. |
| Validação (Validation) | Acompanhar o desempenho e orientar ajustes durante o desenvolvimento. |
| Teste (Testing) | Avaliar o desempenho final com dados não utilizados no treinamento. |

**Exemplo:**

```text
        CONJUNTO DE DADOS
                |
       +--------+--------+
       |        |        |
       v        v        v
   Training Validation Testing
       |        |        |
       v        v        v
    Aprende  Ajustes   Avaliação
       |        |        |
       +--------+--------+
                |
                v
        Modelo avaliado
```

**Importante:**
- Os dados de teste não devem ser utilizados para ajustar o modelo.
- A validação ajuda a identificar problemas durante o desenvolvimento.
- Os conjuntos devem ser representativos.
- Quando necessário, deve-se evitar que informações duplicadas ou relacionadas apareçam em conjuntos diferentes, causando vazamento de dados.

> **PEGADINHA:** Training ensina; Validation ajuda a ajustar; Testing avalia o resultado final.

<h3><strong style='color: skyblue'>Aprendizado por reforço com feedback humano (RLHF)</strong></h3>

<p align="justify">RLHF (Reinforcement Learning from Human Feedback) é uma abordagem que utiliza avaliações humanas para orientar e melhorar o comportamento de um modelo.</p>

<p align="justify">Em vez de depender exclusivamente de respostas corretas previamente rotuladas, o processo pode utilizar comparações e preferências humanas para identificar quais respostas são melhores.</p>

**Como funciona:**

```text
       PROMPT DO USUÁRIO
              |
              v
       MODELO GERA
       VÁRIAS RESPOSTAS
              |
              v
      AVALIADORES HUMANOS
      COMPARAM AS RESPOSTAS
              |
              v
      PREFERÊNCIAS HUMANAS
       (MELHOR / PIOR)
              |
              v
       MODELO DE RECOMPENSA
              |
              v
     OTIMIZAÇÃO DO MODELO
       POR APRENDIZADO
          POR REFORÇO
              |
              v
       MODELO MAIS ALINHADO
       ÀS PREFERÊNCIAS
```

**Etapas conceituais:**

1. O modelo recebe prompts e gera respostas.
2. Avaliadores humanos analisam e comparam as respostas.
3. As preferências são utilizadas para construir um sinal de recompensa.
4. O modelo é otimizado para produzir respostas com maior recompensa.
5. O processo pode ser repetido para melhorar o alinhamento.

**Objetivos do RLHF:**
- Melhorar a utilidade das respostas.
- Alinhar o modelo às preferências humanas.
- Reduzir respostas inadequadas.
- Melhorar a qualidade das interações.
- Orientar o comportamento do modelo.

**Exemplo:**

Um assistente gera duas respostas para uma pergunta de suporte.

- Resposta A: técnica, mas confusa e muito extensa.
- Resposta B: clara, objetiva e correta.

Os avaliadores humanos preferem a resposta B. Esse feedback pode ser utilizado para orientar o modelo a produzir respostas mais adequadas.

> **DECORA:** RLHF = utilizar feedback humano para orientar o comportamento do modelo por meio de aprendizado por reforço.

<h3><strong style='color: skyblue'>RLHF × Ajuste fino supervisionado</strong></h3>

| Característica | Ajuste fino supervisionado (SFT) | RLHF |
|---|---|---|
| Dados | Exemplos com respostas desejadas. | Preferências e avaliações humanas. |
| Orientação | Aprender a produzir a resposta esperada. | Aprender quais respostas são preferíveis. |
| Objetivo | Melhorar tarefas e seguir instruções. | Alinhar o comportamento às preferências humanas. |
| Feedback | Resposta de referência. | Sinal de preferência ou recompensa. |

**Atenção:** RLHF não significa simplesmente pedir que uma pessoa corrija uma resposta. O feedback humano é incorporado a um processo de aprendizado por reforço.

<h3><strong style='color: skyblue'>Qualidade dos dados e problemas de treinamento</strong></h3>

Alguns problemas podem comprometer o resultado do ajuste fino:

| Problema | Consequência |
|---|---|
| Dados incorretos | Modelo aprende informações erradas. |
| Dados duplicados | Pode reforçar padrões de maneira desproporcional. |
| Dados pouco representativos | Baixa capacidade de generalização. |
| Rótulos inconsistentes | Comportamento imprevisível. |
| Dados insuficientes | Aprendizado limitado. |
| Dados desatualizados | Conhecimento inadequado. |
| Dados enviesados | Respostas discriminatórias ou distorcidas. |
| Dados contaminados | Aprendizado de padrões maliciosos ou indesejados. |

> **DECORA:** Garbage in, garbage out — dados ruins podem produzir modelos ruins.

<h3><strong style='color: skyblue'>Preparação de dados no Amazon Bedrock</strong></h3>

<p align="justify">O Amazon Bedrock permite personalizar modelos utilizando conjuntos de dados preparados de acordo com os requisitos do modelo e do método de personalização escolhido.</p>

**Pontos importantes:**
- Os dados de treinamento devem seguir o formato exigido pelo modelo.
- Para determinados ajustes finos de texto, os dados podem utilizar arquivos JSONL.
- Cada linha do JSONL representa um registro.
- Os registros podem conter prompts e respostas esperadas.
- Alguns métodos também permitem conjuntos de validação.
- Os dados podem ser armazenados no Amazon S3.
- O acesso aos arquivos deve ser autorizado por políticas e funções IAM.

**Exemplo simplificado de JSONL para ajuste fino supervisionado:**

```json
{"prompt":"Qual é a capital do Brasil?","completion":"Brasília."}
{"prompt":"Quanto é 2 + 2?","completion":"4."}
{"prompt":"Explique o que é armazenamento em nuvem.","completion":"É o armazenamento de dados em infraestrutura acessível pela rede."}
```

**Atenção:**
- JSONL significa JSON Lines.
- Cada linha representa um objeto JSON independente.
- O formato exato depende do modelo e do método de personalização.
- Os limites de quantidade de registros, tokens e tamanho dos arquivos variam conforme o modelo.

> **DECORA:** Amazon Bedrock utiliza dados preparados conforme os requisitos do modelo; JSONL é um formato comum para conjuntos de ajuste fino.

---

## 🎯 DECORAÇÃO FINAL

| Conceito | O que lembrar |
|---|---|
| FM | Modelo treinado com grandes volumes de dados e reutilizável em várias tarefas. |
| Pré-treinamento | Desenvolve conhecimentos e capacidades gerais. |
| Fine-tuning | Especializa um modelo pré-treinado. |
| Continued Pre-training | Continua o treinamento com dados adicionais, geralmente não rotulados. |
| Distillation | Transfere conhecimento do modelo professor para o aluno. |
| Teacher | Modelo maior que fornece conhecimento. |
| Student | Modelo menor que aprende com o professor. |
| Instruction Tuning | Ensina o modelo a seguir instruções. |
| Domain Adaptation | Adapta o modelo a um domínio específico. |
| Transfer Learning | Reutiliza conhecimento de um modelo existente. |
| Data Curation | Selecionar, limpar e organizar dados. |
| Data Governance | Controlar o uso, a segurança e a qualidade dos dados. |
| Dataset Size | Quantidade adequada de dados para o treinamento. |
| Data Labeling | Associar dados às respostas ou categorias esperadas. |
| Representativeness | Representar os cenários reais de utilização. |
| Training | Ensina o modelo. |
| Validation | Ajuda a ajustar o desenvolvimento. |
| Testing | Avalia o modelo com dados não utilizados no treinamento. |
| RLHF | Utiliza feedback humano para orientar o comportamento do modelo. |
| JSONL | Formato de dados em que cada linha contém um objeto JSON. |
| Amazon S3 | Armazenamento dos dados de treinamento. |
| AWS IAM | Controle de acesso aos dados e recursos. |

## ⚠️ PEGADINHAS DE PROVA

- **Pré-treinamento:** grandes volumes de dados para desenvolver capacidades gerais.
- **Fine-tuning:** utiliza um modelo já pré-treinado e o especializa.
- **Continued Pre-training:** continua o aprendizado com novos dados, geralmente não rotulados.
- **Instruction Tuning:** ensina o modelo a seguir instruções utilizando exemplos de entrada e saída.
- **Domain Adaptation:** adapta o modelo a uma área específica, como saúde, direito ou finanças.
- **Transfer Learning:** aproveita conhecimentos aprendidos anteriormente em uma nova tarefa.
- **Distillation:** transfere conhecimento de um modelo professor maior para um modelo aluno menor.
- **Teacher não é o modelo menor.** Teacher ensina; Student aprende.
- **Distilação não significa simplesmente remover camadas do modelo.** É um processo de transferência de conhecimento.
- **Mais dados não significam necessariamente melhor treinamento.** Qualidade e representatividade são fundamentais.
- **Data Curation não é Data Governance.** Curadoria organiza e limpa; governança estabelece políticas e controles.
- **Labeling:** associa exemplos a respostas ou categorias esperadas.
- **Representatividade:** os dados precisam refletir os cenários reais.
- **Training, Validation e Testing têm finalidades diferentes.**
- **RLHF utiliza preferências ou avaliações humanas para orientar o aprendizado.**
- **RLHF não é sinônimo de ajuste fino supervisionado.**
- **JSONL:** cada linha representa um registro JSON independente.
- **Os requisitos de dados do Bedrock variam conforme o modelo e o método escolhido.**

## 🧩 MAPA MENTAL

<pre>
TREINAMENTO E AJUSTE FINO DE FMs
│
├── 1. ELEMENTOS DO TREINAMENTO
│   ├── Pré-treinamento
│   │   └── Conhecimento geral
│   ├── Fine-tuning
│   │   └── Especialização
│   ├── Continued Pre-training
│   │   └── Conhecimento adicional
│   └── Distillation
│       ├── Teacher → Professor
│       └── Student → Aluno menor
│
├── 2. MÉTODOS DE AJUSTE FINO
│   ├── Instruction Tuning
│   │   └── Seguir instruções
│   ├── Domain Adaptation
│   │   └── Domínio específico
│   ├── Transfer Learning
│   │   └── Reutilizar conhecimento
│   └── Continued Pre-training
│       └── Aprendizado adicional
│
└── 3. PREPARAÇÃO DOS DADOS
    ├── Data Curation
    │   └── Selecionar e limpar
    ├── Data Governance
    │   └── Segurança e controle
    ├── Dataset Size
    │   └── Quantidade adequada
    ├── Data Labeling
    │   └── Rótulos corretos
    ├── Representativeness
    │   └── Cenários reais
    ├── Training / Validation / Testing
    │   └── Aprender / Ajustar / Avaliar
    └── RLHF
        ├── Feedback humano
        ├── Preferências
        ├── Recompensas
        └── Alinhamento do modelo
</pre>

## 📚 REFERÊNCIAS OFICIAIS AWS

- [Guia oficial do exame AIF-C01 — Task 3.3](https://docs.aws.amazon.com/pt_br/aws-certification/latest/ai-practitioner-01/ai-practitioner-01-domain3.html)
- [Personalizar modelos no Amazon Bedrock](https://docs.aws.amazon.com/pt_br/bedrock/latest/userguide/custom-models.html)
- [Preparar dados para ajuste fino](https://docs.aws.amazon.com/pt_br/bedrock/latest/userguide/model-customization-prepare.html)
- [Ajuste fino por reforço no Amazon Bedrock](https://docs.aws.amazon.com/pt_br/bedrock/latest/userguide/reinforcement-fine-tuning.html)
- [Destilação de modelos no Amazon Bedrock](https://docs.aws.amazon.com/pt_br/bedrock/latest/userguide/model-distillation.html)
- [Destilação no Amazon SageMaker AI](https://docs.aws.amazon.com/sagemaker/latest/dg/customizing-models-distillation.html)
