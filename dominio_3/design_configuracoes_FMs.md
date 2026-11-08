## Declaração de tarefa 3.1 — Descrever as considerações sobre design de aplicações que usam modelos de base (FMs)

### 1️⃣ Identificar os critérios de seleção para escolher modelos de base pré-treinados (FMs)

<h3><strong style='color: skyblue'>Custo (Cost)</strong></h3>

<p align="justify">O custo é um dos principais critérios para selecionar um modelo de base. É necessário avaliar o valor de utilização do modelo, o volume de solicitações, a quantidade de tokens processados e os recursos necessários para executar a aplicação.</p>

**Fatores que influenciam o custo:**
- Preço dos tokens de entrada (Input Tokens).
- Preço dos tokens de saída (Output Tokens).
- Tamanho e complexidade do modelo.
- Volume de requisições.
- Necessidade de personalização.
- Infraestrutura para implantação.
- Armazenamento e processamento de dados.

**Exemplo:**

Uma aplicação de perguntas frequentes pode utilizar um modelo menor e mais econômico, enquanto uma aplicação de análise complexa pode justificar um modelo mais avançado e caro.

> **DECORA:** O modelo mais caro não é necessariamente o melhor. Escolha aquele que atende aos requisitos com o menor custo adequado.

<h3><strong style='color: skyblue'>Modalidade (Modality)</strong></h3>

<p align="justify">A modalidade representa os tipos de dados que o modelo consegue receber e gerar. A escolha depende do conteúdo utilizado pela aplicação.</p>

| Modalidade | Aplicação |
|---|---|
| Texto | Chatbots, resumos e tradução |
| Imagem | Geração e análise de imagens |
| Áudio | Transcrição, reconhecimento e geração de voz |
| Vídeo | Análise e geração de vídeos |
| Multimodal | Combinação de texto, imagem, áudio e vídeo |

**Exemplo:**

- Chatbot textual: modelo especializado em texto.
- Análise de fotografias: modelo com capacidade de visão.
- Assistente por voz: modelo que trabalha com áudio.
- Aplicação que interpreta imagens e responde perguntas: modelo multimodal.

> **PEGADINHA:** Nem todo modelo de linguagem aceita imagens, áudio ou vídeo. Verifique as modalidades de entrada e saída suportadas.

<h3><strong style='color: skyblue'>Latência (Latency)</strong></h3>

<p align="justify">Latência é o tempo necessário para o modelo processar uma solicitação e começar ou concluir a geração da resposta. É um critério importante para aplicações que precisam responder rapidamente.</p>

**Exemplos:**
- Chatbot: exige respostas rápidas.
- Assistente por voz: precisa de baixa latência para manter uma conversa natural.
- Geração de relatórios extensos: pode tolerar maior tempo de processamento.

**Fatores que influenciam:**
- Tamanho do modelo.
- Complexidade da solicitação.
- Quantidade de tokens de entrada e saída.
- Capacidade computacional.
- Distância entre a aplicação e o serviço.

> **DECORA:** Menor latência significa resposta mais rápida, não necessariamente mais precisa.

<h3><strong style='color: skyblue'>Suporte multilíngue (Multilingual Support)</strong></h3>

<p align="justify">É a capacidade do modelo de compreender e gerar conteúdo em diferentes idiomas. Deve ser considerada quando a aplicação atende usuários de diferentes países ou precisa trabalhar com documentos em vários idiomas.</p>

**Exemplos:**
- Atendimento em português, inglês e espanhol.
- Tradução de documentos.
- Análise de conteúdo em diferentes idiomas.
- Suporte internacional ao cliente.

**Atenção:** Um modelo pode oferecer suporte a vários idiomas, mas apresentar qualidade diferente em cada um. É necessário avaliar o desempenho no idioma utilizado pela aplicação.

<h3><strong style='color: skyblue'>Tamanho do modelo (Model Size)</strong></h3>

<p align="justify">O tamanho do modelo está relacionado à quantidade de parâmetros utilizados para representar seu conhecimento e suas capacidades. Modelos maiores podem oferecer capacidades mais avançadas, mas geralmente exigem mais recursos computacionais.</p>

**Comparação:**

| Modelos menores | Modelos maiores |
|---|---|
| Geralmente mais baratos | Geralmente mais caros |
| Menor consumo de recursos | Maior consumo de recursos |
| Podem apresentar menor latência | Podem apresentar maior latência |
| Adequados para tarefas simples | Podem atender tarefas complexas |
| Implantação potencialmente mais simples | Podem exigir infraestrutura mais robusta |

**Exemplo:**

- Classificação simples de mensagens: modelo menor.
- Análise complexa de documentos: pode exigir modelo maior.

> **PEGADINHA:** Mais parâmetros não garantem automaticamente melhor resultado para qualquer tarefa.

<h3><strong style='color: skyblue'>Complexidade do modelo (Model Complexity)</strong></h3>

<p align="justify">A complexidade envolve a arquitetura, os recursos computacionais, a capacidade de processamento e a dificuldade de implantação e manutenção do modelo.</p>

**Considerações:**
- Capacidade de raciocínio e compreensão.
- Recursos computacionais necessários.
- Facilidade de integração.
- Tempo de inferência.
- Necessidade de manutenção.
- Complexidade operacional.

**Exemplo:** Uma aplicação que realiza classificação de sentimentos pode não precisar de um modelo complexo com capacidades avançadas de raciocínio.

<h3><strong style='color: skyblue'>Personalização (Customization)</strong></h3>

<p align="justify">É a capacidade de adaptar um modelo pré-treinado às necessidades específicas da organização ou da aplicação.</p>

**Possibilidades:**
- Engenharia de prompts (Prompt Engineering).
- Aprendizado em contexto (In-Context Learning).
- Geração aumentada via recuperação (RAG).
- Ajuste fino (Fine-tuning).
- Pré-treinamento adicional.
- Destilação de modelos (Model Distillation).

**Exemplo:**

Uma empresa pode utilizar um modelo pré-treinado e fornecer documentos internos por RAG para responder perguntas sobre suas próprias políticas.

> **DECORA:** Personalização não significa necessariamente treinar novamente o modelo. RAG e aprendizado em contexto podem adaptar a aplicação sem alterar os pesos do modelo.

<h3><strong style='color: skyblue'>Tamanho da entrada e da saída (Input/Output Length)</strong></h3>

<p align="justify">O tamanho da entrada representa a quantidade de informações enviadas ao modelo. O tamanho da saída representa a quantidade de conteúdo que ele pode gerar. Ambos são normalmente medidos em tokens.</p>

**Entrada (Input):**
- Instruções.
- Perguntas.
- Histórico da conversa.
- Documentos.
- Contexto recuperado por RAG.

**Saída (Output):**
- Respostas.
- Resumos.
- Relatórios.
- Código.
- Conteúdo gerado.

**Exemplo:**

Uma aplicação que analisa contratos extensos precisa de um modelo com capacidade adequada para receber grandes volumes de contexto.

**Limitações importantes:**
- Cada modelo possui um limite de contexto.
- Entradas maiores podem aumentar o custo e a latência.
- Saídas maiores podem aumentar o custo e o tempo de geração.
- A saída pode ser limitada por parâmetros de inferência.

> **PEGADINHA:** Janela de contexto não é a mesma coisa que limite de saída. A janela considera o contexto processado pelo modelo; o limite de saída controla a quantidade máxima de tokens gerados.

<h3><strong style='color: skyblue'>Armazenamento em cache de prompts (Prompt Caching)</strong></h3>

<p align="justify">Prompt caching permite reutilizar partes repetidas de um prompt, evitando que o modelo precise processar novamente todo o contexto em determinadas solicitações. No Amazon Bedrock, esse recurso está disponível para modelos e APIs compatíveis.</p>

**Exemplo:**

Um chatbot corporativo utiliza sempre:
- Instruções fixas.
- Políticas internas.
- Documentação extensa.
- Perguntas diferentes dos usuários.

Sem cache, o contexto repetido pode precisar ser processado novamente.

Com prompt caching, partes elegíveis e repetidas podem ser reutilizadas.

**Benefícios:**
- Redução da latência.
- Redução do custo de tokens de entrada, quando há leitura do cache.
- Melhor eficiência em aplicações com contexto repetitivo.

**Limitações:**
- Depende do suporte do modelo.
- Depende das condições de cache e da correspondência do conteúdo.
- O conteúdo dinâmico pode impedir a reutilização de determinadas partes.
- Não elimina o custo de processamento de novos conteúdos.

> **DECORA:** Prompt caching é especialmente útil quando uma aplicação envia instruções ou documentos extensos e repetidos em várias solicitações.

<h3><strong style='color: skyblue'>Resumo dos critérios de seleção</strong></h3>

| Critério | O que avaliar? |
|---|---|
| Custo | Quanto custa utilizar o modelo? |
| Modalidade | Trabalha com texto, imagem, áudio ou vídeo? |
| Latência | Quanto tempo demora para responder? |
| Multilíngue | Atende aos idiomas necessários? |
| Tamanho | Quantos parâmetros e recursos exige? |
| Complexidade | Qual o esforço de operação e integração? |
| Personalização | Pode ser adaptado ao negócio? |
| Entrada/saída | Suporta o volume de tokens necessário? |
| Prompt caching | Permite reutilizar contexto repetido? |

> **PEGADINHA:** A seleção de um FM envolve equilibrar qualidade, custo, velocidade, capacidades e necessidades empresariais. Não existe um modelo ideal para todos os cenários.

---

### 2️⃣ Descrever o efeito dos parâmetros de inferência nas respostas do modelo

<h3><strong style='color: skyblue'>Temperatura (Temperature)</strong></h3>

<p align="justify">A temperatura controla o grau de aleatoriedade na seleção dos próximos tokens durante a geração. Influencia a diversidade e a previsibilidade das respostas.</p>

**Temperatura baixa:**
- Respostas mais previsíveis.
- Menor diversidade.
- Maior consistência na geração.
- Adequada para tarefas estruturadas.

**Temperatura alta:**
- Respostas mais variadas.
- Maior diversidade de conteúdo.
- Maior liberdade criativa.
- Pode aumentar a imprevisibilidade.

**Exemplo:**

Pergunta: "Sugira um nome para uma empresa de tecnologia."

- Temperatura baixa: tende a produzir sugestões mais conservadoras e previsíveis.
- Temperatura alta: tende a produzir sugestões mais variadas e criativas.

| Temperatura | Comportamento esperado |
|---|---|
| Baixa | Mais previsibilidade |
| Média | Equilíbrio entre diversidade e consistência |
| Alta | Mais diversidade e criatividade |

> **DECORA:** Temperatura baixa = mais previsibilidade. Temperatura alta = mais diversidade. Isso não garante que a resposta seja correta.

<h3><strong style='color: skyblue'>Tamanho da entrada (Input Length)</strong></h3>

<p align="justify">Representa a quantidade de tokens enviados ao modelo. Quanto maior o contexto, mais informações o modelo pode considerar para produzir uma resposta, desde que respeite sua janela de contexto.</p>

**Exemplos de entrada:**
- Pergunta simples.
- Instruções detalhadas.
- Histórico de conversação.
- Documentos extensos.
- Informações recuperadas por RAG.

**Efeitos de entradas maiores:**
- Podem fornecer mais contexto.
- Podem melhorar respostas que dependem de documentos.
- Podem aumentar custo e latência.
- Podem ultrapassar a janela de contexto.
- Informações irrelevantes podem prejudicar a qualidade da resposta.

> **PEGADINHA:** Mais contexto não significa necessariamente melhor resposta. O importante é fornecer informações relevantes.

<h3><strong style='color: skyblue'>Tamanho da saída (Output Length / Max Tokens)</strong></h3>

<p align="justify">Controla a quantidade máxima de tokens que o modelo pode gerar em uma resposta. Em APIs e modelos compatíveis, esse limite é configurado por parâmetros como Max Tokens ou Maximum Generation Length.</p>

**Limite baixo:**
- Respostas mais curtas.
- Menor quantidade de tokens gerados.
- Pode interromper explicações antes da conclusão.

**Limite alto:**
- Permite respostas mais extensas.
- Pode gerar explicações mais detalhadas.
- Pode aumentar custo e latência.

**Exemplo:**

Uma aplicação de classificação de sentimentos pode utilizar uma saída curta, enquanto uma aplicação que gera relatórios pode precisar de um limite maior.

> **DECORA:** Max Tokens controla o limite máximo de geração, não obriga o modelo a utilizar todos os tokens disponíveis.

<h3><strong style='color: skyblue'>Top-P e Top-K (parâmetros complementares)</strong></h3>

<p align="justify">Além da temperatura, alguns modelos permitem controlar a seleção dos tokens por meio de Top-P e Top-K. A disponibilidade e o comportamento exato dependem do modelo.</p>

**Top-P (Nucleus Sampling):**

Limita as opções aos tokens mais prováveis cuja probabilidade acumulada atinge determinado valor.

- Top-P menor: restringe as opções de tokens.
- Top-P maior: permite um conjunto mais amplo de opções.

**Top-K:**

Limita a seleção aos K tokens mais prováveis.

- Top-K menor: reduz as opções disponíveis.
- Top-K maior: amplia as opções consideradas.

> **PEGADINHA:** Temperatura, Top-P e Top-K influenciam a seleção dos tokens. Max Tokens controla o tamanho máximo da resposta. São parâmetros diferentes.

<h3><strong style='color: skyblue'>Comparação dos parâmetros</strong></h3>

| Parâmetro | Principal efeito |
|---|---|
| Temperature | Controla aleatoriedade e diversidade |
| Input Length | Define quanto contexto pode ser enviado |
| Max Tokens | Limita o tamanho da saída |
| Top-P | Controla opções por probabilidade acumulada |
| Top-K | Limita a quantidade de opções consideradas |

**Exemplo prático:**

Para um chatbot que responde dúvidas sobre políticas internas:

- Temperatura baixa: respostas mais previsíveis.
- Entrada suficiente: fornece as políticas relevantes.
- Max Tokens adequado: evita respostas excessivamente longas.
- Top-P/Top-K: podem ser ajustados conforme o modelo.

> **DECORA:** Os parâmetros de inferência controlam como o modelo gera a resposta, mas não substituem a qualidade dos dados, do contexto ou do próprio modelo.

---

### 3️⃣ Definir RAG e descrever suas aplicações empresariais

<h3><strong style='color: skyblue'>O que é RAG (Retrieval-Augmented Generation)?</strong></h3>

<p align="justify">RAG, ou Geração Aumentada via Recuperação, é uma técnica que combina recuperação de informações externas com geração de conteúdo por um modelo de base. Antes de gerar uma resposta, a aplicação recupera informações relevantes de uma fonte de dados e fornece esse conteúdo ao modelo como contexto.</p>

<p align="justify">O objetivo é permitir que o modelo responda utilizando informações específicas, atualizadas ou privadas da organização, sem precisar realizar um novo treinamento para incorporar cada documento.</p>

**Funcionamento simplificado:**

<pre>
       DOCUMENTOS E DADOS
                │
                ▼
       Divisão em fragmentos
            (Chunks)
                │
                ▼
       Modelo de incorporações
          (Embeddings)
                │
                ▼
       BANCO DE DADOS VETORIAL
                │
                │
USUÁRIO ──► PERGUNTA
                │
                ▼
       Busca por similaridade
                │
                ▼
       Recuperação de documentos
                │
                ▼
       CONTEXTO + PERGUNTA
                │
                ▼
       MODELO DE BASE (FM)
                │
                ▼
        RESPOSTA GERADA
</pre>

<h3><strong style='color: skyblue'>Etapas do funcionamento do RAG</strong></h3>

**1. Preparação dos dados**

<p align="justify">A aplicação recebe documentos e informações de fontes como arquivos, bancos de dados e sistemas corporativos.</p>

**2. Fragmentação (Chunking)**

<p align="justify">Os documentos são divididos em partes menores para facilitar o armazenamento e a recuperação de informações relevantes.</p>

**3. Geração de incorporações (Embeddings)**

<p align="justify">Um modelo de embeddings transforma os fragmentos em representações numéricas chamadas vetores, que representam características semânticas do conteúdo.</p>

**4. Armazenamento vetorial**

<p align="justify">Os vetores e seus metadados são armazenados em um banco de dados vetorial, permitindo pesquisas por similaridade.</p>

**5. Recuperação (Retrieval)**

<p align="justify">Quando o usuário faz uma pergunta, ela também é convertida em um vetor. O sistema procura os fragmentos mais relevantes no banco de dados.</p>

**6. Geração (Generation)**

<p align="justify">Os fragmentos recuperados são enviados ao modelo junto com a pergunta original. O modelo utiliza essas informações para gerar uma resposta contextualizada.</p>

<h3><strong style='color: skyblue'>Amazon Bedrock Knowledge Bases</strong></h3>

<p align="justify">O Amazon Bedrock Knowledge Bases é um recurso gerenciado que simplifica a implementação de RAG. Ele permite conectar fontes de dados, gerar incorporações, armazenar informações em bancos vetoriais e recuperar conteúdos relevantes para complementar as respostas dos modelos.</p>

**Principais recursos:**
- Integração com fontes de dados.
- Preparação e fragmentação de documentos.
- Geração de embeddings.
- Armazenamento vetorial.
- Recuperação de informações relevantes.
- Integração com modelos de base do Bedrock.
- Possibilidade de apresentar referências das fontes recuperadas.

**Exemplo empresarial:**

Uma empresa possui milhares de documentos internos:
- Políticas corporativas.
- Manuais técnicos.
- Procedimentos operacionais.
- Documentação de sistemas.
- Perguntas frequentes.

Um funcionário pergunta: "Qual é o procedimento para solicitar acesso a um sistema?"

O RAG recupera os documentos relacionados e fornece o conteúdo ao modelo, que gera uma resposta baseada nas informações encontradas.

<h3><strong style='color: skyblue'>Aplicações empresariais do RAG</strong></h3>

| Aplicação | Utilização |
|---|---|
| Atendimento ao cliente | Consultar informações atualizadas sobre produtos e serviços |
| Recursos humanos | Responder dúvidas sobre políticas internas |
| Suporte técnico | Consultar manuais e procedimentos |
| Jurídico | Recuperar informações de contratos e documentos |
| Financeiro | Consultar políticas e relatórios |
| Pesquisa corporativa | Pesquisar informações em grandes repositórios |
| Desenvolvimento | Consultar documentação e padrões técnicos |

<h3><strong style='color: skyblue'>Vantagens e limitações do RAG</strong></h3>

**Vantagens:**
- Utiliza dados privados da organização.
- Permite trabalhar com informações atualizadas.
- Não exige retreinamento do modelo a cada alteração documental.
- Pode fornecer referências das fontes utilizadas.
- Ajuda a fundamentar as respostas em documentos recuperados.

**Limitações:**
- Depende da qualidade dos documentos.
- Depende da qualidade da recuperação.
- Pode aumentar latência e custo.
- Pode recuperar informações irrelevantes.
- Não elimina completamente as alucinações.

> **PEGADINHA:** RAG não é treinamento do modelo. Ele recupera informações no momento da inferência e adiciona esse conteúdo ao contexto enviado ao FM.

<h3><strong style='color: skyblue'>RAG × Fine-tuning</strong></h3>

| RAG | Fine-tuning |
|---|---|
| Recupera informações externas | Atualiza os pesos do modelo |
| Utiliza dados durante a inferência | Utiliza dados durante o treinamento |
| Ideal para informações atualizadas | Ideal para adaptar comportamento e tarefas |
| Não exige retreinamento para cada documento novo | Exige processo de treinamento |
| Pode fornecer referências | Não fornece automaticamente referências das fontes |

**Regra prática:**
- Precisa consultar documentos atualizados? RAG.
- Precisa adaptar o estilo, formato ou comportamento? Fine-tuning.
- Precisa das duas coisas? É possível combinar RAG e Fine-tuning.

> **DECORA:** RAG adiciona conhecimento externo ao contexto; Fine-tuning modifica o comportamento aprendido pelo modelo.

---

### 4️⃣ Identificar serviços da AWS que ajudam a armazenar incorporações em bancos de dados vetoriais

<h3><strong style='color: skyblue'>O que é um banco de dados vetorial?</strong></h3>

<p align="justify">Um banco de dados vetorial armazena incorporações (Embeddings), que são representações numéricas de informações como textos, imagens e áudios. Ele permite realizar buscas por similaridade semântica, encontrando conteúdos relacionados mesmo quando não existe correspondência exata entre as palavras.</p>

**Exemplo:**

Uma pesquisa por "como recuperar minha senha" pode encontrar um documento chamado "Procedimento para redefinição de credenciais", mesmo sem utilizar as mesmas palavras.

<h3><strong style='color: skyblue'>Amazon OpenSearch Service</strong></h3>

<p align="justify">O Amazon OpenSearch Service oferece recursos de pesquisa e análise, incluindo pesquisa vetorial e semântica. Pode armazenar embeddings e recuperar documentos semelhantes por meio de consultas vetoriais.</p>

**Características:**
- Pesquisa vetorial.
- Pesquisa textual e semântica.
- Pesquisa híbrida.
- Escalabilidade.
- Integração com aplicações RAG.

**Quando utilizar:** Aplicações que precisam combinar pesquisa textual tradicional com pesquisa semântica em grandes volumes de documentos.

<h3><strong style='color: skyblue'>Amazon Aurora</strong></h3>

<p align="justify">O Amazon Aurora é um banco de dados relacional compatível com PostgreSQL e MySQL. Na modalidade PostgreSQL, pode utilizar a extensão pgvector para armazenar e pesquisar embeddings.</p>

**Características:**
- Armazenamento vetorial com pgvector.
- Integração com dados relacionais.
- Consultas SQL.
- Combinação de dados estruturados e vetores.
- Integração com Amazon Bedrock Knowledge Bases em configurações compatíveis.

**Quando utilizar:** Quando a organização já utiliza Aurora PostgreSQL e deseja adicionar pesquisa vetorial aos dados relacionais existentes.

<h3><strong style='color: skyblue'>Amazon Neptune</strong></h3>

<p align="justify">O Amazon Neptune é um serviço de banco de dados de grafos. É utilizado para representar relacionamentos entre entidades e pode participar de soluções de recuperação que combinam informações vetoriais e relacionamentos entre dados.</p>

**Características:**
- Armazenamento de grafos.
- Representação de relacionamentos.
- Consultas baseadas em conexões entre entidades.
- Recursos de pesquisa vetorial em ofertas compatíveis, como Neptune Analytics.
- Aplicações de GraphRAG.

**Quando utilizar:** Quando a aplicação precisa compreender relacionamentos complexos entre pessoas, produtos, organizações ou conceitos.

**Exemplo:** Uma aplicação que pesquisa relações entre clientes, contratos, fornecedores e transações.

<h3><strong style='color: skyblue'>Amazon RDS para PostgreSQL</strong></h3>

<p align="justify">O Amazon RDS para PostgreSQL é um serviço gerenciado de banco de dados relacional que pode utilizar a extensão pgvector para armazenar e consultar embeddings.</p>

**Características:**
- Banco de dados relacional PostgreSQL.
- Armazenamento de vetores por meio de pgvector.
- Consultas SQL.
- Combinação de informações estruturadas e vetoriais.
- Integração com aplicações que implementam RAG.

**Quando utilizar:** Quando a organização já utiliza PostgreSQL no RDS e deseja adicionar recursos de pesquisa vetorial sem necessariamente adotar outro mecanismo de armazenamento.

<h3><strong style='color: skyblue'>Comparação dos serviços</strong></h3>

| Serviço | Principal característica | Cenário de uso |
|---|---|---|
| Amazon OpenSearch Service | Pesquisa vetorial e textual | Busca semântica e híbrida |
| Amazon Aurora | Banco relacional com pgvector | RAG com dados relacionais |
| Amazon Neptune | Banco de grafos | Relacionamentos e GraphRAG |
| Amazon RDS para PostgreSQL | PostgreSQL com pgvector | Vetores junto a dados relacionais |

**Outros recursos relacionados:**

- Amazon Bedrock Knowledge Bases: gerencia etapas de ingestão, embeddings e recuperação.
- Amazon Titan Embeddings: modelo que pode gerar representações vetoriais.
- pgvector: extensão PostgreSQL que permite armazenar e pesquisar vetores.

> **PEGADINHA:** Amazon Bedrock Knowledge Bases não é simplesmente um banco de dados vetorial. É um recurso gerenciado para implementar RAG, utilizando armazenamentos vetoriais compatíveis.

---

### 5️⃣ Explicar as compensações de custos das abordagens de personalização de modelos de base (FMs)

<h3><strong style='color: skyblue'>Pré-treinamento (Pre-training)</strong></h3>

<p align="justify">É o processo de treinamento inicial de um modelo utilizando grandes volumes de dados. O modelo aprende padrões, relações e características gerais que permitem executar diferentes tarefas.</p>

**Características:**
- Utiliza grandes conjuntos de dados.
- Exige elevado poder computacional.
- Pode envolver grandes quantidades de GPUs.
- Demanda tempo e conhecimento especializado.
- Apresenta custo elevado.

**Vantagem:** Permite desenvolver um modelo com capacidades amplas a partir dos dados de treinamento.

**Desvantagem:** É uma das abordagens mais caras e complexas, normalmente desnecessária para organizações que apenas precisam adaptar um FM existente.

> **DECORA:** Pré-treinamento = construir a base de conhecimento e capacidades do modelo. Alto custo e complexidade.

<h3><strong style='color: skyblue'>Ajuste fino (Fine-tuning)</strong></h3>

<p align="justify">É o processo de continuar o treinamento de um modelo pré-treinado utilizando dados específicos para adaptar seu comportamento, estilo, formato de resposta ou desempenho em determinadas tarefas.</p>

**Exemplos:**
- Adaptar um modelo ao vocabulário de uma área profissional.
- Ensinar um formato específico de resposta.
- Melhorar a execução de tarefas especializadas.
- Adaptar o modelo a padrões de comunicação corporativa.

**Vantagens:**
- Reaproveita um modelo pré-treinado.
- Pode melhorar o desempenho em tarefas específicas.
- Pode reduzir a necessidade de instruções extensas em cada solicitação.

**Desvantagens:**
- Exige dados de treinamento de qualidade.
- Demanda processamento e investimento.
- Pode exigir avaliação e novos ajustes.
- Não garante que o modelo tenha informações atualizadas.

> **DECORA:** Fine-tuning = modificar os pesos do modelo para adaptar seu comportamento.

<h3><strong style='color: skyblue'>Aprendizado em contexto (In-Context Learning)</strong></h3>

<p align="justify">Consiste em fornecer instruções, informações e exemplos diretamente no prompt para orientar o comportamento do modelo durante a inferência, sem atualizar seus pesos.</p>

**Exemplos:**
- Zero-shot: fornecer somente a instrução.
- One-shot: fornecer um exemplo.
- Few-shot: fornecer vários exemplos.

**Vantagens:**
- Não exige treinamento adicional.
- Implementação rápida.
- Fácil de testar e modificar.
- Pode utilizar exemplos específicos de uma tarefa.

**Desvantagens:**
- Depende da janela de contexto.
- Prompts maiores podem aumentar custos.
- O modelo não aprende permanentemente com os exemplos.
- Pode apresentar limitações em tarefas muito complexas.

> **DECORA:** In-Context Learning = ensinar pelo contexto do prompt, sem alterar os pesos do modelo.

<h3><strong style='color: skyblue'>RAG (Retrieval-Augmented Generation)</strong></h3>

<p align="justify">Utiliza uma fonte externa de conhecimento para recuperar informações relevantes e adicioná-las ao contexto do modelo durante a inferência.</p>

**Vantagens:**
- Utiliza documentos atualizados.
- Permite consultar dados privados.
- Não exige retreinamento a cada atualização documental.
- Pode fornecer referências das fontes.

**Desvantagens:**
- Exige infraestrutura de recuperação.
- Pode gerar custos de embeddings, armazenamento e consultas.
- Aumenta potencialmente a latência.
- Depende da qualidade da recuperação.

**Exemplo:** Uma empresa utiliza Bedrock Knowledge Bases para consultar políticas internas atualizadas.

> **DECORA:** RAG = buscar informações externas e fornecer ao modelo no momento da resposta.

<h3><strong style='color: skyblue'>Destilação de modelos (Model Distillation)</strong></h3>

<p align="justify">É uma técnica que transfere conhecimento de um modelo maior e mais capaz, chamado Teacher, para um modelo menor, chamado Student. O objetivo é fazer com que o modelo menor reproduza capacidades relevantes do modelo maior com menor custo de inferência.</p>

**Funcionamento:**

<pre>
     MODELO MAIOR
       (TEACHER)
           │
           │ Respostas e conhecimento
           ▼
     PROCESSO DE
      DESTILAÇÃO
           │
           ▼
     MODELO MENOR
       (STUDENT)
           │
           ▼
    INFERÊNCIA MAIS
    ECONÔMICA
</pre>

**Vantagens:**
- Reduz o tamanho do modelo utilizado em produção.
- Pode diminuir custos de inferência.
- Pode reduzir latência.
- Pode reduzir requisitos de memória e processamento.

**Desvantagens:**
- Exige um processo de treinamento.
- Depende da qualidade do modelo Teacher.
- O modelo Student pode perder capacidades.
- O modelo menor pode não reproduzir todas as habilidades do maior.

**Exemplo:**

Uma empresa utiliza um modelo grande para gerar respostas de referência e treina um modelo menor para executar uma tarefa específica com menor custo operacional.

> **DECORA:** Distillation = transferir conhecimento de um modelo maior (Teacher) para um menor (Student), buscando reduzir o custo de execução.

<h3><strong style='color: skyblue'>Comparação das abordagens de personalização</strong></h3>

| Abordagem | Altera os pesos? | Principal finalidade | Custo relativo |
|---|---|---|---|
| Pré-treinamento | Sim, cria os pesos iniciais | Desenvolver capacidades gerais | Muito alto |
| Fine-tuning | Sim | Adaptar comportamento e tarefas | Médio a alto |
| In-Context Learning | Não | Orientar pelo prompt e exemplos | Baixo para começar |
| RAG | Não | Adicionar conhecimento externo | Variável |
| Distillation | Sim, no Student | Reduzir custo e tamanho do modelo | Investimento inicial adicional; pode reduzir custo de inferência |

<text color="secondary" size="xs">Os custos relativos são comparações gerais. O custo real depende do modelo, volume de dados, infraestrutura, frequência de uso e implementação.</text>

<h3><strong style='color: skyblue'>Quando escolher cada abordagem?</strong></h3>

| Necessidade | Abordagem recomendada |
|---|---|
| Criar um modelo do zero | Pré-treinamento |
| Adaptar estilo ou comportamento | Fine-tuning |
| Fornecer exemplos diretamente no prompt | In-Context Learning |
| Consultar documentos atualizados | RAG |
| Executar tarefas com um modelo menor e mais econômico | Distillation |

**Regra prática:**

- Precisa de conhecimento atualizado? RAG.
- Precisa mudar o comportamento do modelo? Fine-tuning.
- Precisa apenas orientar a resposta? In-Context Learning.
- Precisa construir capacidades gerais de um modelo? Pré-treinamento.
- Precisa reduzir o custo de inferência transferindo capacidades? Distillation.

> **PEGADINHA:** RAG e In-Context Learning não atualizam os pesos do modelo. Fine-tuning, pré-treinamento e destilação envolvem treinamento e alteração dos pesos do modelo correspondente.

---

### 6️⃣ Definir a função dos agentes de IA e descrever aplicações comerciais

<h3><strong style='color: skyblue'>O que são agentes de IA (AI Agents)?</strong></h3>

<p align="justify">Agentes de IA são sistemas que utilizam modelos de base para compreender objetivos, planejar etapas, tomar decisões e executar ações por meio de ferramentas e sistemas externos.</p>

<p align="justify">Diferentemente de uma aplicação que apenas recebe uma pergunta e gera uma resposta, um agente pode realizar várias etapas para alcançar um objetivo, consultar informações, utilizar APIs e interagir com outros sistemas.</p>

**Principais características:**
- Compreender solicitações em linguagem natural.
- Planejar tarefas.
- Dividir problemas complexos em etapas menores.
- Utilizar ferramentas externas.
- Consultar bases de conhecimento.
- Executar chamadas de API.
- Manter contexto e memória.
- Verificar resultados e continuar o fluxo de trabalho.

<h3><strong style='color: skyblue'>Como funciona um agente?</strong></h3>

<pre>
        USUÁRIO
           │
           ▼
     OBJETIVO / TAREFA
           │
           ▼
       AGENTE DE IA
           │
           ▼
    MODELO DE BASE (FM)
           │
           ▼
   PLANEJAMENTO DAS ETAPAS
           │
           ▼
      ESCOLHA DE FERRAMENTAS
           │
      ┌────┼───────────┐
      ▼    ▼           ▼
    API  BANCO       SISTEMA
         DE DADOS    EXTERNO
      │    │           │
      └────┼───────────┘
           │
           ▼
     RESULTADO / AÇÃO
           │
           ▼
      RESPOSTA AO
         USUÁRIO
</pre>

**Exemplo:**

Um cliente solicita: "Verifique meu pedido e informe se posso receber o produto amanhã."

O agente pode:
1. Identificar a solicitação.
2. Consultar o pedido no sistema.
3. Consultar o estoque.
4. Consultar o sistema de entregas.
5. Verificar a previsão.
6. Responder ao cliente.

<h3><strong style='color: skyblue'>Agentes × Chatbots tradicionais</strong></h3>

| Chatbot tradicional | Agente de IA |
|---|---|
| Responde perguntas | Pode executar tarefas |
| Geralmente segue fluxos predefinidos | Pode planejar etapas |
| Interação mais limitada | Pode utilizar ferramentas |
| Pode depender de regras fixas | Pode decidir quais ferramentas utilizar |
| Foco na comunicação | Foco em alcançar objetivos |

> **PEGADINHA:** Um agente pode conversar com o usuário, mas sua principal diferença é a capacidade de utilizar ferramentas e executar ações para atingir objetivos.

<h3><strong style='color: skyblue'>Aplicações comerciais de agentes de IA</strong></h3>

<p align="justify">Os agentes podem automatizar processos empresariais que exigem várias etapas, consultas a sistemas e execução de ações. São especialmente úteis quando uma tarefa depende de diferentes fontes de dados e aplicações.</p>

**Atendimento ao cliente**
- Consultar pedidos.
- Verificar entregas.
- Processar solicitações.
- Abrir chamados.
- Encaminhar casos complexos.

**Recursos humanos**
- Consultar políticas internas.
- Auxiliar processos de integração de funcionários.
- Responder dúvidas sobre benefícios.
- Apoiar solicitações administrativas.

**Financeiro**
- Consultar transações.
- Auxiliar processos de cobrança.
- Identificar inconsistências.
- Preparar relatórios financeiros.

**Vendas e marketing**
- Qualificar oportunidades.
- Consultar informações de clientes.
- Recomendar produtos.
- Preparar propostas comerciais.
- Apoiar o acompanhamento de vendas.

**TI e suporte técnico**
- Consultar documentação.
- Diagnosticar problemas.
- Abrir e atualizar chamados.
- Executar procedimentos autorizados.
- Auxiliar na análise de incidentes.

**Operações e logística**
- Consultar estoque.
- Acompanhar entregas.
- Verificar pedidos.
- Coordenar etapas de processos.
- Identificar atrasos e inconsistências.

<h3><strong style='color: skyblue'>Agentes e ferramentas externas</strong></h3>

<p align="justify">Para executar ações, os agentes podem utilizar ferramentas como APIs, funções, bancos de dados e serviços externos. Essas integrações permitem que o agente deixe de apenas gerar respostas e passe a interagir com os sistemas da organização.</p>

**Exemplos de ferramentas:**
- AWS Lambda: execução de funções.
- Amazon API Gateway: disponibilização e gerenciamento de APIs.
- Amazon DynamoDB: consulta e atualização de dados.
- Amazon S3: acesso a arquivos e documentos.
- Amazon Bedrock Knowledge Bases: recuperação de informações.
- AWS Step Functions: orquestração de fluxos de trabalho.

<h3><strong style='color: skyblue'>Benefícios empresariais dos agentes</strong></h3>

- Automação de processos com várias etapas.
- Redução de atividades manuais.
- Maior produtividade.
- Atendimento contínuo.
- Integração entre sistemas.
- Redução do tempo de execução.
- Melhor experiência do cliente.
- Possibilidade de escalar operações.

<h3><strong style='color: skyblue'>Limitações e cuidados</strong></h3>

<p align="justify">Como agentes podem executar ações em sistemas externos, é necessário estabelecer limites e controles para evitar operações incorretas ou não autorizadas.</p>

**Cuidados importantes:**
- Controle de permissões.
- Validação das ações.
- Monitoramento das execuções.
- Tratamento de erros.
- Proteção de dados.
- Aprovação humana para ações sensíveis.
- Limitação das ferramentas disponíveis.

**Exemplo:** Um agente pode preparar uma solicitação de reembolso, mas a aprovação final pode exigir autorização humana.

> **DECORA:** Agente = modelo de base + planejamento + ferramentas + execução de ações para alcançar um objetivo.

---

### 🧠 DECORAÇÃO FINAL — Tarefa 3.1

**1. Seleção de modelos de base**

- Custo: quanto custa utilizar?
- Modalidade: texto, imagem, áudio, vídeo ou multimodal?
- Latência: quanto tempo demora para responder?
- Multilíngue: suporta os idiomas necessários?
- Tamanho: quantos parâmetros e recursos exige?
- Complexidade: qual o esforço de operação?
- Personalização: pode ser adaptado?
- Entrada/saída: quantos tokens suporta?
- Prompt caching: consegue reutilizar contexto repetido?

**2. Parâmetros de inferência**

- Temperature: controla aleatoriedade.
- Input Length: quantidade de tokens enviados.
- Max Tokens: limite de tokens gerados.
- Top-P: seleção por probabilidade acumulada.
- Top-K: quantidade de opções consideradas.

**3. RAG**

- Recupera informações externas.
- Utiliza embeddings e bancos vetoriais.
- Adiciona documentos relevantes ao contexto.
- Não altera os pesos do modelo.
- Amazon Bedrock Knowledge Bases facilita sua implementação.

**4. Bancos de dados vetoriais AWS**

- OpenSearch Service: pesquisa vetorial e híbrida.
- Aurora: banco relacional com pgvector.
- Neptune: grafos e relacionamentos.
- RDS PostgreSQL: armazenamento vetorial com pgvector.

**5. Personalização de FMs**

- Pré-treinamento: cria capacidades gerais; muito caro.
- Fine-tuning: adapta comportamento; exige treinamento.
- In-Context Learning: fornece exemplos no prompt; não altera pesos.
- RAG: recupera informações externas; não altera pesos.
- Distillation: transfere conhecimento do Teacher para o Student; busca reduzir custo de inferência.

**6. Agentes de IA**

- Compreendem objetivos.
- Planejam tarefas.
- Utilizam ferramentas.
- Consultam sistemas externos.
- Executam ações.
- Automatizam processos empresariais.

### ⚠️ PEGADINHAS DE PROVA

1. O maior modelo não é necessariamente o mais adequado. Custo, latência e capacidade precisam ser equilibrados.
2. Modelo multimodal consegue trabalhar com diferentes modalidades, mas é necessário verificar quais são suportadas.
3. Janela de contexto e limite de saída são conceitos diferentes.
4. Temperatura alta aumenta a diversidade; temperatura baixa aumenta a previsibilidade.
5. Max Tokens limita a geração, não determina que o modelo utilize todos os tokens.
6. Prompt caching reutiliza partes elegíveis de prompts repetidos, reduzindo potencialmente custo e latência.
7. RAG recupera informações externas durante a inferência; não realiza treinamento.
8. Fine-tuning modifica os pesos do modelo para adaptar seu comportamento.
9. In-Context Learning utiliza exemplos no prompt sem atualizar os pesos.
10. Pré-treinamento é uma abordagem de alto custo para desenvolver capacidades gerais.
11. Distillation transfere conhecimento de um modelo Teacher para um Student, geralmente menor.
12. OpenSearch, Aurora, Neptune e RDS PostgreSQL podem participar de soluções com armazenamento ou pesquisa vetorial.
13. Neptune é especialmente associado a grafos e relacionamentos entre entidades.
14. pgvector é uma extensão utilizada com PostgreSQL para trabalhar com vetores.
15. Bedrock Knowledge Bases facilita a implementação de RAG.
16. Agentes não apenas respondem: podem planejar, consultar ferramentas e executar ações.
17. Um agente pode utilizar APIs e bancos de dados para concluir processos empresariais.
18. Ações sensíveis executadas por agentes precisam de controles, permissões e, quando necessário, aprovação humana.

### 🗺️ MAPA MENTAL

<pre>
APLICAÇÕES DE FMs — TAREFA 3.1
│
├── 1. SELEÇÃO DO MODELO
│   ├── Custo
│   ├── Modalidade
│   ├── Latência
│   ├── Multilíngue
│   ├── Tamanho
│   ├── Complexidade
│   ├── Personalização
│   ├── Entrada / Saída
│   └── Prompt Caching
│
├── 2. INFERÊNCIA
│   ├── Temperature → Aleatoriedade
│   ├── Input Length → Contexto
│   ├── Max Tokens → Limite de saída
│   ├── Top-P → Probabilidade acumulada
│   └── Top-K → Quantidade de opções
│
├── 3. RAG
│   ├── Documentos
│   ├── Chunking
│   ├── Embeddings
│   ├── Banco vetorial
│   ├── Retrieval
│   └── Generation
│
├── 4. BANCOS VETORIAIS AWS
│   ├── OpenSearch → Pesquisa
│   ├── Aurora → Relacional + pgvector
│   ├── Neptune → Grafos
│   └── RDS PostgreSQL → pgvector
│
├── 5. PERSONALIZAÇÃO
│   ├── Pré-treinamento → Criar capacidades
│   ├── Fine-tuning → Alterar comportamento
│   ├── In-Context → Exemplos no prompt
│   ├── RAG → Conhecimento externo
│   └── Distillation → Teacher → Student
│
└── 6. AGENTES DE IA
    ├── Compreender objetivos
    ├── Planejar tarefas
    ├── Utilizar ferramentas
    ├── Consultar sistemas
    ├── Executar ações
    └── Automatizar processos
</pre>
