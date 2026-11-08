## Declaração de tarefa 2.3 — Descrever a infraestrutura e as tecnologias da AWS para criar aplicações de IA generativa

### 1️⃣ Identificar serviços e recursos da AWS para desenvolver aplicações de IA generativa

<h3><strong style='color: skyblue'>Amazon Bedrock</strong></h3>

<p align="justify">O Amazon Bedrock é um serviço gerenciado que permite criar aplicações de IA generativa utilizando modelos de base (Foundation Models — FMs) de diferentes provedores, por meio de uma API unificada. Não é necessário treinar modelos do zero nem gerenciar toda a infraestrutura de execução.</p>

**Principais recursos:**
- Acesso a modelos de diferentes provedores.
- Experimentação e avaliação de modelos.
- Personalização de modelos com dados próprios.
- Integração com aplicações por APIs.
- Knowledge Bases para implementar RAG.
- Guardrails para aplicar controles de segurança e uso responsável.
- Recursos para criação de agentes e fluxos de trabalho.

**Quando utilizar:** Quando a organização deseja desenvolver aplicações generativas sem precisar administrar diretamente toda a infraestrutura de modelos.

> **DECORA:** Bedrock = consumir modelos de base e construir aplicações generativas de forma gerenciada.

<h3><strong style='color: skyblue'>Amazon SageMaker AI</strong></h3>

<p align="justify">O Amazon SageMaker AI é um serviço gerenciado para desenvolver, treinar, personalizar, implantar e operar modelos de aprendizado de máquina e IA, incluindo modelos de base.</p>

**Principais recursos:**
- Preparação e processamento de dados.
- Desenvolvimento e treinamento de modelos.
- Ajuste fino (Fine-tuning).
- Implantação de modelos em endpoints.
- Inferência em escala.
- Monitoramento e gerenciamento do ciclo de vida dos modelos.
- Recursos de MLOps.

**Quando utilizar:** Quando a equipe precisa de maior controle sobre o desenvolvimento, treinamento, personalização e implantação dos modelos.

<h3><strong style='color: skyblue'>Amazon SageMaker JumpStart</strong></h3>

<p align="justify">O SageMaker JumpStart oferece acesso a modelos pré-treinados, algoritmos e soluções que podem ser descobertos, avaliados, personalizados e implantados no ambiente SageMaker.</p>

**Principais recursos:**
- Catálogo de modelos pré-treinados.
- Modelos de base e modelos de aprendizado de máquina.
- Avaliação e experimentação.
- Personalização com dados próprios.
- Implantação de modelos em infraestrutura gerenciada pelo SageMaker.

**Quando utilizar:** Quando a equipe deseja começar com um modelo existente e adaptá-lo ao seu caso de uso, em vez de desenvolver tudo do zero.

> **PEGADINHA:** JumpStart é um recurso do ecossistema SageMaker. Não é um serviço concorrente do SageMaker AI.

<h3><strong style='color: skyblue'>Amazon Quick</strong></h3>

<p align="justify">O Amazon Quick é uma solução de IA voltada à produtividade empresarial, permitindo que usuários obtenham respostas, insights e executem tarefas utilizando informações e fontes de dados corporativas.</p>

**Principais aplicações:**
- Pesquisa de informações empresariais.
- Análise e obtenção de insights.
- Consultas em linguagem natural.
- Automação de tarefas.
- Assistentes e recursos agênticos para atividades de negócio.

**Quando utilizar:** Quando usuários de negócio precisam consultar informações, pesquisar dados e automatizar atividades sem necessariamente desenvolver uma aplicação de IA do zero.

<h3><strong style='color: skyblue'>Kiro</strong></h3>

<p align="justify">O Kiro é um ambiente de desenvolvimento integrado (IDE) com recursos de IA, voltado à engenharia de software. Utiliza desenvolvimento orientado por especificações (Spec-driven Development), ajudando a transformar requisitos em especificações, tarefas e código.</p>

**Principais aplicações:**
- Apoio à escrita e compreensão de código.
- Geração de código.
- Planejamento de tarefas de desenvolvimento.
- Documentação técnica.
- Desenvolvimento orientado por especificações.
- Apoio à execução de tarefas de engenharia de software.

**Quando utilizar:** Quando desenvolvedores precisam acelerar o desenvolvimento de aplicações utilizando assistência de IA.

<h3><strong style='color: skyblue'>Strands Agents</strong></h3>

<p align="justify">Strands Agents é um SDK de código aberto da AWS para desenvolver agentes de IA. Permite criar agentes que utilizam modelos, ferramentas e instruções para executar tarefas e interagir com sistemas externos.</p>

**Principais recursos:**
- Desenvolvimento de agentes em Python e outras linguagens suportadas.
- Integração com modelos de IA.
- Uso de ferramentas externas.
- Suporte a padrões de agentes individuais e múltiplos agentes.
- Integração com protocolos como MCP.
- Orquestração de tarefas e fluxos de trabalho.

**Quando utilizar:** Quando desenvolvedores precisam construir agentes personalizados com flexibilidade de código e integração com diferentes ferramentas.

<h3><strong style='color: skyblue'>Amazon Bedrock AgentCore</strong></h3>

<p align="justify">O Amazon Bedrock AgentCore fornece infraestrutura gerenciada para implantar, operar e escalar agentes de IA com segurança. Pode trabalhar com diferentes modelos e frameworks de agentes, não ficando limitado a um único modelo ou SDK.</p>

**Principais componentes e recursos:**

| Componente | Função |
|---|---|
| Runtime | Executa agentes em ambiente gerenciado e isolado |
| Memory | Gerencia memória e contexto dos agentes |
| Gateway | Conecta agentes a ferramentas, APIs e serviços |
| Identity | Gerencia identidade e credenciais |
| Policy | Controla e autoriza ações dos agentes |
| Observability | Permite monitorar, rastrear e depurar agentes |
| Evaluations | Avalia a qualidade e o comportamento dos agentes |
| Browser | Permite interação com páginas e aplicações web |
| Code Interpreter | Permite executar código em ambiente isolado |

**Quando utilizar:** Quando a organização precisa levar agentes para produção, com isolamento, identidade, memória, controle de ferramentas, monitoramento e escalabilidade.

> **DECORA:** Strands Agents = desenvolver agentes. AgentCore = infraestrutura para executar, proteger, monitorar e escalar agentes.

<h3><strong style='color: skyblue'>Comparação dos principais serviços</strong></h3>

| Serviço ou recurso | Principal finalidade |
|---|---|
| Amazon Bedrock | Consumir FMs e desenvolver aplicações generativas |
| SageMaker AI | Desenvolver, treinar e implantar modelos |
| SageMaker JumpStart | Encontrar, personalizar e implantar modelos pré-treinados |
| Amazon Quick | Produtividade, pesquisa e insights empresariais |
| Kiro | Desenvolvimento de software assistido por IA |
| Strands Agents | Criar agentes de IA por meio de SDK |
| Bedrock AgentCore | Executar e operar agentes em escala |

**Diferença fundamental:**

- Bedrock: foco em utilizar modelos de base para aplicações generativas.
- SageMaker AI: foco em construir, treinar, personalizar e implantar modelos.
- JumpStart: acelera o início com modelos e soluções pré-treinados.
- Strands: facilita a criação de agentes.
- AgentCore: fornece infraestrutura para agentes em produção.

---

### 2️⃣ Descrever as vantagens de usar os serviços de IA generativa da AWS

<h3><strong style='color: skyblue'>Acessibilidade (Accessibility)</strong></h3>

<p align="justify">Os serviços gerenciados da AWS tornam os recursos de IA generativa mais acessíveis para organizações e desenvolvedores, mesmo quando não possuem equipes especializadas em treinamento e administração de modelos.</p>

**Exemplos:**
- Acesso a modelos de diferentes provedores pelo Bedrock.
- Uso de APIs para integrar IA às aplicações.
- Catálogos de modelos pré-treinados pelo JumpStart.
- Ferramentas de desenvolvimento assistido por IA.

<h3><strong style='color: skyblue'>Menor barreira de entrada (Lower Barrier to Entry)</strong></h3>

<p align="justify">Os serviços gerenciados reduzem a necessidade de desenvolver modelos do zero, configurar infraestrutura especializada e manter ambientes complexos de treinamento e inferência.</p>

**Exemplo:** Uma empresa pode criar um chatbot utilizando um modelo disponível no Bedrock, sem precisar construir e treinar seu próprio LLM.

<h3><strong style='color: skyblue'>Eficiência (Efficiency)</strong></h3>

<p align="justify">A AWS oferece serviços e recursos que automatizam partes do desenvolvimento e da operação de aplicações generativas, reduzindo o esforço operacional das equipes.</p>

**Benefícios:**
- Menos trabalho com infraestrutura.
- Reutilização de modelos existentes.
- Integração com serviços AWS.
- Automação de tarefas.
- Redução do tempo de desenvolvimento e manutenção.

<h3><strong style='color: skyblue'>Custo-benefício (Cost-effectiveness)</strong></h3>

<p align="justify">A utilização de serviços gerenciados e modelos pré-treinados pode reduzir o investimento inicial necessário para criar soluções generativas. A organização pode escolher modelos e modalidades de consumo adequados à demanda.</p>

**Exemplos:**
- Evitar custos de treinamento de modelos do zero.
- Utilizar modelos menores para tarefas simples.
- Pagar conforme o consumo, quando aplicável.
- Selecionar capacidade provisionada quando houver demanda previsível.

<h3><strong style='color: skyblue'>Velocidade de comercialização (Time to Market)</strong></h3>

<p align="justify">Permite desenvolver, testar e disponibilizar aplicações mais rapidamente, utilizando modelos existentes, ferramentas gerenciadas e integrações prontas.</p>

**Exemplo:** Uma equipe pode criar um assistente de atendimento com Bedrock e uma base de conhecimento, sem precisar desenvolver um modelo de linguagem próprio.

<h3><strong style='color: skyblue'>Capacidade de atingir objetivos empresariais</strong></h3>

<p align="justify">Os serviços permitem desenvolver soluções alinhadas às necessidades do negócio, como melhorar o atendimento, aumentar a produtividade, reduzir custos e gerar novas oportunidades de receita.</p>

**Exemplos:**
- Atendimento automatizado.
- Pesquisa em documentos corporativos.
- Análise de informações.
- Geração de relatórios.
- Assistentes para funcionários.
- Automação de processos.

> **DECORA:** A AWS reduz a barreira de entrada, simplifica a infraestrutura, acelera o desenvolvimento e permite concentrar esforços no resultado empresarial.

---

### 3️⃣ Descrever os benefícios da infraestrutura da AWS para aplicações de IA generativa

<h3><strong style='color: skyblue'>Proteção (Protection)</strong></h3>

<p align="justify">A AWS disponibiliza mecanismos de proteção para infraestrutura, aplicações e dados utilizados por soluções de IA generativa.</p>

**Recursos importantes:**

| Serviço ou recurso | Finalidade |
|---|---|
| AWS IAM | Controle de identidade e permissões |
| AWS KMS | Criptografia e gerenciamento de chaves |
| Amazon VPC | Isolamento e controle de rede |
| AWS PrivateLink | Conectividade privada com serviços compatíveis |
| AWS Secrets Manager | Armazenamento e gerenciamento de segredos |
| AWS CloudTrail | Registro de atividades e auditoria |
| AWS WAF | Proteção de aplicações web |
| AWS Shield | Proteção contra ataques DDoS |

**Exemplo:** Uma aplicação que utiliza Bedrock pode ter suas permissões controladas por IAM e seus recursos protegidos por mecanismos de criptografia e isolamento de rede.

<h3><strong style='color: skyblue'>Conformidade (Compliance)</strong></h3>

<p align="justify">A AWS mantém programas e recursos de conformidade que ajudam organizações a atender requisitos regulatórios e padrões de segurança aplicáveis aos seus ambientes.</p>

**Pontos importantes:**
- Programas de conformidade e certificações da AWS.
- Controles de acesso e auditoria.
- Criptografia de dados.
- Governança e políticas de segurança.
- Opções de localização e processamento regional.
- Documentação para apoiar auditorias.

**Atenção:** A utilização de um serviço AWS compatível com determinado padrão não significa que a aplicação do cliente esteja automaticamente em conformidade. A organização também precisa configurar e operar seus controles corretamente.

<h3><strong style='color: skyblue'>Responsabilidade compartilhada (Shared Responsibility Model)</strong></h3>

<p align="justify">A segurança na AWS segue o modelo de responsabilidade compartilhada. A AWS é responsável pela segurança da nuvem, enquanto o cliente é responsável pela segurança na nuvem. A divisão exata depende do serviço utilizado.</p>

<pre>
        RESPONSABILIDADE COMPARTILHADA
                    │
          ┌─────────┴─────────┐
          │                   │
      AWS                  CLIENTE
          │                   │
  Segurança da nuvem    Segurança na nuvem
          │                   │
  Infraestrutura física  Dados e permissões
  Hardware               Configurações
  Rede física            Aplicações
  Datacenters            Controle de acesso
                         Uso responsável
</pre>

**Responsabilidade da AWS:**
- Segurança física dos datacenters.
- Hardware e infraestrutura subjacente.
- Infraestrutura global da nuvem.
- Segurança dos componentes gerenciados pelo provedor.

**Responsabilidade do cliente:**
- Configurar permissões e acessos.
- Proteger dados e credenciais.
- Configurar aplicações.
- Definir políticas de uso.
- Validar entradas e saídas dos modelos.
- Monitorar o comportamento da solução.

> **PEGADINHA:** Mesmo utilizando serviços totalmente gerenciados, o cliente continua responsável por aspectos como dados, permissões e configurações de sua aplicação.

<h3><strong style='color: skyblue'>Segurança e uso responsável de IA (Safety and Responsible AI)</strong></h3>

<p align="justify">Além da segurança tradicional da infraestrutura, aplicações generativas precisam de controles específicos para reduzir riscos relacionados às entradas, respostas e ações dos modelos.</p>

**Recursos importantes do Amazon Bedrock:**

- Guardrails: ajudam a filtrar conteúdos indesejados, aplicar políticas e controlar entradas e saídas.
- Knowledge Bases: permitem fornecer informações de fontes corporativas por meio de RAG.
- Avaliação de modelos: ajuda a comparar qualidade, precisão e adequação ao caso de uso.
- Controles de acesso: limitam quem pode utilizar modelos e recursos.

**Exemplos de riscos que precisam ser tratados:**
- Respostas inadequadas ou prejudiciais.
- Vazamento de informações confidenciais.
- Injeção de prompts (Prompt Injection).
- Uso indevido de ferramentas por agentes.
- Geração de conteúdo não confiável.
- Decisões automatizadas sem supervisão adequada.

> **DECORA:** Segurança da infraestrutura protege a nuvem e os dados. Segurança de IA também precisa proteger entradas, saídas, ferramentas e ações dos agentes.

---

### 4️⃣ Descrever as compensações de custos dos serviços de IA generativa da AWS

<h3><strong style='color: skyblue'>Capacidade de resposta (Responsiveness)</strong></h3>

<p align="justify">A capacidade de resposta depende de fatores como tamanho do modelo, quantidade de tokens, processamento disponível, latência de rede e modalidade de inferência.</p>

**Considerações:**
- Modelos maiores podem exigir mais tempo de processamento.
- Respostas mais longas podem aumentar o tempo de geração.
- Modelos menores podem oferecer respostas mais rápidas e econômicas.
- Cache de prompts pode reduzir processamento repetido quando aplicável.

**Compensação:** Uma resposta mais rápida pode exigir um modelo menor, mais capacidade computacional ou recursos adicionais de otimização, dependendo da aplicação.

<h3><strong style='color: skyblue'>Disponibilidade (Availability)</strong></h3>

<p align="justify">A disponibilidade representa a capacidade de manter o serviço acessível quando a aplicação precisa utilizá-lo.</p>

**Considerações:**
- Disponibilidade do serviço na região escolhida.
- Limites e cotas de requisições.
- Capacidade de processamento disponível.
- Dependência de modelos e endpoints específicos.
- Necessidade de estratégias de contingência.

**Compensação:** Uma arquitetura com maior disponibilidade pode exigir recursos adicionais, redundância e custos operacionais mais elevados.

<h3><strong style='color: skyblue'>Redundância (Redundancy)</strong></h3>

<p align="justify">Consiste em manter recursos ou caminhos alternativos para reduzir o risco de indisponibilidade. Em aplicações generativas, pode envolver múltiplas regiões, endpoints ou modelos compatíveis.</p>

**Exemplos:**
- Utilizar uma região alternativa.
- Manter modelos alternativos.
- Configurar mecanismos de fallback.
- Distribuir a carga entre recursos disponíveis.

**Compensação:** A redundância aumenta a resiliência, mas pode elevar custos de infraestrutura, operação e transferência de dados.

<h3><strong style='color: skyblue'>Desempenho (Performance)</strong></h3>

<p align="justify">O desempenho envolve a capacidade de processar solicitações, gerar respostas e atender ao volume de usuários esperado.</p>

**Fatores importantes:**
- Tamanho e capacidade do modelo.
- Throughput (vazão de processamento).
- Tokens processados por segundo.
- Quantidade de solicitações simultâneas.
- Capacidade computacional disponível.

**Compensação:** Maior desempenho pode exigir modelos mais avançados, maior capacidade provisionada ou infraestrutura mais robusta, aumentando os custos.

<h3><strong style='color: skyblue'>Cobertura regional (Regional Coverage)</strong></h3>

<p align="justify">Nem todos os modelos e recursos estão disponíveis em todas as regiões da AWS. A escolha da região pode afetar disponibilidade, latência, conformidade e custo.</p>

**Considerações:**
- Disponibilidade do modelo na região.
- Localização dos usuários.
- Requisitos de residência dos dados.
- Latência entre aplicação e serviço.
- Possibilidade de inferência entre regiões.

**Opções de inferência do Amazon Bedrock:**

| Modalidade | Funcionamento | Principal consideração |
|---|---|---|
| In-Region | Processamento na região selecionada | Maior controle de localização |
| Cross-Region geográfica | Roteamento entre regiões de uma mesma área geográfica | Equilíbrio entre capacidade e limites geográficos |
| Cross-Region global | Roteamento entre regiões comerciais compatíveis | Maior flexibilidade de capacidade, com requisitos de residência a avaliar |

**Compensação:** A inferência entre regiões pode melhorar a disponibilidade e a capacidade de processamento, mas é necessário avaliar os requisitos de localização e residência dos dados.

<h3><strong style='color: skyblue'>Preços baseados em tokens (Token-based Pricing)</strong></h3>

<p align="justify">No Amazon Bedrock, diversos modelos utilizam cobrança baseada na quantidade de tokens processados. Normalmente, os tokens de entrada e os tokens de saída possuem preços diferentes.</p>

**Tokens de entrada (Input Tokens):**
- Instruções do prompt.
- Contexto enviado ao modelo.
- Histórico da conversa.
- Documentos e informações fornecidas.

**Tokens de saída (Output Tokens):**
- Respostas geradas.
- Textos produzidos.
- Conteúdo retornado pelo modelo.

**Exemplo simplificado:**

| Tipo | Quantidade | Preço ilustrativo |
|---|---:|---:|
| Entrada | 10.000 tokens | R$ 0,02 por mil tokens |
| Saída | 2.000 tokens | R$ 0,04 por mil tokens |

Cálculo:
- Entrada: 10 × R$ 0,02 = R$ 0,20.
- Saída: 2 × R$ 0,04 = R$ 0,08.
- Total: R$ 0,28.

<text color="secondary" size="xs">Valores meramente ilustrativos, não representam preços reais da AWS.</text>

**Compensação:**
- Mais tokens de entrada aumentam o custo de processamento.
- Mais tokens de saída aumentam o custo de geração.
- Contextos muito extensos podem elevar o custo.
- Modelos diferentes possuem preços diferentes.

> **DECORA:** Input = o que você envia. Output = o que o modelo gera. Ambos podem ser cobrados.

<h3><strong style='color: skyblue'>Throughput provisionado (Provisioned Throughput)</strong></h3>

<p align="justify">O Provisioned Throughput permite reservar capacidade de processamento para modelos compatíveis no Amazon Bedrock, oferecendo maior previsibilidade de capacidade para workloads com demanda conhecida.</p>

**Características:**
- Capacidade reservada para inferência.
- Maior previsibilidade de throughput.
- Adequado para aplicações com demanda consistente.
- Cobrança baseada na capacidade provisionada e no período contratado, conforme as condições do serviço.

**Compensação:**
- Pode oferecer previsibilidade para cargas de trabalho constantes.
- Exige compromisso financeiro com capacidade reservada.
- Pode ser menos econômico quando a utilização é baixa ou imprevisível.

**Exemplo:** Uma empresa que recebe milhares de solicitações continuamente pode avaliar capacidade provisionada para atender à demanda.

<h3><strong style='color: skyblue'>Modelos personalizados (Custom Models)</strong></h3>

<p align="justify">Modelos personalizados são modelos adaptados às necessidades específicas de uma organização, utilizando técnicas como fine-tuning ou outras formas de personalização suportadas pelo serviço.</p>

**Custos que devem ser considerados:**
- Preparação e qualidade dos dados.
- Treinamento ou personalização.
- Armazenamento dos artefatos.
- Implantação e inferência.
- Capacidade computacional.
- Manutenção e avaliação contínua.

**Compensação:**
- Podem melhorar o desempenho em tarefas específicas.
- Podem exigir investimento adicional.
- Aumentam a complexidade de desenvolvimento e manutenção.
- Nem sempre são necessários: prompt engineering ou RAG podem resolver o problema com menor esforço.

<h3><strong style='color: skyblue'>Comparação das modalidades e compensações</strong></h3>

| Fator | Benefício esperado | Possível custo ou desvantagem |
|---|---|---|
| Maior capacidade de resposta | Menor tempo de espera | Mais recursos ou otimizações |
| Maior disponibilidade | Menor risco de interrupção | Redundância e operação adicionais |
| Redundância | Maior resiliência | Custos duplicados ou adicionais |
| Maior desempenho | Mais processamento e throughput | Capacidade mais cara |
| Cobertura regional | Flexibilidade e proximidade | Restrições de disponibilidade e dados |
| Cobrança por tokens | Pagamento conforme utilização | Custos variáveis com o consumo |
| Throughput provisionado | Capacidade previsível | Compromisso financeiro |
| Modelos personalizados | Melhor adequação ao domínio | Treinamento e manutenção adicionais |

<h3><strong style='color: skyblue'>Modalidades de inferência e cobrança</strong></h3>

| Modalidade | Característica | Quando considerar |
|---|---|---|
| Sob demanda (On-Demand) | Paga pelo consumo, normalmente por tokens | Demanda variável ou inicial |
| Processamento em lote (Batch) | Processa grandes volumes de solicitações de forma assíncrona | Tarefas que não exigem resposta imediata |
| Throughput provisionado | Reserva capacidade de processamento | Demanda previsível e contínua |

**Exemplos:**

- On-Demand: chatbot que recebe solicitações variáveis durante o dia.
- Batch: geração de resumos para milhares de documentos durante a noite.
- Provisioned Throughput: aplicação empresarial com volume elevado e constante de solicitações.

> **PEGADINHA:** Batch é adequado para processamento assíncrono e não para aplicações que exigem resposta imediata. Provisioned Throughput reserva capacidade e não significa simplesmente pagar por tokens utilizados.

---

### 🧠 DECORAÇÃO FINAL — Tarefa 2.3

**1. Serviços e tecnologias AWS**

- Amazon Bedrock: acesso a modelos de base e criação de aplicações generativas.
- SageMaker AI: desenvolvimento, treinamento e implantação de modelos.
- SageMaker JumpStart: catálogo de modelos pré-treinados e soluções.
- Amazon Quick: pesquisa, insights e produtividade empresarial.
- Kiro: desenvolvimento de software assistido por IA.
- Strands Agents: SDK para criação de agentes.
- Bedrock AgentCore: infraestrutura para implantar, operar e escalar agentes.

**2. Vantagens dos serviços AWS**

- Acessibilidade: acesso facilitado a modelos.
- Menor barreira de entrada: não precisa construir modelos do zero.
- Eficiência: menos trabalho operacional.
- Custo-benefício: escolha de modelos e modalidades de cobrança.
- Velocidade de comercialização: desenvolvimento mais rápido.
- Objetivos empresariais: produtividade, redução de custos e novas receitas.

**3. Benefícios da infraestrutura AWS**

- Proteção: IAM, KMS, VPC, CloudTrail, WAF e Shield.
- Conformidade: programas e controles para apoiar requisitos regulatórios.
- Responsabilidade: modelo de responsabilidade compartilhada.
- Segurança de IA: Guardrails, controle de ferramentas e validação de entradas e saídas.

**4. Compensações de custos**

- Capacidade de resposta: velocidade versus recursos.
- Disponibilidade: continuidade versus custo.
- Redundância: resiliência versus infraestrutura adicional.
- Desempenho: throughput versus capacidade computacional.
- Cobertura regional: localização versus disponibilidade de modelos.
- Tokens: entrada e saída geram custos.
- Throughput provisionado: capacidade reservada versus compromisso financeiro.
- Modelos personalizados: adequação ao negócio versus custo de personalização.

### ⚠️ PEGADINHAS DE PROVA

1. Bedrock permite utilizar modelos de base sem precisar gerenciar toda a infraestrutura de treinamento.
2. SageMaker AI permite desenvolver, treinar e implantar modelos com maior controle.
3. JumpStart disponibiliza modelos pré-treinados para acelerar o desenvolvimento.
4. Amazon Quick é voltado à produtividade e aos insights empresariais.
5. Kiro é uma ferramenta de desenvolvimento de software assistido por IA.
6. Strands Agents é um SDK para desenvolver agentes; AgentCore oferece infraestrutura para operá-los.
7. Serviços gerenciados reduzem o trabalho operacional, mas não eliminam as responsabilidades do cliente.
8. AWS é responsável pela segurança da nuvem; o cliente é responsável pela segurança na nuvem.
9. Guardrails ajudam a controlar entradas e saídas dos modelos.
10. Mais redundância pode aumentar disponibilidade, mas também aumenta custos.
11. On-Demand é adequado para demanda variável; Batch para processamento assíncrono; Provisioned Throughput para capacidade reservada.
12. Inferência Cross-Region pode melhorar capacidade e disponibilidade, mas exige atenção à residência dos dados.
13. Cobrança por tokens considera entrada e saída, que podem ter preços diferentes.
14. Personalizar um modelo pode melhorar resultados específicos, mas aumenta custos e complexidade.
15. O modelo mais caro não é necessariamente o mais adequado para o objetivo empresarial.

### 🗺️ MAPA MENTAL

<pre>
AWS — INFRAESTRUTURA PARA IA GENERATIVA
│
├── SERVIÇOS
│   ├── Bedrock → Modelos de base
│   ├── SageMaker AI → Treinar e implantar
│   ├── JumpStart → Modelos pré-treinados
│   ├── Quick → Produtividade empresarial
│   ├── Kiro → Desenvolvimento de software
│   ├── Strands → Criar agentes
│   └── AgentCore → Operar agentes
│
├── VANTAGENS
│   ├── Acessibilidade
│   ├── Menor barreira de entrada
│   ├── Eficiência
│   ├── Custo-benefício
│   ├── Velocidade
│   └── Objetivos empresariais
│
├── INFRAESTRUTURA
│   ├── Proteção
│   ├── Conformidade
│   ├── Responsabilidade compartilhada
│   └── Segurança e uso responsável
│
└── CUSTOS E COMPENSAÇÕES
    ├── Capacidade de resposta
    ├── Disponibilidade
    ├── Redundância
    ├── Desempenho
    ├── Cobertura regional
    ├── Tokens de entrada e saída
    ├── Throughput provisionado
    └── Modelos personalizados
</pre>
