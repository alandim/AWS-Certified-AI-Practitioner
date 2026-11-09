## 🧠 AWS AI Practitioner — Tarefa 3.4: Descrever métodos para avaliar o desempenho dos FMs

### 1️⃣ Abordagens para avaliar o desempenho de modelos de base (FMs)

<h3><strong style='color: skyblue'>O que significa avaliar um FM?</strong></h3>

<p align="justify">A avaliação de um modelo de base (Foundation Model — FM) consiste em medir a qualidade, a precisão, a relevância, a segurança e a capacidade do modelo de executar as tarefas para as quais foi selecionado.</p>

<p align="justify">O objetivo é verificar se o modelo atende aos requisitos técnicos e empresariais, comparando seus resultados com critérios definidos, conjuntos de dados de referência ou avaliações humanas.</p>

**Principais aspectos avaliados:**
- Precisão (Accuracy): qualidade e correção das respostas.
- Relevância (Relevance): relação da resposta com a pergunta.
- Completude (Completeness): se a resposta cobre todos os pontos solicitados.
- Fidelidade (Faithfulness): se a resposta está fundamentada nas informações fornecidas.
- Robustez (Robustness): capacidade de manter o desempenho diante de variações nas entradas.
- Segurança (Safety): capacidade de evitar conteúdo prejudicial.
- Toxicidade (Toxicity): presença de linguagem ofensiva ou prejudicial.
- Viés (Bias): presença de respostas tendenciosas ou discriminatórias.
- Latência (Latency): tempo necessário para produzir uma resposta.
- Custo (Cost): recursos financeiros utilizados para executar o modelo.

> **DECORA:** Avaliar um FM não significa apenas verificar se a resposta está correta. Também é necessário analisar relevância, segurança, consistência, desempenho e custo.

<h3><strong style='color: skyblue'>Avaliação humana (Human Evaluation / Human-in-the-Loop)</strong></h3>

<p align="justify">Consiste em utilizar pessoas para analisar e classificar as respostas produzidas pelo modelo. Os avaliadores verificam se as respostas atendem aos critérios definidos para a aplicação.</p>

**O que pode ser avaliado:**
- Precisão e correção.
- Clareza e compreensão.
- Relevância.
- Completude.
- Tom e estilo.
- Utilidade para o usuário.
- Adequação ao contexto.
- Segurança e ausência de conteúdo prejudicial.

**Exemplo:**

Uma empresa está avaliando dois modelos para atendimento ao cliente.

| Critério | Modelo A | Modelo B |
|---|---|---|
| Clareza | Boa | Excelente |
| Precisão | Excelente | Boa |
| Tom profissional | Bom | Excelente |
| Completude | Boa | Excelente |

Os avaliadores humanos podem identificar que o Modelo A é mais preciso, enquanto o Modelo B oferece uma experiência mais agradável.

**Vantagens:**
- Permite avaliar características subjetivas.
- Considera o contexto da resposta.
- Identifica problemas difíceis de medir automaticamente.
- Permite utilizar especialistas do domínio.

**Limitações:**
- Pode ser demorada.
- Pode apresentar custos elevados.
- Pode existir divergência entre avaliadores.
- Pode sofrer influência de preferências e vieses humanos.

> **DECORA:** Human Evaluation = pessoas avaliam diretamente a qualidade das respostas.

<h3><strong style='color: skyblue'>Conjuntos de dados de referência (Benchmark Datasets)</strong></h3>

<p align="justify">São conjuntos de dados padronizados utilizados para avaliar e comparar o desempenho de modelos em tarefas específicas.</p>

<p align="justify">Normalmente, contêm entradas de teste e respostas esperadas ou critérios de avaliação. Permitem executar os mesmos testes em diferentes modelos e comparar seus resultados.</p>

**Exemplo:**

Uma empresa deseja comparar três modelos para classificação de solicitações de suporte.

Utiliza um conjunto com 1.000 solicitações previamente classificadas por especialistas.

Cada modelo recebe as mesmas entradas e suas classificações são comparadas com os resultados esperados.

**Vantagens:**
- Permite comparações consistentes.
- Facilita testes repetíveis.
- Ajuda a identificar melhorias ou regressões.
- Permite comparar diferentes modelos.
- Ajuda a avaliar tarefas específicas.

**Limitações:**
- Um benchmark pode não representar situações reais.
- Pode conter dados desatualizados.
- Pode favorecer modelos treinados com dados semelhantes.
- Um bom resultado no benchmark não garante bom desempenho em produção.

> **DECORA:** Benchmark = conjunto padronizado de testes para comparar modelos.

<h3><strong style='color: skyblue'>Amazon Bedrock Model Evaluation</strong></h3>

<p align="justify">O Amazon Bedrock Model Evaluation é um recurso que permite avaliar e comparar modelos de base utilizando avaliações automáticas ou humanas.</p>

<p align="justify">Ele ajuda a identificar qual modelo atende melhor a determinado caso de uso, utilizando conjuntos de dados e métricas de avaliação.</p>

**Principais possibilidades:**

- Comparar diferentes modelos.
- Avaliar modelos personalizados.
- Utilizar conjuntos de dados próprios.
- Utilizar conjuntos de dados selecionados para avaliação.
- Executar avaliações automáticas.
- Configurar avaliações humanas.
- Utilizar LLM-as-a-Judge.
- Comparar resultados de diferentes avaliações.

**Tipos de avaliação:**

| Tipo | Característica | Quando utilizar |
|---|---|---|
| Automática (Programmatic) | Utiliza métricas e algoritmos para avaliar resultados. | Quando é necessário avaliar rapidamente grandes volumes de respostas. |
| Humana (Human) | Utiliza pessoas para analisar as respostas. | Quando critérios subjetivos são importantes. |
| LLM-as-a-Judge | Utiliza outro modelo de linguagem como avaliador. | Quando é necessário escalar avaliações de qualidade. |

**Exemplo prático:**

Uma empresa deseja selecionar um modelo para responder perguntas sobre seus produtos.

1. Seleciona os modelos candidatos.
2. Prepara um conjunto de perguntas.
3. Executa avaliações.
4. Compara precisão, relevância e completude.
5. Analisa os resultados.
6. Escolhe o modelo mais adequado.

> **DECORA:** Amazon Bedrock Model Evaluation = avaliar e comparar modelos para selecionar o mais adequado ao caso de uso.

<h3><strong style='color: skyblue'>LLM-as-a-Judge — Modelo de linguagem como avaliador</strong></h3>

<p align="justify">É uma abordagem em que um modelo de linguagem é utilizado para avaliar as respostas produzidas por outro modelo. O avaliador recebe critérios e pode atribuir pontuações ou justificativas para cada resposta.</p>

**Como funciona:**

```text
       PERGUNTA DO USUÁRIO
                |
                v
        MODELO A GERA
           RESPOSTA
                |
                v
       RESPOSTA PRODUZIDA
                |
                v
        MODELO AVALIADOR
         (LLM-as-a-Judge)
                |
                v
       AVALIAÇÃO POR CRITÉRIOS
       ├── Precisão
       ├── Relevância
       ├── Completude
       ├── Fidelidade
       └── Segurança
                |
                v
         NOTA E JUSTIFICATIVA
```

**Vantagens:**
- Permite avaliar grandes volumes de respostas.
- Reduz a necessidade de avaliação humana em todas as interações.
- Pode utilizar critérios personalizados.
- Facilita comparações entre modelos e versões.

**Limitações:**
- O modelo avaliador também pode cometer erros.
- Pode apresentar vieses.
- Pode favorecer respostas mais longas.
- Pode interpretar incorretamente determinados contextos.
- Não substitui completamente a avaliação humana.

> **DECORA:** LLM-as-a-Judge = um modelo avalia as respostas de outro modelo.

<h3><strong style='color: skyblue'>Comparação das abordagens de avaliação</strong></h3>

| Abordagem | Principal vantagem | Principal limitação |
|---|---|---|
| Avaliação humana | Julgamento contextual e subjetivo. | Custo e tempo. |
| Benchmark | Comparação padronizada e repetível. | Pode não refletir o ambiente real. |
| Avaliação automática | Rapidez e escalabilidade. | Depende das métricas escolhidas. |
| LLM-as-a-Judge | Avaliação escalável de qualidade. | Pode apresentar vieses e erros. |
| Bedrock Model Evaluation | Centraliza diferentes métodos de avaliação. | Depende da configuração e dos dados utilizados. |

> **PEGADINHA:** Benchmark é um conjunto de testes; avaliação humana é uma abordagem; LLM-as-a-Judge é uma técnica de avaliação; Amazon Bedrock Model Evaluation é o recurso AWS que permite organizar avaliações.

---

### 2️⃣ Métricas para avaliar o desempenho de FMs

<h3><strong style='color: skyblue'>O que são métricas de avaliação?</strong></h3>

<p align="justify">Métricas são medidas utilizadas para quantificar ou classificar o desempenho de um modelo. Elas ajudam a determinar se as respostas geradas atendem aos critérios esperados para determinada tarefa.</p>

<p align="justify">Cada métrica possui uma finalidade. Algumas comparam palavras e expressões; outras analisam similaridade semântica ou utilizam modelos para avaliar a qualidade das respostas.</p>

<h3><strong style='color: skyblue'>ROUGE — Recall-Oriented Understudy for Gisting Evaluation</strong></h3>

<p align="justify">ROUGE é uma família de métricas utilizada principalmente para avaliar tarefas de resumo de texto. Compara o conteúdo gerado pelo modelo com um ou mais textos de referência, verificando a sobreposição de palavras e sequências de palavras.</p>

**Principal aplicação:**
- Resumo de documentos.
- Resumo de relatórios.
- Síntese de notícias.
- Comparação de textos resumidos.

**Exemplo:**

Texto de referência:
```text
A empresa reduziu os custos operacionais
e aumentou sua receita.
```

Resumo gerado:
```text
A empresa diminuiu as despesas
e aumentou a receita.
```

A redação é diferente, mas existe sobreposição de palavras e informações.

**Características:**
- Avalia a sobreposição entre o texto gerado e o texto de referência.
- Dá atenção à cobertura do conteúdo de referência.
- Pode utilizar correspondência de palavras ou sequências de palavras.
- Não compreende perfeitamente o significado do texto.

> **DECORA:** ROUGE = avaliação de resumos, com foco na cobertura do conteúdo de referência.

<h3><strong style='color: skyblue'>BLEU — Bilingual Evaluation Understudy</strong></h3>

<p align="justify">BLEU é uma métrica tradicionalmente utilizada para avaliar a qualidade de traduções automáticas. Compara o texto produzido pelo modelo com traduções de referência, verificando a correspondência de palavras e sequências de palavras.</p>

**Principal aplicação:**
- Tradução automática.
- Avaliação de sistemas multilíngues.
- Comparação de textos traduzidos.

**Exemplo:**

Texto de referência:
```text
The company increased its revenue.
```

Tradução gerada:
```text
A empresa aumentou sua receita.
```

O BLEU compara a tradução produzida com traduções de referência para medir a correspondência textual.

**Características:**
- Avalia correspondência de palavras e sequências.
- Tradicionalmente utilizado em tradução automática.
- Considera penalização para respostas excessivamente curtas.
- Não avalia perfeitamente o significado ou a qualidade contextual.

> **DECORA:** BLEU = avaliação de traduções, com foco na correspondência textual com referências.

<h3><strong style='color: skyblue'>BERTScore</strong></h3>

<p align="justify">BERTScore é uma métrica que utiliza representações contextuais de modelos baseados em BERT para comparar o significado das palavras e dos textos gerados com os textos de referência.</p>

<p align="justify">Diferentemente de métricas baseadas apenas na correspondência literal de palavras, considera similaridade semântica. Assim, textos com palavras diferentes podem receber pontuações semelhantes quando expressam significados próximos.</p>

**Exemplo:**

Texto de referência:
```text
O cliente cancelou o pedido.
```

Texto gerado:
```text
O consumidor desistiu da compra.
```

As palavras são diferentes, mas o significado é semelhante.

**Características:**
- Utiliza representações contextuais.
- Considera similaridade semântica.
- É menos dependente de correspondência literal.
- Pode ser útil em tarefas de geração de texto.
- Não garante que a resposta seja factualmente correta.

> **DECORA:** BERTScore = compara similaridade semântica, não apenas palavras iguais.

<h3><strong style='color: skyblue'>LLM-as-a-Judge como métrica de avaliação</strong></h3>

<p align="justify">LLM-as-a-Judge também pode ser utilizado para avaliar dimensões de qualidade que são difíceis de medir apenas por correspondência textual.</p>

O modelo avaliador pode analisar critérios como:

| Métrica | O que avalia |
|---|---|
| Correctness | Se a resposta está correta. |
| Completeness | Se responde a todos os pontos solicitados. |
| Faithfulness | Se permanece fiel ao contexto fornecido. |
| Helpfulness | Se a resposta é útil para o usuário. |
| Relevance | Se responde ao que foi perguntado. |
| Coherence | Se apresenta lógica e consistência. |
| Following Instructions | Se respeita as instruções. |
| Harmfulness | Se apresenta conteúdo prejudicial. |
| Stereotyping | Se apresenta estereótipos. |
| Refusal | Se o modelo recusa responder. |

**Exemplo:**

Uma aplicação RAG responde a uma pergunta utilizando documentos empresariais.

O modelo avaliador pode verificar:
- Se a resposta está correta.
- Se todas as partes da pergunta foram respondidas.
- Se a resposta está fundamentada nos documentos.
- Se existem informações inventadas.

> **DECORA:** LLM-as-a-Judge permite avaliar qualidade, relevância, fidelidade, completude e segurança usando outro modelo.

<h3><strong style='color: skyblue'>Comparação: ROUGE × BLEU × BERTScore × LLM-as-a-Judge</strong></h3>

| Métrica | Foco principal | Aplicação típica |
|---|---|---|
| ROUGE | Cobertura e sobreposição textual. | Resumos. |
| BLEU | Correspondência textual. | Traduções. |
| BERTScore | Similaridade semântica. | Comparação de textos com palavras diferentes. |
| LLM-as-a-Judge | Avaliação contextual e qualitativa. | Correção, completude, fidelidade e utilidade. |

**Exemplo para memorizar:**

- Preciso avaliar um resumo? ROUGE.
- Preciso avaliar uma tradução? BLEU.
- Preciso comparar significados semelhantes com palavras diferentes? BERTScore.
- Preciso que outro modelo avalie se a resposta é correta, útil e completa? LLM-as-a-Judge.

> **PEGADINHA:** ROUGE, BLEU e BERTScore não garantem que uma resposta seja verdadeira. Uma resposta pode ter alta similaridade textual e ainda conter informações incorretas.

---

### 3️⃣ Avaliar se o FM atende aos objetivos empresariais

<h3><strong style='color: skyblue'>Desempenho técnico versus valor empresarial</strong></h3>

<p align="justify">Um modelo pode apresentar excelentes resultados técnicos e ainda não atender às necessidades de uma organização. A avaliação precisa verificar se o modelo gera valor para o negócio, melhora processos e atende às expectativas dos usuários.</p>

**Exemplo:**

Uma empresa utiliza IA generativa para automatizar o atendimento ao cliente.

O modelo apresenta:
- Respostas rápidas.
- Boa precisão.
- Alta disponibilidade.

Entretanto, os clientes continuam solicitando atendimento humano e o custo por interação permanece elevado.

Nesse cenário, o modelo apresenta bom desempenho técnico, mas talvez não esteja atingindo os objetivos empresariais.

> **DECORA:** Um modelo tecnicamente bom não é necessariamente um modelo que gera valor para o negócio.

<h3><strong style='color: skyblue'>Produtividade (Productivity)</strong></h3>

<p align="justify">Avalia se a aplicação de IA permite que funcionários executem atividades com maior eficiência, reduzindo o tempo e o esforço necessários para concluir tarefas.</p>

**Indicadores:**
- Tempo economizado.
- Quantidade de tarefas concluídas.
- Redução de atividades manuais.
- Aumento da produtividade por funcionário.
- Redução do tempo de processamento.
- Redução de erros operacionais.

**Exemplo:**

Uma empresa utiliza IA para resumir relatórios técnicos.

Antes:
- Um funcionário gastava 40 minutos por relatório.

Depois:
- O funcionário gasta 10 minutos revisando o resumo gerado.

A aplicação reduz o tempo de trabalho e aumenta a capacidade de processamento.

> **DECORA:** Produtividade = fazer mais em menos tempo ou reduzir o esforço para realizar uma tarefa.

<h3><strong style='color: skyblue'>Envolvimento dos usuários (User Engagement)</strong></h3>

<p align="justify">Mede o nível de interação dos usuários com uma aplicação de IA e o quanto eles utilizam e retornam ao serviço.</p>

**Indicadores:**
- Número de usuários ativos.
- Frequência de utilização.
- Número de interações por usuário.
- Taxa de retorno.
- Tempo de utilização.
- Taxa de abandono.
- Satisfação dos usuários.

**Exemplo:**

Uma empresa disponibiliza um assistente virtual para seus clientes.

Após a implantação, observa:
- Mais usuários utilizando o assistente.
- Maior frequência de interação.
- Menor taxa de abandono.
- Maior satisfação.

Esses resultados indicam maior envolvimento dos usuários.

> **DECORA:** User Engagement = medir quanto os usuários interagem e continuam utilizando a aplicação.

<h3><strong style='color: skyblue'>Engenharia de tarefas (Task Engineering)</strong></h3>

<p align="justify">No contexto de aplicações com FMs, é importante avaliar se o modelo consegue executar de maneira eficaz as tarefas específicas para as quais foi projetado. Isso envolve verificar a adequação entre o objetivo da tarefa, as instruções, os dados e os resultados produzidos.</p>

**Exemplos de tarefas:**
- Classificar chamados.
- Resumir documentos.
- Extrair informações.
- Responder perguntas.
- Gerar relatórios.
- Traduzir textos.
- Executar etapas de um processo.

**O que avaliar:**
- Se o modelo executa a tarefa solicitada.
- Se respeita as instruções.
- Se produz o formato esperado.
- Se consegue lidar com diferentes entradas.
- Se mantém qualidade em situações variadas.
- Se conclui a tarefa com o nível de precisão necessário.

**Exemplo:**

Uma empresa utiliza um FM para classificar chamados de infraestrutura.

A avaliação verifica:
- Se a categoria está correta.
- Se a prioridade foi atribuída adequadamente.
- Se as informações relevantes foram extraídas.
- Se o formato da resposta atende ao sistema de chamados.

> **DECORA:** Task Engineering = verificar se o modelo está adequado à tarefa específica e consegue executá-la conforme os requisitos.

<h3><strong style='color: skyblue'>Alinhamento entre modelo e objetivos do negócio</strong></h3>

<p align="justify">A seleção de um FM deve considerar os resultados esperados pela organização. O modelo escolhido precisa apresentar desempenho adequado, custos sustentáveis e capacidade de atender aos requisitos da aplicação.</p>

**Exemplo de critérios empresariais:**

| Objetivo | Indicador |
|---|---|
| Aumentar produtividade | Tempo economizado por tarefa. |
| Melhorar atendimento | Satisfação dos clientes. |
| Automatizar processos | Taxa de conclusão de tarefas. |
| Reduzir custos | Custo por interação. |
| Aumentar utilização | Usuários ativos e frequência de uso. |
| Melhorar qualidade | Precisão e taxa de erros. |

> **DECORA:** A melhor escolha é o modelo que atende aos requisitos do negócio considerando qualidade, custo, desempenho e experiência do usuário.

---

### 4️⃣ Avaliar aplicações construídas com FMs: RAG, agentes e fluxos de trabalho

<h3><strong style='color: skyblue'>Avaliação de aplicações com IA generativa</strong></h3>

<p align="justify">Avaliar apenas o modelo de base não é suficiente. Uma aplicação pode combinar modelos, bancos de dados, mecanismos de recuperação, ferramentas externas e fluxos de trabalho.</p>

<p align="justify">Por isso, é necessário avaliar o desempenho de cada componente e também o resultado final da aplicação.</p>

**Exemplos de aplicações:**
- RAG (Retrieval-Augmented Generation).
- Agentes de IA (AI Agents).
- Fluxos de trabalho (Workflows).

<h3><strong style='color: skyblue'>Avaliação de RAG</strong></h3>

<p align="justify">RAG combina recuperação de informações em fontes externas com geração de respostas por um modelo de base. Sua avaliação deve verificar tanto a qualidade da recuperação quanto a qualidade da resposta gerada.</p>

**Fluxo de avaliação:**

```text
        PERGUNTA DO USUÁRIO
                |
                v
       MECANISMO DE RECUPERAÇÃO
                |
                v
       DOCUMENTOS RECUPERADOS
                |
                v
        MODELO DE LINGUAGEM
                |
                v
         RESPOSTA GERADA
                |
                v
          AVALIAÇÃO
```

**O que avaliar na recuperação:**
- Relevância dos documentos recuperados.
- Cobertura das informações necessárias.
- Precisão dos resultados.
- Capacidade de localizar informações corretas.

**O que avaliar na geração:**
- Correção da resposta.
- Completude.
- Fidelidade aos documentos.
- Ausência de alucinações.
- Qualidade das citações.
- Relevância para a pergunta.

**Métricas importantes no Amazon Bedrock RAG Evaluation:**

| Métrica | O que avalia |
|---|---|
| Context Relevance | Relevância dos textos recuperados em relação à pergunta. |
| Context Coverage | Quanto do conteúdo de referência foi coberto pelos textos recuperados. |
| Correctness | Correção da resposta gerada. |
| Completeness | Se a resposta cobre todos os aspectos da pergunta. |
| Faithfulness | Se a resposta permanece fiel ao contexto recuperado. |
| Helpfulness | Utilidade da resposta. |
| Citation Precision | Se as citações utilizadas estão corretas. |
| Citation Coverage | Se a resposta está adequadamente sustentada pelas citações. |

**Exemplo:**

Uma empresa possui uma base de conhecimento com documentos técnicos.

O usuário pergunta como resolver uma falha de autenticação.

A avaliação verifica:
1. Se os documentos corretos foram recuperados.
2. Se as informações recuperadas cobrem a pergunta.
3. Se o modelo gerou uma solução correta.
4. Se a resposta está fundamentada nos documentos.
5. Se as citações apontam para as fontes adequadas.

**Na AWS:**
- Amazon Bedrock Knowledge Bases.
- Amazon Bedrock Evaluations.

> **DECORA:** RAG precisa ser avaliado em duas partes: recuperação (retrieval) e geração (generation).

<h3><strong style='color: skyblue'>Avaliação de agentes de IA (AI Agents)</strong></h3>

<p align="justify">Agentes de IA podem interpretar solicitações, planejar etapas, selecionar ferramentas e executar ações. Sua avaliação precisa considerar não apenas a qualidade textual das respostas, mas também a execução correta das tarefas.</p>

**O que avaliar:**
- Seleção correta de ferramentas.
- Execução correta das ações.
- Conclusão das tarefas.
- Precisão das informações.
- Quantidade de etapas executadas.
- Tempo de execução.
- Custo das chamadas aos modelos e ferramentas.
- Tratamento de erros.
- Respeito às permissões e políticas.

**Exemplo:**

Um agente recebe a solicitação de consultar o status de um pedido.

O processo pode envolver:
1. Interpretar a solicitação.
2. Consultar uma API.
3. Localizar o pedido.
4. Recuperar o status.
5. Informar o resultado ao usuário.

A avaliação verifica se o agente utilizou a ferramenta correta, recuperou os dados corretos e concluiu a tarefa.

**Métricas possíveis:**
- Taxa de conclusão de tarefas.
- Taxa de sucesso das chamadas de ferramentas.
- Taxa de erros.
- Número de etapas por tarefa.
- Latência total.
- Custo por execução.

> **DECORA:** Agentes devem ser avaliados pela capacidade de executar ações e concluir tarefas, não apenas pela qualidade das respostas.

<h3><strong style='color: skyblue'>Avaliação de fluxos de trabalho (Workflows)</strong></h3>

<p align="justify">Workflows são sequências organizadas de etapas que podem integrar modelos de IA, serviços e sistemas externos. A avaliação verifica se cada etapa e o fluxo completo funcionam conforme o esperado.</p>

**O que avaliar:**
- Sucesso de cada etapa.
- Sucesso do fluxo completo.
- Tempo total de execução.
- Tratamento de falhas.
- Consistência dos resultados.
- Integração entre serviços.
- Custo total do processo.

**Exemplo:**

Uma empresa utiliza um fluxo para processar documentos:

```text
       DOCUMENTO RECEBIDO
                |
                v
       EXTRAÇÃO DE TEXTO
                |
                v
        CLASSIFICAÇÃO COM IA
                |
                v
        EXTRAÇÃO DE DADOS
                |
                v
        VALIDAÇÃO DOS DADOS
                |
                v
        ARMAZENAMENTO
                |
                v
        PROCESSO CONCLUÍDO
```

A avaliação verifica:
- Se o documento foi recebido.
- Se o texto foi extraído corretamente.
- Se a classificação foi adequada.
- Se os dados foram extraídos sem erros.
- Se a validação funcionou.
- Se o processo foi concluído.

**Na AWS:**
- Amazon Bedrock Flows.
- AWS Step Functions.
- AWS Lambda.
- Amazon CloudWatch.

> **DECORA:** Workflow = avaliar cada etapa e o resultado final do processo.

<h3><strong style='color: skyblue'>Comparação: RAG × Agentes × Workflows</strong></h3>

| Aplicação | Principal foco da avaliação |
|---|---|
| RAG | Qualidade da recuperação e fidelidade da resposta. |
| Agentes | Seleção de ferramentas, execução de ações e conclusão de tarefas. |
| Workflows | Funcionamento das etapas e sucesso do processo completo. |

**Para memorizar:**
- RAG: recuperou a informação correta e respondeu corretamente?
- Agente: escolheu as ferramentas certas e concluiu a tarefa?
- Workflow: todas as etapas foram executadas corretamente?

---

### 5️⃣ Métricas de alinhamento aos objetivos empresariais para aplicações de IA

<h3><strong style='color: skyblue'>Taxa de conclusão de tarefas (Task Completion Rate)</strong></h3>

<p align="justify">Mede a proporção de tarefas que a aplicação consegue concluir com sucesso em relação ao total de tarefas solicitadas.</p>

**Fórmula:**

\[
\text{Taxa de conclusão} =
\frac{\text{Tarefas concluídas com sucesso}}
{\text{Total de tarefas solicitadas}}
\times 100
\]

**Exemplo:**

Uma aplicação recebeu 1.000 solicitações e concluiu 850 corretamente.

\[
\frac{850}{1000}\times100=85\%
\]

<badge color="success">Resultado: 85%</badge>

**Interpretação:**
- Taxa elevada: maior capacidade de concluir tarefas.
- Taxa baixa: pode indicar falhas no modelo, nas ferramentas ou no fluxo de trabalho.

> **DECORA:** Task Completion Rate = percentual de tarefas concluídas com sucesso.

<h3><strong style='color: skyblue'>Satisfação do usuário (User Satisfaction)</strong></h3>

<p align="justify">Mede o nível de satisfação dos usuários com a experiência oferecida pela aplicação de IA.</p>

**Formas de medição:**
- Pesquisas de satisfação.
- Avaliações por estrelas.
- Questionários após o atendimento.
- Feedback direto.
- Indicadores como CSAT e NPS.

**Exemplo:**

Após uma interação com um assistente virtual, o usuário responde:

"Qual seu nível de satisfação com o atendimento?"

A empresa utiliza as respostas para identificar problemas e oportunidades de melhoria.

**Indicadores relacionados:**
- CSAT: Customer Satisfaction Score.
- NPS: Net Promoter Score.
- Taxa de reclamações.
- Taxa de abandono.

> **DECORA:** User Satisfaction = medir a percepção e satisfação dos usuários.

<h3><strong style='color: skyblue'>Custo por interação (Cost per Interaction)</strong></h3>

<p align="justify">Mede o custo médio para processar uma interação ou solicitação utilizando a aplicação de IA.</p>

**Fórmula simplificada:**

\[
\text{Custo por interação} =
\frac{\text{Custo total das interações}}
{\text{Número de interações}}
\]

**Exemplo:**

Uma aplicação gastou R$ 500 para processar 1.000 interações.

\[
\frac{500}{1000}=R\$0,50
\]

<badge color="success">Resultado: R$ 0,50 por interação</badge>

**Custos que podem ser considerados:**
- Tokens de entrada.
- Tokens de saída.
- Chamadas aos modelos.
- Recuperação de informações.
- Execução de ferramentas.
- Infraestrutura.
- Armazenamento e processamento.

> **DECORA:** Cost per Interaction = custo médio de cada interação com a aplicação.

<h3><strong style='color: skyblue'>Produtividade e eficiência</strong></h3>

<p align="justify">Avaliam se a aplicação reduz o esforço necessário para executar atividades e melhora a capacidade operacional da organização.</p>

**Indicadores:**
- Tempo médio por tarefa.
- Tarefas processadas por hora.
- Horas de trabalho economizadas.
- Redução de tarefas manuais.
- Redução de erros.
- Aumento de produtividade por funcionário.

**Exemplo:**

Uma aplicação reduziu o tempo de análise de documentos de 30 minutos para 5 minutos.

A empresa consegue processar mais documentos com o mesmo número de funcionários.

<h3><strong style='color: skyblue'>Envolvimento e retenção dos usuários</strong></h3>

<p align="justify">Avaliam se os usuários continuam utilizando a aplicação e se ela consegue manter uma interação relevante ao longo do tempo.</p>

**Indicadores:**
- Usuários ativos diários ou mensais.
- Frequência de utilização.
- Número de interações por usuário.
- Taxa de retorno.
- Retenção de usuários.
- Taxa de abandono.

**Exemplo:**

Uma aplicação apresenta muitos acessos iniciais, mas poucos usuários retornam após a primeira utilização.

Isso pode indicar problemas de experiência, utilidade ou qualidade das respostas.

<h3><strong style='color: skyblue'>Retorno sobre investimento (ROI)</strong></h3>

<p align="justify">Mede se os benefícios financeiros gerados pela aplicação compensam os investimentos realizados para desenvolvê-la, operá-la e mantê-la.</p>

**Fórmula:**

\[
ROI =
\frac{\text{Benefícios financeiros} - \text{Custos}}
{\text{Custos}}
\times 100
\]

**Exemplo:**

Uma empresa investiu R$ 20.000 em uma aplicação de IA e obteve R$ 30.000 em benefícios financeiros.

\[
ROI =
\frac{30.000-20.000}{20.000}
\times100
=50\%
\]

<badge color="success">Resultado: ROI de 50%</badge>

> **DECORA:** ROI = verificar se os benefícios financeiros superam os custos do investimento.

<h3><strong style='color: skyblue'>Comparação das métricas empresariais</strong></h3>

| Métrica | Pergunta que responde |
|---|---|
| Task Completion Rate | Quantas tarefas foram concluídas corretamente? |
| User Satisfaction | Os usuários estão satisfeitos? |
| Cost per Interaction | Quanto custa cada interação? |
| Productivity | A aplicação economiza tempo e esforço? |
| User Engagement | Os usuários interagem com a aplicação? |
| Retention Rate | Os usuários continuam utilizando a aplicação? |
| ROI | O investimento gera retorno financeiro? |
| Accuracy | As respostas estão corretas? |
| Latency | Quanto tempo a aplicação demora para responder? |

<h3><strong style='color: skyblue'>Exemplo integrado: avaliação de um assistente de atendimento</strong></h3>

Uma empresa implementa um assistente de IA para atendimento ao cliente.

Após um período de avaliação, obtém:

| Indicador | Resultado |
|---|---:|
| Solicitações recebidas | 10.000 |
| Tarefas concluídas corretamente | 8.500 |
| Taxa de conclusão | 85% |
| Satisfação dos usuários | 90% |
| Custo total | R$ 2.000 |
| Custo por interação | R$ 0,20 |
| Tempo médio de resposta | 3 segundos |

**Interpretação:**

- 85% das solicitações foram concluídas corretamente.
- 90% de satisfação indica boa percepção dos usuários.
- R$ 0,20 por interação permite analisar a eficiência financeira.
- Três segundos de resposta permitem avaliar a experiência e a latência.

<p align="justify">A decisão de manter ou ampliar a aplicação deve considerar todos esses indicadores em conjunto, e não apenas a precisão do modelo.</p>

> **DECORA:** O sucesso de uma aplicação de IA depende de desempenho técnico, experiência do usuário e resultados empresariais.

---

## 🎯 DECORAÇÃO FINAL

| Conceito | O que lembrar |
|---|---|
| Human Evaluation | Pessoas avaliam a qualidade das respostas. |
| Benchmark Dataset | Conjunto padronizado para comparar modelos. |
| Amazon Bedrock Model Evaluation | Serviço para avaliar e comparar modelos. |
| LLM-as-a-Judge | Um modelo avalia as respostas de outro. |
| ROUGE | Avaliação de resumos e cobertura textual. |
| BLEU | Avaliação de traduções e correspondência textual. |
| BERTScore | Similaridade semântica entre textos. |
| Correctness | Correção da resposta. |
| Completeness | Cobertura de todos os pontos solicitados. |
| Faithfulness | Fidelidade ao contexto e às fontes. |
| Relevance | Relação da resposta com a pergunta. |
| Helpfulness | Utilidade para o usuário. |
| Productivity | Economia de tempo e esforço. |
| User Engagement | Nível de interação dos usuários. |
| Task Engineering | Adequação do modelo à tarefa específica. |
| RAG Evaluation | Avaliar recuperação e geração. |
| Agent Evaluation | Avaliar ferramentas, ações e conclusão de tarefas. |
| Workflow Evaluation | Avaliar etapas e processo completo. |
| Task Completion Rate | Percentual de tarefas concluídas com sucesso. |
| User Satisfaction | Satisfação dos usuários. |
| Cost per Interaction | Custo médio por interação. |
| ROI | Retorno financeiro do investimento. |
| Latency | Tempo de resposta. |
| Robustness | Capacidade de lidar com variações nas entradas. |

## ⚠️ PEGADINHAS DE PROVA

- **ROUGE:** lembre-se de resumo de texto.
- **BLEU:** lembre-se de tradução automática.
- **BERTScore:** lembre-se de similaridade semântica.
- **LLM-as-a-Judge:** outro modelo avalia a resposta.
- **Human Evaluation:** pessoas avaliam diretamente as respostas.
- **Benchmark:** conjunto padronizado para comparação.
- **Amazon Bedrock Model Evaluation:** permite avaliações automáticas e humanas.
- **Uma métrica alta não garante qualidade total.** É necessário considerar o objetivo e o contexto.
- **ROUGE e BLEU não avaliam perfeitamente o significado.**
- **BERTScore não garante precisão factual.**
- **LLM-as-a-Judge também pode apresentar vieses e erros.**
- **RAG:** avaliar recuperação e geração separadamente.
- **Agentes:** avaliar seleção de ferramentas, execução de ações e conclusão das tarefas.
- **Workflows:** avaliar as etapas e o resultado do processo completo.
- **Produtividade:** mede economia de tempo e esforço.
- **User Engagement:** mede interação e utilização.
- **Task Completion Rate:** mede tarefas concluídas com sucesso.
- **User Satisfaction:** mede a satisfação dos usuários.
- **Cost per Interaction:** mede o custo médio por interação.
- **ROI:** mede o retorno financeiro do investimento.

## 🧩 MAPA MENTAL

<pre>
AVALIAÇÃO DE FMs
│
├── 1. ABORDAGENS
│   ├── Human Evaluation
│   │   └── Pessoas avaliam
│   ├── Benchmark Datasets
│   │   └── Testes padronizados
│   ├── Avaliação automática
│   │   └── Métricas programáticas
│   ├── LLM-as-a-Judge
│   │   └── Modelo avaliador
│   └── Amazon Bedrock Model Evaluation
│       └── Comparação e avaliação
│
├── 2. MÉTRICAS
│   ├── ROUGE
│   │   └── Resumos
│   ├── BLEU
│   │   └── Traduções
│   ├── BERTScore
│   │   └── Similaridade semântica
│   └── LLM-as-a-Judge
│       ├── Correção
│       ├── Completude
│       ├── Fidelidade
│       └── Relevância
│
├── 3. OBJETIVOS EMPRESARIAIS
│   ├── Produtividade
│   ├── Envolvimento dos usuários
│   └── Engenharia de tarefas
│
├── 4. APLICAÇÕES
│   ├── RAG
│   │   ├── Recuperação
│   │   └── Geração
│   ├── Agentes
│   │   ├── Ferramentas
│   │   ├── Ações
│   │   └── Conclusão
│   └── Workflows
│       ├── Etapas
│       └── Processo completo
│
└── 5. MÉTRICAS DE NEGÓCIO
    ├── Task Completion Rate
    ├── User Satisfaction
    ├── Cost per Interaction
    ├── Productivity
    ├── User Engagement
    ├── Retention Rate
    └── ROI
</pre>

## 📚 REFERÊNCIAS OFICIAIS AWS

- [Guia oficial do exame AIF-C01 — Task 3.4](https://docs.aws.amazon.com/aws-certification/latest/ai-practitioner-01/ai-practitioner-01-domain3.html)
- [Amazon Bedrock Model Evaluation](https://docs.aws.amazon.com/bedrock/latest/userguide/evaluation.html)
- [Métricas para avaliar modelos no Amazon Bedrock](https://docs.aws.amazon.com/bedrock/latest/userguide/model-evaluation-metrics.html)
- [Métricas para avaliar sistemas RAG no Amazon Bedrock](https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base-evaluation-metrics.html)
- [Amazon Bedrock Evaluations — visão geral](https://aws.amazon.com/bedrock/evaluations/)
