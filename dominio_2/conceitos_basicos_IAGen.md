## Declaração de tarefa 2.1: Explicar os conceitos básicos de IA generativa

<p align="justify">Esta tarefa aborda os fundamentos da IA generativa (GenAI), os conceitos utilizados pelos modelos de base (Foundation Models), suas aplicações, o ciclo de vida desses modelos, a cobrança por tokens, a engenharia de contexto e os fundamentos da IA agêntica.</p>

<pre>
IA GENERATIVA
     │
     ├── CONCEITOS
     │     ├── Tokens
     │     ├── Chunking
     │     ├── Embeddings
     │     ├── Vetores
     │     ├── Prompt Engineering
     │     ├── Transformers / LLMs
     │     ├── Foundation Models
     │     ├── Multimodalidade
     │     └── Modelos de difusão
     │
     ├── APLICAÇÕES
     │     ├── Texto
     │     ├── Imagem
     │     ├── Áudio
     │     ├── Vídeo
     │     ├── Código
     │     └── Assistentes
     │
     ├── CICLO DE VIDA DO FM
     │     ├── Dados
     │     ├── Seleção
     │     ├── Pré-treinamento
     │     ├── Fine-tuning
     │     ├── Avaliação
     │     ├── Deployment
     │     └── Feedback
     │
     ├── PRECIFICAÇÃO
     │     ├── Tokens de entrada
     │     ├── Tokens de saída
     │     └── Custo de inferência
     │
     ├── CONTEXT ENGINEERING
     │     ├── Instruções
     │     ├── Histórico
     │     ├── Dados relevantes
     │     └── Ferramentas
     │
     └── IA AGÊNTICA
           ├── Agentes
           ├── Multiagentes
           ├── MCP
           ├── Memória
           ├── Ferramentas
           └── Orquestração
</pre>

> 🔥 **DECORA:** IA generativa cria conteúdo novo a partir de padrões aprendidos. Modelos de base permitem construir diferentes aplicações, e agentes podem utilizar ferramentas para executar tarefas.

---

### 1️⃣ Definir os conceitos fundamentais de IA generativa

<h3><strong style='color: skyblue'>🧩 Tokens</strong></h3>

<p align="justify">Tokens são unidades de texto processadas pelo modelo. Um token pode representar uma palavra inteira, parte de uma palavra, pontuação ou uma sequência de caracteres.</p>

Exemplo ilustrativo:

```text
Texto: Inteligência Artificial

Possível divisão:
[Inteligência] [Artificial]

Outro texto:
[desenvolvimento] [tecnológico]
```

A divisão real depende do tokenizer utilizado pelo modelo.

**Por que são importantes?**

- Os modelos processam entradas e produzem saídas em tokens.
- O limite de contexto costuma ser medido em tokens.
- A cobrança de muitos serviços de GenAI é baseada na quantidade de tokens.
- Prompts e respostas maiores geralmente consomem mais tokens.

> **DECORA:** token ≠ necessariamente uma palavra. É uma unidade de processamento do modelo.

---

<h3><strong style='color: skyblue'>🧩 Chunking — Fragmentação</strong></h3>

<p align="justify">Chunking é a divisão de conteúdos grandes em partes menores (chunks), facilitando o processamento, armazenamento, recuperação e envio de informações aos modelos.</p>

Exemplo: um documento de 100 páginas pode ser dividido em pequenos trechos.

```text
DOCUMENTO COMPLETO
        │
        ▼
   CHUNKING
        │
   ┌────┼────┐
   ▼    ▼    ▼
Chunk 1 Chunk 2 Chunk 3
   │      │      │
   ▼      ▼      ▼
Trecho  Trecho  Trecho
```

**Por que utilizar?**

- Evitar ultrapassar o limite de contexto do modelo.
- Facilitar buscas em documentos grandes.
- Recuperar apenas os trechos relevantes.
- Melhorar a eficiência de aplicações com RAG.
- Reduzir a quantidade de informação desnecessária enviada ao modelo.

**Exemplo prático:**

Uma empresa possui milhares de páginas de documentação. Em vez de enviar todos os documentos ao modelo em cada pergunta, divide o conteúdo em chunks e recupera somente os trechos relacionados à pergunta.

> **DECORA:** Chunking = dividir documentos grandes em partes menores.

> **PEGADINHA:** Chunking não é treinamento do modelo. É uma técnica de preparação e organização do conteúdo.

---

<h3><strong style='color: skyblue'>🧩 Embeddings — Incorporações</strong></h3>

<p align="justify">Embeddings são representações numéricas de informações, como textos, imagens ou outros conteúdos, que capturam características e relações semânticas.</p>

Eles permitem que conteúdos com significados semelhantes sejam representados de maneira próxima em um espaço vetorial.

Exemplo:

```text
"Carro"
"Automóvel"
"Veículo"
```

Essas palavras possuem significados relacionados e podem apresentar embeddings próximos.

**Aplicações:**

- busca semântica;
- sistemas de recomendação;
- recuperação de documentos;
- agrupamento de conteúdos;
- aplicações RAG.

> **DECORA:** Embedding = transformar conteúdo em representação numérica que preserva características semânticas.

---

<h3><strong style='color: skyblue'>🧩 Vetores — Vectors</strong></h3>

<p align="justify">Um vetor é uma representação matemática formada por uma sequência de números. Em IA, vetores podem representar embeddings e permitir cálculos de similaridade entre conteúdos.</p>

Exemplo simplificado:

```text
Texto A → [0.2, 0.8, 0.4]
Texto B → [0.3, 0.7, 0.5]
Texto C → [0.9, 0.1, 0.2]
```

Se os vetores A e B estiverem próximos, seus conteúdos podem apresentar maior similaridade semântica.

**Conceito importante:**

- Vetores próximos → maior similaridade, dependendo da métrica utilizada.
- Vetores distantes → menor similaridade, dependendo da métrica utilizada.

Uma técnica comum é a similaridade de cosseno (cosine similarity).

**Exemplo prático:**

Uma pessoa pesquisa "como trocar a bateria do notebook". Um mecanismo de busca semântica pode recuperar um documento chamado "substituição da bateria de computadores portáteis", mesmo sem as palavras serem exatamente iguais.

> **DECORA:** Vetor = sequência numérica. Embedding = representação vetorial de um conteúdo.

---

<h3><strong style='color: skyblue'>🧩 Prompt Engineering — Engenharia de prompts</strong></h3>

<p align="justify">É a prática de criar e aperfeiçoar instruções enviadas ao modelo para orientar a resposta e obter resultados mais relevantes.</p>

Um bom prompt pode especificar:

- objetivo;
- contexto;
- instruções;
- formato esperado;
- restrições;
- exemplos.

**Exemplo de prompt genérico:**

```text
Explique segurança da informação.
```

**Exemplo de prompt mais estruturado:**

```text
Explique segurança da informação
para um iniciante.

Utilize:
- linguagem simples;
- exemplos práticos;
- tópicos curtos;
- um resumo final.
```

O segundo prompt fornece mais direcionamento ao modelo.

**Técnicas relacionadas:**

| Técnica | Significado |
|---|---|
| Zero-shot | Solicitação sem fornecer exemplos |
| One-shot | Solicitação com um exemplo |
| Few-shot | Solicitação com alguns exemplos |
| Prompt template | Modelo reutilizável de prompt |
| Negative prompt | Indica o que deve ser evitado na geração, quando suportado |

> **DECORA:** Prompt Engineering = melhorar as instruções para melhorar a resposta.

> **PEGADINHA:** Prompt Engineering não altera necessariamente os pesos do modelo. É uma técnica de orientação por meio das entradas.

---

<h3><strong style='color: skyblue'>🧩 LLMs baseados em Transformers</strong></h3>

<p align="justify">LLM (Large Language Model) é um grande modelo de linguagem treinado com grandes volumes de dados para compreender e gerar textos.</p>

<p align="justify">Muitos LLMs modernos utilizam a arquitetura Transformer, que emprega mecanismos de atenção (Attention) para identificar relações entre diferentes partes de uma sequência.</p>

**Como funciona conceitualmente?**

```text
Texto de entrada
       ↓
Tokenização
       ↓
Representação dos tokens
       ↓
Transformer / Atenção
       ↓
Processamento do contexto
       ↓
Previsão do próximo token
       ↓
Texto gerado
```

**Mecanismo de atenção (Attention):**

Permite que o modelo considere relações entre diferentes partes do texto para determinar quais informações são relevantes durante o processamento.

Exemplo:

```text
"O banco aprovou o empréstimo
porque o cliente tinha bom histórico."
```

O modelo precisa considerar o contexto para interpretar o significado das palavras.

**Características dos LLMs:**

- geração de texto;
- respostas a perguntas;
- resumo;
- tradução;
- classificação;
- geração de código;
- conversação.

> **DECORA:** Transformer = arquitetura baseada em mecanismos de atenção. LLM = grande modelo de linguagem.

---

<h3><strong style='color: skyblue'>🧩 Foundation Models — Modelos de base (FMs)</strong></h3>

<p align="justify">Foundation Models são modelos treinados previamente em grandes volumes de dados e que podem ser adaptados para diferentes tarefas e aplicações.</p>

Um único FM pode servir como base para diferentes soluções.

```text
             FOUNDATION MODEL
                    │
       ┌────────────┼────────────┐
       ▼            ▼            ▼
    Resumo       Tradução      Código
       │            │            │
       ▼            ▼            ▼
   Aplicação    Aplicação    Aplicação
```

**Características:**

- treinamento prévio em grandes conjuntos de dados;
- capacidade de atender diferentes tarefas;
- possibilidade de adaptação;
- podem ser utilizados por meio de serviços gerenciados;
- podem ser especializados com técnicas de customização.

**Exemplos de utilização:**

- assistentes virtuais;
- geração de conteúdo;
- análise de documentos;
- aplicações de atendimento;
- geração de código.

> **DECORA:** Foundation Model = modelo de base reutilizável para diferentes aplicações.

**Diferença entre LLM e FM:**

| Conceito | Significado |
|---|---|
| LLM | Modelo de linguagem de grande escala |
| FM | Modelo de base treinado para servir a diferentes aplicações |
| Relação | Um LLM pode ser um tipo de Foundation Model |

> **PEGADINHA:** nem todo Foundation Model é um LLM. Existem modelos de base para imagens, áudio e outras modalidades.

---

<h3><strong style='color: skyblue'>🧩 Modelos multimodais</strong></h3>

<p align="justify">São modelos capazes de processar ou gerar diferentes tipos de dados, como texto, imagem, áudio e vídeo.</p>

Exemplo:

```text
          MODELO MULTIMODAL
                  │
       ┌──────────┼──────────┐
       ▼          ▼          ▼
     Texto     Imagem      Áudio
       │          │          │
       └──────────┼──────────┘
                  ▼
          Compreensão conjunta
```

**Exemplos de aplicações:**

- analisar uma imagem e responder perguntas sobre ela;
- interpretar áudio e gerar uma resposta;
- resumir um vídeo;
- gerar imagens a partir de descrições textuais;
- combinar texto e imagem em uma única aplicação.

> **DECORA:** multimodal = trabalha com mais de uma modalidade de dados.

---

<h3><strong style='color: skyblue'>🧩 Modelos de difusão — Diffusion Models</strong></h3>

<p align="justify">Modelos de difusão são modelos generativos que aprendem a criar conteúdo, especialmente imagens, por meio de um processo de adição e remoção gradual de ruído.</p>

**Como funciona?**

Durante o treinamento:

1. O modelo recebe dados, como imagens.
2. Ruído é adicionado gradualmente.
3. O modelo aprende a reverter esse processo, removendo o ruído.

Durante a geração:

1. O processo começa com ruído.
2. O modelo remove o ruído progressivamente.
3. Uma imagem coerente é formada.

<pre>
TREINAMENTO
Imagem original
      ↓
Adição gradual de ruído
      ↓
Imagem com ruído
      ↓
Modelo aprende a remover ruído


GERAÇÃO
Ruído aleatório
      ↓
Remoção gradual de ruído
      ↓
Imagem formada
      ↓
Imagem gerada
</pre>

**Aplicações:**

- geração de imagens;
- criação de ilustrações;
- edição de imagens;
- geração de conteúdo visual;
- geração de vídeo em determinadas arquiteturas.

> **DECORA:** Diffusion = geração por remoção gradual de ruído.

---

### 🧠 Tabela definitiva dos conceitos

| Conceito | O que significa? |
|---|---|
| Token | Unidade de processamento do texto |
| Chunking | Divisão de conteúdo em partes menores |
| Embedding | Representação numérica semântica |
| Vetor | Sequência de números |
| Prompt Engineering | Aperfeiçoamento das instruções |
| LLM | Grande modelo de linguagem |
| Transformer | Arquitetura baseada em atenção |
| Foundation Model | Modelo de base reutilizável |
| Multimodal | Processa diferentes modalidades |
| Diffusion | Geração por remoção gradual de ruído |

> 🔥 **DECORAÇÃO:** Token = unidade; Chunk = pedaço; Embedding = representação; Vetor = números; Prompt = instrução; Transformer = arquitetura; FM = modelo de base; Multimodal = vários tipos de dados; Diffusion = remoção de ruído.

---

### 2️⃣ Identificar possíveis casos de uso para modelos de IA generativa

<p align="justify">A IA generativa pode produzir diferentes tipos de conteúdo e apoiar atividades empresariais, automatizando tarefas e facilitando o acesso à informação.</p>

<h3><strong style='color: skyblue'>🖼️ Geração de imagens</strong></h3>

<p align="justify">Criação ou edição de imagens a partir de descrições textuais ou outras imagens.</p>

Exemplos:

- criar imagens para campanhas publicitárias;
- gerar ilustrações;
- produzir imagens de produtos;
- criar conceitos visuais;
- editar imagens existentes.

> **DECORA:** texto → imagem.

---

<h3><strong style='color: skyblue'>🎵 Geração de áudio</strong></h3>

<p align="justify">Criação de conteúdo sonoro, fala ou outros tipos de áudio.</p>

Exemplos:

- transformar texto em fala;
- gerar narrações;
- criar vozes sintéticas;
- produzir conteúdo de áudio;
- gerar efeitos sonoros.

> **DECORA:** texto → áudio ou geração de áudio.

---

<h3><strong style='color: skyblue'>🎬 Geração de vídeo</strong></h3>

<p align="justify">Criação ou transformação de vídeos utilizando instruções textuais, imagens ou outros conteúdos.</p>

Exemplos:

- criar vídeos publicitários;
- gerar animações;
- produzir vídeos explicativos;
- criar cenas a partir de descrições;
- editar conteúdo audiovisual.

> **DECORA:** prompt ou imagem → vídeo.

---

<h3><strong style='color: skyblue'>📝 Resumo de conteúdo</strong></h3>

<p align="justify">Transformação de textos ou documentos extensos em versões menores que preservam as informações principais.</p>

Exemplos:

- resumir contratos;
- resumir relatórios;
- sintetizar reuniões;
- resumir artigos;
- extrair pontos importantes de documentos.

> **DECORA:** conteúdo extenso → informações essenciais.

---

<h3><strong style='color: skyblue'>🤖 Assistentes de IA</strong></h3>

<p align="justify">Aplicações conversacionais que respondem perguntas, auxiliam usuários e executam tarefas conforme suas capacidades.</p>

Exemplos:

- assistente para funcionários;
- assistente de estudos;
- assistente de produtividade;
- assistente para análise de documentos;
- assistente de suporte técnico.

> **DECORA:** assistente de IA = interação conversacional para ajudar em tarefas.

---

<h3><strong style='color: skyblue'>🌎 Tradução</strong></h3>

<p align="justify">Conversão de conteúdo entre diferentes idiomas, preservando o significado e considerando o contexto.</p>

Exemplos:

- traduzir documentos;
- traduzir mensagens;
- traduzir páginas;
- auxiliar na comunicação internacional.

> **DECORA:** idioma A → idioma B.

---

<h3><strong style='color: skyblue'>💻 Geração de código</strong></h3>

<p align="justify">Criação, explicação, revisão ou transformação de código a partir de instruções em linguagem natural.</p>

Exemplos:

- gerar funções Python;
- criar consultas SQL;
- explicar erros;
- sugerir correções;
- gerar testes;
- documentar código.

> **DECORA:** instrução em linguagem natural → código.

---

<h3><strong style='color: skyblue'>🎧 Atendentes de suporte ao cliente</strong></h3>

<p align="justify">Soluções que respondem dúvidas, consultam informações e auxiliam clientes durante o atendimento.</p>

Exemplos:

- responder perguntas frequentes;
- consultar status de pedidos;
- orientar sobre produtos;
- encaminhar solicitações;
- oferecer atendimento contínuo.

> **DECORA:** GenAI pode melhorar o atendimento com respostas contextualizadas e conversacionais.

---

<h3><strong style='color: skyblue'>🔎 Pesquisa — Search</strong></h3>

<p align="justify">Aplicações que permitem localizar informações relevantes em grandes volumes de dados, inclusive utilizando significado e contexto em vez de depender apenas de palavras exatas.</p>

Exemplos:

- pesquisar documentos corporativos;
- localizar informações em manuais;
- consultar bases de conhecimento;
- recuperar trechos relevantes para responder perguntas.

> **DECORA:** pesquisa semântica = buscar pelo significado, não apenas pela correspondência exata de palavras.

---

<h3><strong style='color: skyblue'>🎯 Mecanismos de recomendação</strong></h3>

<p align="justify">Sistemas que sugerem conteúdos, produtos ou serviços com base em preferências, histórico e características dos usuários.</p>

Exemplos:

- recomendar filmes;
- sugerir produtos;
- recomendar músicas;
- personalizar conteúdo;
- sugerir cursos.

> **DECORA:** recomendação = sugerir algo relevante para determinado usuário.

---

### 🧠 Tabela de casos de uso

| Caso de uso | Aplicação |
|---|---|
| Imagem | Criar ilustrações e imagens |
| Áudio | Gerar fala e narrações |
| Vídeo | Criar vídeos e animações |
| Resumo | Reduzir documentos extensos |
| Assistente | Responder e auxiliar usuários |
| Tradução | Converter idiomas |
| Código | Gerar e explicar programas |
| Atendimento | Responder clientes |
| Pesquisa | Encontrar informações relevantes |
| Recomendação | Sugerir produtos e conteúdos |

> 🔥 **PEGADINHA:** IA generativa não serve apenas para criar textos. Ela também pode gerar imagens, áudio, vídeos, código e apoiar pesquisa e recomendação.

---

### 3️⃣ Descrever o ciclo de vida do modelo de base (Foundation Model)

<p align="justify">O ciclo de vida de um Foundation Model envolve etapas desde a escolha dos dados e do modelo até o treinamento, avaliação, implantação e coleta de feedback.</p>

<pre>
SELEÇÃO DE DADOS
       ↓
SELEÇÃO DO MODELO
       ↓
PRÉ-TREINAMENTO
       ↓
AJUSTE FINO / FINE-TUNING
       ↓
AVALIAÇÃO
       ↓
IMPLANTAÇÃO
       ↓
FEEDBACK
       ↺
```
</pre>
---

<h3><strong style='color: skyblue'>📥 Seleção de dados</strong></h3>

<p align="justify">Escolha dos dados utilizados para treinar ou adaptar o modelo.</p>

É importante considerar:

- qualidade;
- quantidade;
- diversidade;
- relevância;
- representatividade;
- direitos de uso;
- privacidade;
- possíveis vieses.

> **DECORA:** seleção de dados = escolher os dados adequados para o modelo.

---

<h3><strong style='color: skyblue'>🧠 Seleção do modelo</strong></h3>

<p align="justify">Escolha do Foundation Model mais adequado ao caso de uso.</p>

Fatores importantes:

- capacidade do modelo;
- tipo de tarefa;
- modalidade de dados;
- custo;
- latência;
- desempenho;
- idioma;
- requisitos de segurança e conformidade.

Exemplo:

```text
Necessidade: gerar textos
       ↓
Modelo de linguagem

Necessidade: gerar imagens
       ↓
Modelo de geração de imagens
```

> **DECORA:** selecionar o modelo = escolher a base mais adequada para o problema.

---

<h3><strong style='color: skyblue'>🏋️ Pré-treinamento — Pre-training</strong></h3>

<p align="justify">Etapa em que o modelo aprende padrões gerais a partir de grandes volumes de dados.</p>

Exemplo:

```text
Grandes volumes de dados
          ↓
    Pré-treinamento
          ↓
Foundation Model
```

O modelo aprende padrões de linguagem, estruturas, relações e características dos dados.

> **DECORA:** Pre-training = aprendizado inicial em grande escala.

---

<h3><strong style='color: skyblue'>🎯 Ajuste fino — Fine-tuning</strong></h3>

<p align="justify">Processo de adaptar um modelo previamente treinado para uma tarefa, domínio ou comportamento mais específico.</p>

Exemplo:

```text
Foundation Model
       ↓
Fine-tuning
       ↓
Modelo especializado
       ↓
Atendimento bancário
```

Pode ser utilizado para:

- especializar o modelo em determinado domínio;
- adaptar o comportamento;
- melhorar o desempenho em uma tarefa;
- ajustar respostas a necessidades específicas.

> **DECORA:** Fine-tuning = adaptar um modelo já treinado.

> **PEGADINHA:** Fine-tuning não é necessariamente treinar um modelo do zero.

---

<h3><strong style='color: skyblue'>📊 Avaliação</strong></h3>

<p align="justify">Verificação da qualidade, desempenho e adequação do modelo ao caso de uso.</p>

Pode considerar:

- precisão das respostas;
- qualidade do conteúdo;
- relevância;
- segurança;
- consistência;
- latência;
- custo;
- comportamento diante de diferentes entradas.

> **DECORA:** avaliação = verificar se o modelo atende aos requisitos.

---

<h3><strong style='color: skyblue'>🚀 Implantação — Deployment</strong></h3>

<p align="justify">Disponibilização do modelo para utilização em aplicações reais.</p>

Exemplo:

```text
Modelo avaliado
       ↓
Deployment
       ↓
API / Aplicação
       ↓
Usuários
```

Pode ser realizado por serviços gerenciados ou infraestrutura própria.

> **DECORA:** Deployment = colocar o modelo em uso.

---

<h3><strong style='color: skyblue'>💬 Feedback</strong></h3>

<p align="justify">Coleta de informações sobre o comportamento do modelo e a experiência dos usuários após sua disponibilização.</p>

Exemplos:

- avaliações dos usuários;
- respostas consideradas incorretas;
- reclamações;
- qualidade das respostas;
- taxa de utilização;
- resultados do negócio.

O feedback pode orientar:

- ajustes nos prompts;
- melhoria do contexto;
- mudanças nos dados;
- fine-tuning;
- substituição do modelo;
- novas avaliações.

> **DECORA:** feedback = aprender com o uso real e melhorar a solução.

---

### 🧠 Tabela do ciclo de vida do FM

| Etapa | Objetivo |
|---|---|
| Seleção de dados | Escolher os dados adequados |
| Seleção do modelo | Escolher o modelo-base |
| Pré-treinamento | Aprender padrões gerais |
| Fine-tuning | Adaptar para uma necessidade específica |
| Avaliação | Verificar qualidade e desempenho |
| Deployment | Disponibilizar para uso |
| Feedback | Identificar melhorias |

> 🔥 **PEGADINHA:** pré-treinamento cria a base de conhecimento geral; fine-tuning especializa o modelo; feedback identifica oportunidades de melhoria após o uso.

---

### 4️⃣ Descrever o modelo de precificação baseado em tokens e seu efeito no custo e no desempenho para inferência

<h3><strong style='color: skyblue'>💰 Como funciona a cobrança por tokens?</strong></h3>

<p align="justify">Em muitos serviços de IA generativa, o custo de inferência é calculado com base na quantidade de tokens processados pelo modelo.</p>

Existem dois grupos importantes:

- **Tokens de entrada (Input Tokens):** informações enviadas ao modelo.
- **Tokens de saída (Output Tokens):** conteúdo gerado pelo modelo.

<pre>
USUÁRIO
   │
   ▼
PROMPT / CONTEXTO
   │
   ▼
TOKENS DE ENTRADA
   │
   ▼
MODELO DE IA
   │
   ▼
TOKENS DE SAÍDA
   │
   ▼
RESPOSTA
</pre>

**Exemplo:**

Uma aplicação envia:

```text
Prompt: 1.000 tokens
Resposta: 500 tokens
```

O modelo processou:

- 1.000 tokens de entrada;
- 500 tokens de saída;
- 1.500 tokens no total.

A cobrança efetiva depende da tabela de preços do modelo e do serviço utilizado.

> **DECORA:** Input = o que envio. Output = o que o modelo gera.

---

<h3><strong style='color: skyblue'>💵 Fatores que influenciam o custo</strong></h3>

O custo pode variar conforme:

- quantidade de tokens de entrada;
- quantidade de tokens de saída;
- modelo escolhido;
- preço por milhão de tokens;
- quantidade de solicitações;
- recursos adicionais contratados;
- modalidade de inferência.

**Exemplo conceitual:**

| Modelo | Entrada | Saída |
|---|---:|---:|
| Modelo A | US$ 1 / milhão | US$ 4 / milhão |
| Modelo B | US$ 3 / milhão | US$ 12 / milhão |

Os valores são apenas ilustrativos, não preços reais de modelos AWS.

Para 1 milhão de tokens de entrada e 500 mil de saída:

```text
MODELO A

Entrada: 1 × US$ 1 = US$ 1
Saída:   0,5 × US$ 4 = US$ 2

Total = US$ 3
```

> **PEGADINHA:** modelos diferentes podem cobrar valores diferentes para a mesma quantidade de tokens.

---

<h3><strong style='color: skyblue'>⚡ Efeito no desempenho da inferência</strong></h3>

<p align="justify">A quantidade de tokens também pode influenciar o tempo necessário para processar uma solicitação e gerar uma resposta.</p>

**Mais tokens de entrada:**

- mais contexto para processar;
- maior consumo de recursos;
- potencial aumento da latência;
- possível aumento do custo.

**Mais tokens de saída:**

- respostas mais longas;
- maior consumo de recursos;
- maior tempo de geração;
- possível aumento do custo.

**Exemplo:**

```text
Prompt curto
     ↓
Menos tokens de entrada
     ↓
Menor processamento potencial

Prompt muito extenso
     ↓
Mais tokens de entrada
     ↓
Maior processamento potencial
```

> **DECORA:** mais tokens geralmente significam maior custo e podem aumentar a latência.

---

<h3><strong style='color: skyblue'>🎯 Como otimizar o consumo de tokens?</strong></h3>

- evitar instruções repetidas;
- remover informações irrelevantes;
- limitar o tamanho da resposta;
- utilizar chunking;
- recuperar apenas o contexto necessário;
- selecionar um modelo adequado à complexidade da tarefa;
- evitar enviar históricos inteiros quando não forem necessários.

**Exemplo:**

```text
PROMPT INEFICIENTE
Documento completo + histórico inteiro
              ↓
       Muitos tokens


PROMPT OTIMIZADO
Instruções + trechos relevantes
              ↓
       Menos tokens
```

> **PEGADINHA:** reduzir tokens indiscriminadamente pode prejudicar a qualidade. O objetivo é remover conteúdo desnecessário sem eliminar informações importantes.

---

### 5️⃣ Descrever o papel da engenharia de contexto em aplicações de FM

<h3><strong style='color: skyblue'>🧠 O que é Context Engineering?</strong></h3>

<p align="justify">Engenharia de contexto é a prática de selecionar, organizar e fornecer ao Foundation Model as informações necessárias para executar uma tarefa corretamente.</p>

<p align="justify">Enquanto a engenharia de prompts se concentra em formular boas instruções, a engenharia de contexto considera o conjunto mais amplo de informações disponibilizadas ao modelo.</p>

**O contexto pode incluir:**

- instruções;
- prompt;
- histórico da conversa;
- documentos;
- informações recuperadas;
- dados do usuário;
- resultados de ferramentas;
- memória;
- regras e restrições.

<pre>
             CONTEXTO
                 │
      ┌──────────┼──────────┐
      ▼          ▼          ▼
  Instruções  Histórico   Documentos
      │          │          │
      └──────────┼──────────┘
                 ▼
          Context Engineering
                 │
                 ▼
          Foundation Model
                 │
                 ▼
              Resposta
</pre>

> **DECORA:** Context Engineering = fornecer ao modelo as informações certas para a tarefa.

---

<h3><strong style='color: skyblue'>📝 Prompt Engineering × Context Engineering</strong></h3>

| Característica | Prompt Engineering | Context Engineering |
|---|---|---|
| Foco | Instruções | Contexto completo |
| Objetivo | Orientar a resposta | Fornecer informações relevantes |
| Elementos | Prompt, formato, exemplos | Prompt, histórico, dados, memória, ferramentas |
| Pergunta | Como devo instruir? | Quais informações o modelo precisa? |

**Exemplo prático:**

Uma empresa deseja criar um assistente para responder dúvidas sobre seus procedimentos internos.

**Somente Prompt Engineering:**

```text
Responda às dúvidas dos funcionários
sobre os procedimentos da empresa.
```

**Com Context Engineering:**

```text
Instruções:
Responda de forma objetiva.

Contexto:
Manual interno da empresa.
Políticas atualizadas.
Histórico da conversa.
Informações recuperadas da base documental.

Restrição:
Se não encontrar a informação,
informe que não há dados suficientes.
```

O segundo cenário oferece informações mais úteis para gerar uma resposta fundamentada.

---

<h3><strong style='color: skyblue'>📚 Contexto e RAG</strong></h3>

<p align="justify">RAG (Retrieval-Augmented Generation) é uma abordagem que recupera informações de fontes externas e as fornece ao modelo como contexto para gerar respostas mais fundamentadas.</p>

<pre>
PERGUNTA DO USUÁRIO
        ↓
BUSCA NA BASE DE CONHECIMENTO
        ↓
RECUPERAÇÃO DE TRECHOS RELEVANTES
        ↓
INCLUSÃO NO CONTEXTO
        ↓
FOUNDATION MODEL
        ↓
RESPOSTA FUNDAMENTADA
</pre>

**Exemplo:**

Um funcionário pergunta:

"Qual é a política de férias da empresa?"

O sistema:

1. recebe a pergunta;
2. pesquisa os documentos internos;
3. recupera o trecho sobre férias;
4. envia a pergunta e o trecho ao modelo;
5. gera uma resposta baseada no conteúdo recuperado.

> **DECORA:** RAG = recuperar informações externas + fornecer contexto ao modelo + gerar resposta.

**Por que a engenharia de contexto é importante?**

- melhora a relevância das respostas;
- reduz informações desnecessárias;
- ajuda a utilizar dados atualizados;
- permite incorporar conhecimento empresarial;
- auxilia na redução de alucinações;
- melhora a utilização de ferramentas e memória.

> **PEGADINHA:** RAG não é necessariamente retreinar o modelo. Ele fornece informações externas durante a inferência.

---

### 6️⃣ Definir conceitos fundamentais de IA agêntica

<h3><strong style='color: skyblue'>🤖 O que é IA agêntica?</strong></h3>

<p align="justify">IA agêntica (Agentic AI) utiliza agentes capazes de interpretar objetivos, planejar etapas, tomar decisões, utilizar ferramentas e executar ações para alcançar resultados.</p>

<p align="justify">Diferentemente de uma aplicação que apenas recebe uma pergunta e gera uma resposta, um agente pode executar várias etapas e interagir com sistemas externos.</p>

**IA generativa tradicional:**

```text
Usuário
   ↓
Modelo
   ↓
Resposta
```

**IA agêntica:**

```text
Usuário
   ↓
Agente
   ↓
Planejamento
   ↓
Uso de ferramentas
   ↓
Execução de ações
   ↓
Avaliação do resultado
   ↓
Resposta / Próxima ação
```

**Exemplo prático:**

Usuário solicita:

"Pesquise os melhores voos para São Paulo e organize as opções."

O agente pode:

1. interpretar o objetivo;
2. consultar uma ferramenta de pesquisa;
3. comparar os resultados;
4. organizar as opções;
5. apresentar uma resposta.

> **DECORA:** IA generativa gera conteúdo; IA agêntica pode planejar e executar ações usando ferramentas.

---

<h3><strong style='color: skyblue'>🤝 Sistemas multiagentes — Multi-Agent Systems</strong></h3>

<p align="justify">Sistemas multiagentes utilizam vários agentes especializados que colaboram para resolver tarefas complexas.</p>

Em vez de um único agente executar tudo, diferentes agentes podem assumir responsabilidades específicas.

**Exemplo: planejamento de uma viagem**

```text
             AGENTE SUPERVISOR
                     │
        ┌────────────┼────────────┐
        ▼            ▼            ▼
   Agente de     Agente de    Agente de
    voos          hotéis      atividades
        │            │            │
        ▼            ▼            ▼
    Pesquisa     Pesquisa     Pesquisa
        │            │            │
        └────────────┼────────────┘
                     ▼
             AGENTE SUPERVISOR
                     │
                     ▼
              Resultado final
```

**Vantagens:**

- divisão de tarefas;
- especialização;
- execução paralela;
- melhor organização de fluxos complexos;
- possibilidade de combinar resultados.

> **DECORA:** multiagente = vários agentes especializados trabalhando em conjunto.

---

<h3><strong style='color: skyblue'>🧩 Padrões de sistemas multiagentes</strong></h3>

Existem diferentes formas de organizar a colaboração entre agentes.

**1. Supervisor e colaboradores**

Um agente supervisor recebe a solicitação, divide o trabalho e coordena agentes especializados.

```text
Usuário
   ↓
Supervisor
   ├── Agente A
   ├── Agente B
   └── Agente C
          ↓
   Resultado consolidado
```

**2. Execução sequencial**

Os agentes executam tarefas em uma ordem definida. A saída de um agente pode ser utilizada pelo próximo.

```text
Agente A
   ↓
Agente B
   ↓
Agente C
   ↓
Resultado
```

**3. Execução paralela**

Vários agentes trabalham simultaneamente em partes diferentes da tarefa.

```text
        Solicitação
             │
      ┌──────┼──────┐
      ▼      ▼      ▼
   Agente A Agente B Agente C
      │      │      │
      └──────┼──────┘
             ▼
       Consolidar
```

**4. Handoff — Transferência**

Um agente transfere o controle da execução para outro agente mais adequado à próxima etapa.

```text
Agente de atendimento
          ↓
   Identifica problema
          ↓
   Transfere controle
          ↓
   Agente especializado
          ↓
      Solução
```

| Padrão | Funcionamento |
|---|---|
| Supervisor | Coordena outros agentes |
| Sequencial | Um agente executa após o outro |
| Paralelo | Vários agentes executam simultaneamente |
| Handoff | Um agente transfere o controle para outro |

> **DECORA:** supervisor coordena; sequencial ordena; paralelo divide simultaneamente; handoff transfere o controle.

---

<h3><strong style='color: skyblue'>🔌 Model Context Protocol — MCP</strong></h3>

<p align="justify">MCP (Model Context Protocol) é um protocolo aberto que padroniza a comunicação entre aplicações de IA e sistemas externos, como ferramentas, fontes de dados e serviços.</p>

<p align="justify">Ele permite que agentes e aplicações de IA descubram e utilizem recursos externos por meio de uma interface padronizada, sem precisar desenvolver uma integração completamente diferente para cada sistema.</p>

**Exemplo:**

Um agente precisa consultar informações em um banco de dados.

```text
Agente de IA
     ↓
Cliente MCP
     ↓
Servidor MCP
     ↓
Banco de dados
     ↓
Resultado
     ↓
Agente de IA
```

**O MCP pode conectar aplicações a:**

- bancos de dados;
- arquivos;
- APIs;
- ferramentas;
- sistemas corporativos;
- fontes de informação.

**Conceitos importantes:**

| Componente | Função |
|---|---|
| MCP Host | Aplicação que utiliza recursos MCP |
| MCP Client | Componente que estabelece a conexão |
| MCP Server | Expõe ferramentas e recursos externos |

**O que o MCP disponibiliza?**

- **Tools:** ações que o modelo pode solicitar.
- **Resources:** informações e dados disponibilizados.
- **Prompts:** modelos de instruções reutilizáveis.

> 🔥 **DECORA:** MCP = protocolo padronizado para conectar aplicações e agentes de IA a ferramentas e sistemas externos.

> **PEGADINHA:** MCP não é um modelo de IA e não é, por si só, o agente. É um protocolo de integração.

**MCP × comunicação entre agentes:**

O MCP é principalmente utilizado para conectar aplicações de IA a ferramentas e fontes externas. A comunicação direta entre agentes também pode utilizar protocolos e padrões específicos, como A2A (Agent-to-Agent).

---

<h3><strong style='color: skyblue'>💾 Gerenciamento de memória — Memory Management</strong></h3>

<p align="justify">Memória permite que agentes mantenham informações relevantes de interações anteriores, estados de tarefas e dados necessários para dar continuidade ao trabalho.</p>

**Tipos de memória:**

**1. Memória de curto prazo**

Mantém informações da interação ou tarefa atual.

Exemplo:

```text
Usuário:
"Meu destino é Brasília."

Agente:
Utiliza essa informação
durante a conversa atual.
```

**2. Memória de longo prazo**

Armazena informações úteis para interações futuras.

Exemplo:

```text
Preferência do usuário:
Prefere voos sem escalas.

Agente:
Pode utilizar essa preferência
em uma próxima solicitação.
```

| Tipo | Característica |
|---|---|
| Curto prazo | Contexto da tarefa ou conversa atual |
| Longo prazo | Informações persistentes para uso futuro |

**Por que a memória é importante?**

- mantém continuidade;
- evita repetir perguntas;
- permite personalização;
- preserva informações relevantes;
- ajuda a executar tarefas de várias etapas.

> **DECORA:** memória de curto prazo = contexto atual; memória de longo prazo = informações persistentes.

---

<h3><strong style='color: skyblue'>🛠️ Uso de ferramentas — Tool Use</strong></h3>

<p align="justify">Tool Use é a capacidade de um agente utilizar ferramentas externas para obter informações ou executar ações que não seriam realizadas apenas pela geração de texto.</p>

Exemplos:

- consultar APIs;
- pesquisar na internet;
- consultar bancos de dados;
- executar código;
- enviar mensagens;
- consultar sistemas empresariais;
- realizar cálculos.

**Exemplo:**

```text
Usuário:
"Qual é a cotação atual do dólar?"

        ↓

Agente identifica necessidade
        ↓
Consulta ferramenta de cotação
        ↓
Recebe o resultado
        ↓
Interpreta os dados
        ↓
Responde ao usuário
```

> **DECORA:** Tool Use = agente utiliza ferramentas para obter dados ou executar ações.

> **PEGADINHA:** o modelo não precisa conhecer previamente todas as informações. Ele pode consultar ferramentas externas durante a execução.

---

<h3><strong style='color: skyblue'>🔄 Orquestração de fluxo de trabalho — Workflow Orchestration</strong></h3>

<p align="justify">Orquestração é a coordenação das etapas, agentes, ferramentas e dependências necessárias para concluir uma tarefa.</p>

Pode envolver:

- definir a ordem das tarefas;
- distribuir atividades;
- coordenar agentes;
- controlar dependências;
- gerenciar resultados;
- tratar falhas;
- acompanhar o progresso.

**Exemplo: processo de análise de crédito**

```text
Solicitação
     ↓
Agente recebe os dados
     ↓
Agente consulta cadastro
     ↓
Agente analisa informações
     ↓
Agente verifica regras
     ↓
Resultado consolidado
     ↓
Resposta ao sistema
```

> **DECORA:** orquestração = coordenar quem faz o quê, em qual ordem e com quais resultados.

---

<h3><strong style='color: skyblue'>🧠 Multiagentes × MCP × Memória × Ferramentas × Orquestração</strong></h3>

| Conceito | Função |
|---|---|
| Multiagentes | Vários agentes colaboram |
| MCP | Conecta aplicações a ferramentas e dados externos |
| Memória | Mantém informações e histórico |
| Tool Use | Permite executar ações e consultar sistemas |
| Orquestração | Coordena tarefas e fluxos de execução |

> 🔥 **PEGADINHA:** são conceitos relacionados, mas não são sinônimos. Cada um resolve uma parte diferente da arquitetura agêntica.

---

<h3><strong style='color: skyblue'>🔥 DECORAÇÃO FINAL — O que realmente memorizar</strong></h3>

> **1. Token:** unidade de processamento do modelo; não é necessariamente uma palavra inteira.

> **2. Chunking:** divisão de documentos em partes menores.

> **3. Embedding:** representação numérica que captura características semânticas.

> **4. Vetor:** sequência de números utilizada para representar informações.

> **5. Prompt Engineering:** melhorar as instruções enviadas ao modelo.

> **6. Transformer:** arquitetura baseada em mecanismos de atenção.

> **7. LLM:** grande modelo de linguagem.

> **8. Foundation Model:** modelo de base reutilizável para diferentes aplicações.

> **9. Multimodal:** trabalha com diferentes tipos de dados, como texto, imagem, áudio e vídeo.

> **10. Diffusion:** gera conteúdo por meio da remoção gradual de ruído.

> **11. Casos de uso:** texto, imagem, áudio, vídeo, resumo, tradução, código, atendimento, pesquisa e recomendação.

> **12. Pré-treinamento:** aprendizado inicial em grandes volumes de dados.

> **13. Fine-tuning:** adaptação de um modelo previamente treinado.

> **14. Avaliação:** verifica qualidade e desempenho.

> **15. Deployment:** disponibiliza o modelo para uso.

> **16. Feedback:** identifica problemas e oportunidades de melhoria.

> **17. Input Tokens:** tokens enviados ao modelo.

> **18. Output Tokens:** tokens gerados pelo modelo.

> **19. Mais tokens:** geralmente significam maior custo e podem aumentar a latência.

> **20. Context Engineering:** fornece informações relevantes para o modelo executar a tarefa.

> **21. RAG:** recupera informações externas e as fornece como contexto.

> **22. IA agêntica:** planeja e executa ações para alcançar objetivos.

> **23. Multiagentes:** vários agentes especializados colaboram.

> **24. MCP:** conecta aplicações de IA a ferramentas e sistemas externos.

> **25. Memória:** mantém informações de curto ou longo prazo.

> **26. Tool Use:** permite ao agente utilizar ferramentas externas.

> **27. Orquestração:** coordena tarefas, agentes e etapas.

---

<h3><strong style='color: skyblue'>⚠️ PEGADINHAS DE PROVA</strong></h3>

- **Token ≠ palavra inteira.**
- **Chunking ≠ treinamento:** é divisão de conteúdo.
- **Embedding ≠ vetor:** embedding é a representação; vetor é a estrutura numérica.
- **LLM ≠ todo Foundation Model:** existem FMs que trabalham com outras modalidades.
- **Multimodal ≠ somente texto:** pode combinar texto, imagem, áudio e vídeo.
- **Transformer ≠ Diffusion:** são abordagens diferentes.
- **Diffusion:** geração por remoção gradual de ruído.
- **Pré-treinamento ≠ Fine-tuning:** o primeiro aprende padrões gerais; o segundo adapta o modelo.
- **Fine-tuning ≠ RAG:** fine-tuning modifica/adapta o modelo; RAG fornece informações externas durante a inferência.
- **Input Tokens ≠ Output Tokens:** entrada é enviada; saída é gerada.
- **Mais contexto pode melhorar a resposta, mas também aumenta consumo de tokens.**
- **Prompt Engineering ≠ Context Engineering:** instruções são apenas uma parte do contexto.
- **RAG ≠ retreinamento:** recupera informações externas para fornecer contexto.
- **IA generativa ≠ IA agêntica:** gerar conteúdo não significa necessariamente executar ações.
- **MCP ≠ modelo de IA:** é um protocolo de integração.
- **Multiagente ≠ agente único:** envolve colaboração entre agentes.
- **Memória ≠ ferramenta:** memória mantém informações; ferramentas permitem executar ações.
- **Orquestração ≠ execução de uma única ferramenta:** coordena todo o fluxo de trabalho.

---

## 🎯 REGRA DE OURO DA TAREFA 2.1

<pre>
TOKEN       → unidade de processamento
CHUNKING    → divide documentos
EMBEDDING   → representa significado
VETOR       → números
PROMPT      → instrução
TRANSFORMER → atenção
LLM         → modelo de linguagem
FM          → modelo de base
MULTIMODAL  → vários tipos de dados
DIFFUSION   → remove ruído para gerar conteúdo

PRE-TRAINING → aprende padrões gerais
FINE-TUNING  → especializa
RAG          → recupera informações externas
DEPLOYMENT   → disponibiliza
FEEDBACK     → melhora

INPUT TOKENS  → entrada
OUTPUT TOKENS → saída
MAIS TOKENS   → maior custo potencial

CONTEXT ENGINEERING → organiza informações relevantes

IA AGÊNTICA → planeja e executa
MULTIAGENTE  → agentes colaboram
MCP          → conecta a ferramentas e dados
MEMÓRIA      → mantém informações
TOOL USE     → executa ações
ORQUESTRAÇÃO → coordena o fluxo
</pre>
