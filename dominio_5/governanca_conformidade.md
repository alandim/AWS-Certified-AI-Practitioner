## 🏛️ Tarefa 5.2: Reconhecer os regulamentos de governança e conformidade de sistemas de IA

### 1️⃣ 🛡️ Serviços e recursos AWS para governança e conformidade

<h3><strong style='color: skyblue'>⚙️ AWS Config</strong></h3>

<p align="justify">O AWS Config permite avaliar, auditar e monitorar as configurações dos recursos AWS. Ele mantém um histórico das alterações de configuração e verifica se os recursos estão de acordo com regras e requisitos definidos pela organização.</p>

Principais recursos:

- 📋 **Configuração de recursos:** registra informações sobre como os recursos AWS estão configurados.
- 🔄 **Histórico de alterações:** permite acompanhar mudanças nas configurações ao longo do tempo.
- ⚖️ **Regras de conformidade (Config Rules):** avalia se os recursos atendem a requisitos definidos.
- 🚨 **Detecção de não conformidade:** identifica recursos que não seguem as regras estabelecidas.
- 📦 **Conformance Packs:** agrupam regras e ações de remediação para avaliar conjuntos de controles.
- 🔎 **Auditoria:** ajuda a demonstrar se configurações seguem padrões internos e requisitos de segurança.

<h3><strong style='color: skyblue'>📦 Exemplo prático</strong></h3>

Uma empresa utiliza Amazon S3 para armazenar documentos usados por uma aplicação de IA.

A organização determina que todos os buckets devem bloquear o acesso público.

O AWS Config pode:

1. 🔍 Verificar a configuração dos buckets.
2. ⚖️ Avaliar a regra que exige bloqueio de acesso público.
3. 🚨 Identificar buckets fora do padrão.
4. 📋 Registrar o estado de conformidade.
5. 🔄 Apoiar a correção da configuração.

> **DECORA:** AWS Config = verificar configurações dos recursos e avaliar conformidade com regras.

<h3><strong style='color: skyblue'>🔎 Amazon Inspector</strong></h3>

<p align="justify">O Amazon Inspector é um serviço de gerenciamento de vulnerabilidades que realiza avaliações contínuas de recursos compatíveis, identificando vulnerabilidades de software e possíveis exposições de segurança.</p>

Principais recursos:

- 🧰 **Análise de vulnerabilidades:** identifica vulnerabilidades conhecidas em softwares e componentes.
- 🖥️ **Amazon EC2:** avalia vulnerabilidades em instâncias e sistemas operacionais compatíveis.
- 📦 **Imagens de contêineres:** identifica vulnerabilidades em imagens armazenadas em repositórios compatíveis.
- ⚙️ **AWS Lambda:** pode identificar vulnerabilidades em dependências de funções compatíveis.
- 🚨 **Findings:** apresenta descobertas com informações sobre vulnerabilidades e riscos.
- 📊 **Priorização:** ajuda a identificar quais vulnerabilidades precisam de atenção.

<h3><strong style='color: skyblue'>📦 Exemplo prático</strong></h3>

Uma empresa executa uma aplicação de IA em instâncias EC2 e utiliza contêineres para hospedar componentes do sistema.

O Amazon Inspector pode identificar:

- 🐛 Bibliotecas com vulnerabilidades conhecidas.
- 🖥️ Pacotes desatualizados nas instâncias.
- 📦 Vulnerabilidades em imagens de contêineres.
- ⚠️ Problemas que precisam ser corrigidos por meio de atualizações ou patches.

> **DECORA:** Amazon Inspector = identificar e avaliar vulnerabilidades em softwares, instâncias, contêineres e outros recursos compatíveis. Não é uma ferramenta de auditoria de configurações gerais.

<h3><strong style='color: skyblue'>📄 AWS Artifact</strong></h3>

<p align="justify">O AWS Artifact é um portal de autoatendimento que permite acessar documentos relacionados à conformidade da AWS, incluindo relatórios de auditoria e determinados contratos e acordos.</p>

Principais recursos:

- 📋 **Relatórios de conformidade:** disponibiliza relatórios de auditoria relacionados a padrões como ISO e SOC.
- 📜 **Acordos:** permite acessar e gerenciar determinados acordos relacionados à utilização dos serviços AWS.
- 🔎 **Evidências:** fornece documentação que auxilia organizações em suas avaliações de conformidade.
- 🏢 **Auditorias:** ajuda empresas a obter documentos necessários para seus processos de auditoria.

<h3><strong style='color: skyblue'>📦 Exemplo prático</strong></h3>

Uma empresa precisa demonstrar aos seus auditores quais certificações e relatórios de conformidade são disponibilizados pela AWS.

Ela pode acessar o AWS Artifact para consultar relatórios de auditoria e documentos relacionados aos controles da infraestrutura AWS.

> **DECORA:** AWS Artifact = portal para acessar relatórios de conformidade e documentos e acordos relacionados à AWS. Não realiza auditorias diretamente na aplicação do cliente.

<h3><strong style='color: skyblue'>📋 AWS Audit Manager</strong></h3>

<p align="justify">O AWS Audit Manager ajuda a preparar, organizar e simplificar auditorias, coletando evidências relacionadas aos controles e requisitos de frameworks de conformidade.</p>

Principais recursos:

- 📚 **Frameworks:** disponibiliza estruturas de avaliação baseadas em padrões e requisitos de conformidade.
- 📋 **Controles:** organiza requisitos que precisam ser avaliados.
- 🔎 **Coleta de evidências:** reúne evidências automatizadas e manuais.
- 📊 **Avaliações:** acompanha o estado das evidências relacionadas aos controles.
- 📁 **Relatórios:** ajuda a organizar informações para auditorias.
- 🔄 **Monitoramento:** permite acompanhar a coleta de evidências durante uma avaliação ativa.

Pode coletar evidências de diferentes fontes:

- 📋 AWS Config: avaliações de regras de conformidade.
- 🧾 AWS CloudTrail: atividades realizadas por usuários e serviços.
- 🛡️ AWS Security Hub CSPM: descobertas de segurança.
- ⚙️ Chamadas de APIs AWS: informações sobre configurações de recursos.

<h3><strong style='color: skyblue'>📦 Exemplo prático</strong></h3>

Uma empresa precisa demonstrar que seus recursos AWS seguem controles de segurança definidos por um framework.

O Audit Manager pode:

1. 📚 Criar uma avaliação baseada no framework escolhido.
2. 📋 Associar controles aos requisitos.
3. 🔎 Coletar evidências de serviços como Config e CloudTrail.
4. 📁 Organizar as evidências.
5. 📊 Apoiar a preparação dos relatórios de auditoria.

> **DECORA:** AWS Audit Manager = organizar avaliações e coletar evidências para auditorias. Artifact fornece documentos de conformidade da AWS; Audit Manager reúne evidências da organização.

<h3><strong style='color: skyblue'>🧾 AWS CloudTrail</strong></h3>

<p align="justify">O AWS CloudTrail registra atividades realizadas na conta AWS, incluindo chamadas de API executadas por usuários, aplicações e serviços. É fundamental para auditoria, rastreabilidade e investigação de incidentes.</p>

Principais recursos:

- 👤 **Identidade:** identifica quem realizou determinada operação.
- 🕒 **Data e horário:** registra quando a atividade aconteceu.
- ⚙️ **Ação:** informa qual operação foi executada.
- 📦 **Recurso:** identifica o recurso AWS envolvido.
- 🌐 **Origem:** registra informações sobre a origem da solicitação, quando disponíveis.
- 📋 **Trilha de auditoria:** permite investigar alterações e acessos.

<h3><strong style='color: skyblue'>📦 Exemplo prático</strong></h3>

Um funcionário altera uma política IAM que permite a uma aplicação de IA acessar um bucket S3.

O CloudTrail pode registrar:

- 👤 Quem realizou a alteração.
- 🕒 Quando a alteração ocorreu.
- ⚙️ Qual chamada de API foi executada.
- 📦 Qual recurso foi modificado.

Isso permite investigar a mudança e verificar se ela foi autorizada.

> **DECORA:** CloudTrail = quem fez, o que fez e quando fez. É o serviço de registro de atividades e chamadas de API.

<h3><strong style='color: skyblue'>⭐ AWS Trusted Advisor</strong></h3>

<p align="justify">O AWS Trusted Advisor analisa o ambiente AWS e fornece recomendações com base em verificações de boas práticas. Ajuda a identificar oportunidades de melhoria em segurança, confiabilidade, desempenho, otimização de custos e limites de serviço.</p>

Principais áreas:

- 🔐 **Segurança:** identifica configurações que podem aumentar riscos.
- 🏗️ **Confiabilidade:** recomenda melhorias para aumentar a resiliência.
- ⚡ **Desempenho:** aponta oportunidades de otimização.
- 💰 **Otimização de custos:** identifica recursos que podem gerar gastos desnecessários.
- 📊 **Limites de serviço:** ajuda a acompanhar limites e utilização de recursos.

<h3><strong style='color: skyblue'>📦 Exemplo prático</strong></h3>

Uma empresa mantém diversos recursos AWS para executar uma aplicação de IA.

O Trusted Advisor pode recomendar:

- 🔐 Revisar configurações de segurança.
- 🏗️ Melhorar a tolerância a falhas.
- 💰 Reduzir custos de recursos subutilizados.
- ⚡ Otimizar configurações de desempenho.

> **DECORA:** Trusted Advisor = recomendações de boas práticas para segurança, confiabilidade, desempenho, custos e limites de serviço.

<h3><strong style='color: skyblue'>🧭 Comparação dos serviços AWS</strong></h3>

| Serviço | Pergunta que responde | Função principal |
|---|---|---|
| ⚙️ AWS Config | Como meus recursos estão configurados? | Configurações e conformidade |
| 🔎 Amazon Inspector | Existem vulnerabilidades? | Gerenciamento de vulnerabilidades |
| 📄 AWS Artifact | Onde obtenho relatórios de conformidade da AWS? | Documentos e acordos |
| 📋 AWS Audit Manager | Como organizo evidências para auditoria? | Avaliações e coleta de evidências |
| 🧾 AWS CloudTrail | Quem realizou uma ação e quando? | Registro de atividades |
| ⭐ AWS Trusted Advisor | O que posso melhorar no meu ambiente? | Recomendações de boas práticas |

> **DECORA:** Config = configuração; Inspector = vulnerabilidades; Artifact = relatórios; Audit Manager = evidências; CloudTrail = atividades; Trusted Advisor = recomendações.

---

### 2️⃣ 📚 Padrões de conformidade regulatória para sistemas de IA

<h3><strong style='color: skyblue'>🌐 ISO — International Organization for Standardization</strong></h3>

<p align="justify">A ISO é uma organização internacional que desenvolve padrões para diferentes áreas, incluindo segurança da informação, gestão de riscos e governança de inteligência artificial.</p>

Padrões importantes:

- 🔐 **ISO/IEC 27001:** requisitos para sistemas de gestão de segurança da informação (SGSI).
- 🧠 **ISO/IEC 42001:** requisitos para sistemas de gestão de inteligência artificial (AIMS).
- ⚖️ **ISO/IEC 23894:** orientações para gestão de riscos relacionados à inteligência artificial.

<h3><strong style='color: skyblue'>🧠 ISO/IEC 42001</strong></h3>

<p align="justify">A ISO/IEC 42001 estabelece requisitos para criar, implementar, manter e melhorar continuamente um sistema de gestão de inteligência artificial.</p>

Seu foco inclui:

- 📋 Políticas de governança de IA.
- ⚖️ Gestão de riscos.
- 👥 Responsabilidades organizacionais.
- 🔎 Monitoramento e avaliação.
- 🧾 Documentação e rastreabilidade.
- 🔄 Melhoria contínua.

<h3><strong style='color: skyblue'>🔐 ISO/IEC 27001</strong></h3>

<p align="justify">A ISO/IEC 27001 estabelece requisitos para um Sistema de Gestão de Segurança da Informação, ajudando organizações a proteger a confidencialidade, integridade e disponibilidade das informações.</p>

Exemplo:

Uma empresa que utiliza IA para processar documentos confidenciais pode adotar controles de segurança para proteger os dados e gerenciar riscos de acesso indevido.

> **DECORA:** ISO 27001 = gestão de segurança da informação. ISO 42001 = gestão de sistemas de inteligência artificial.

<h3><strong style='color: skyblue'>📋 SOC — System and Organization Controls</strong></h3>

<p align="justify">SOC é uma família de relatórios de auditoria que avalia controles de organizações prestadoras de serviços. Ajuda clientes e parceiros a entender como uma organização protege informações e administra seus controles.</p>

Principais tipos:

- 🔐 **SOC 1:** controles relevantes para relatórios financeiros das organizações clientes.
- 🛡️ **SOC 2:** controles relacionados a segurança, disponibilidade, integridade de processamento, confidencialidade e privacidade.
- 📊 **SOC 3:** relatório de uso mais geral, que apresenta informações sobre controles relacionados aos critérios de serviços de confiança.

<h3><strong style='color: skyblue'>🧩 SOC 2 — Critérios de serviços de confiança</strong></h3>

Os cinco critérios são:

- 🔐 **Security (Segurança):** proteção contra acesso não autorizado.
- 🏗️ **Availability (Disponibilidade):** sistemas disponíveis para operação conforme os compromissos estabelecidos.
- ⚙️ **Processing Integrity (Integridade de processamento):** processamento completo, válido, preciso e oportuno.
- 🔒 **Confidentiality (Confidencialidade):** proteção de informações confidenciais.
- 👤 **Privacy (Privacidade):** tratamento adequado de informações pessoais.

> **DECORA:** SOC 1 = controles relacionados a relatórios financeiros. SOC 2 = controles de confiança. SOC 3 = relatório de uso geral sobre esses controles.

<h3><strong style='color: skyblue'>⚖️ Leis de responsabilidade algorítmica (Algorithmic Accountability Laws)</strong></h3>

<p align="justify">Leis de responsabilidade algorítmica buscam estabelecer obrigações relacionadas à utilização de sistemas automatizados, especialmente quando suas decisões podem afetar direitos, oportunidades e interesses das pessoas.</p>

Possíveis requisitos:

- 🔎 **Transparência:** informar quando sistemas automatizados são utilizados, conforme a legislação aplicável.
- ⚖️ **Imparcialidade:** identificar e reduzir impactos discriminatórios.
- 📋 **Avaliação de impacto:** analisar riscos antes e durante a utilização.
- 👥 **Supervisão:** estabelecer mecanismos de revisão humana.
- 🧾 **Responsabilidade:** definir quem responde pelo desenvolvimento e utilização do sistema.
- 🔐 **Privacidade:** proteger os dados utilizados.

<h3><strong style='color: skyblue'>🇪🇺 GDPR e LGPD</strong></h3>

<p align="justify">Além dos padrões técnicos, sistemas de IA podem estar sujeitos a leis de proteção de dados pessoais, dependendo da localização dos titulares, da organização e do tratamento realizado.</p>

- 🇪🇺 **GDPR (Regulamento Geral sobre a Proteção de Dados):** legislação da União Europeia sobre proteção de dados pessoais.
- 🇧🇷 **LGPD (Lei Geral de Proteção de Dados):** legislação brasileira que estabelece regras para o tratamento de dados pessoais.

Aspectos importantes:

- 🔐 Proteção de dados pessoais.
- 📋 Finalidade e necessidade do tratamento.
- 👤 Direitos dos titulares.
- 🔎 Transparência sobre o tratamento.
- 🧾 Responsabilidade e prestação de contas.
- ⚖️ Cuidados com decisões automatizadas, conforme os requisitos legais aplicáveis.

> **DECORA:** ISO = padrões. SOC = relatórios de controles. GDPR e LGPD = leis de proteção de dados. Leis de responsabilidade algorítmica = responsabilização e avaliação de sistemas automatizados.

---

### 3️⃣ 🗂️ Estratégias de governança de dados

<h3><strong style='color: skyblue'>🔄 Ciclo de vida dos dados (Data Lifecycle)</strong></h3>

<p align="justify">O ciclo de vida dos dados representa as etapas pelas quais as informações passam, desde sua criação ou coleta até seu armazenamento, utilização, arquivamento e exclusão.</p>

Principais etapas:

- 📥 **Coleta:** obtenção de dados de fontes internas ou externas.
- 🧹 **Preparação:** limpeza, validação e transformação.
- 💾 **Armazenamento:** guarda dos dados em sistemas apropriados.
- 🧠 **Utilização:** processamento, análise e treinamento de modelos.
- 📊 **Monitoramento:** acompanhamento da qualidade e do uso.
- 📦 **Arquivamento:** preservação de dados que precisam ser mantidos.
- 🗑️ **Exclusão:** remoção segura quando não existe mais necessidade ou obrigação de retenção.

<h3><strong style='color: skyblue'>🔄 Exemplo de ciclo de vida em IA</strong></h3>

<pre>
Coleta de dados
      |
      v
Preparação e validação
      |
      v
Armazenamento
      |
      v
Treinamento / Inferência
      |
      v
Monitoramento
      |
      v
Arquivamento
      |
      v
Exclusão conforme política
</pre>

<h3><strong style='color: skyblue'>🧾 Registro em log (Logging)</strong></h3>

<p align="justify">Logging consiste em registrar eventos, atividades e operações realizadas nos sistemas, permitindo rastrear acessos, alterações, falhas e interações com aplicações de IA.</p>

Exemplos:

- 👤 Identidade de quem acessou os dados.
- 🕒 Data e horário do acesso.
- 📂 Recurso consultado.
- ⚙️ Operação executada.
- 🧠 Modelo utilizado.
- 📥 Solicitação enviada ao sistema de IA.
- 📤 Resultado produzido.
- 🚨 Eventos de erro ou segurança.

Serviços AWS relacionados:

- 🧾 **AWS CloudTrail:** registra chamadas de API e atividades da conta.
- 📊 **Amazon CloudWatch:** coleta e monitora logs, métricas e eventos.
- 📦 **Amazon S3:** pode armazenar registros e evidências de longo prazo.

⚠️ Atenção: logs podem conter informações pessoais, prompts e dados confidenciais. Devem ter controles de acesso, criptografia e políticas de retenção.

<h3><strong style='color: skyblue'>🌎 Residência de dados (Data Residency)</strong></h3>

<p align="justify">Residência de dados determina em quais países ou regiões os dados são armazenados e, conforme os requisitos aplicáveis, processados. É especialmente importante para organizações sujeitas a leis de proteção de dados, soberania digital e regulamentações setoriais.</p>

Exemplo:

Uma empresa brasileira precisa armazenar determinados dados de clientes no Brasil, conforme suas políticas e obrigações aplicáveis.

Ela deve avaliar:

- 🌎 Região AWS utilizada.
- 📦 Localização dos dados armazenados.
- 🔄 Replicação entre regiões.
- 🌐 Transferências internacionais.
- 📜 Requisitos legais e contratuais.
- 🔐 Controles de acesso e proteção.

<h3><strong style='color: skyblue'>📦 Exemplo com Amazon S3</strong></h3>

Uma organização armazena documentos de clientes em um bucket S3 na região São Paulo.

Para manter o controle de residência, deve avaliar:

- 📍 Região de armazenamento.
- 🔄 Replicação para outras regiões.
- 📋 Políticas de acesso e movimentação.
- 🧾 Registros de operações de leitura e escrita.
- ⚖️ Requisitos legais de transferência internacional.

> **DECORA:** Data Residency = onde os dados estão armazenados ou são processados, conforme os requisitos aplicáveis. Não confundir com retenção, que determina por quanto tempo os dados são mantidos.

<h3><strong style='color: skyblue'>📊 Monitoramento (Monitoring)</strong></h3>

<p align="justify">Monitoramento consiste em acompanhar continuamente o funcionamento, a segurança e a conformidade dos sistemas, identificando problemas e desvios em relação aos requisitos estabelecidos.</p>

Exemplos:

- 🚨 Identificar acessos suspeitos.
- 🔎 Detectar alterações não autorizadas.
- 📉 Acompanhar falhas e indisponibilidade.
- ⚖️ Identificar recursos fora das políticas.
- 🔐 Monitorar controles de segurança.
- 🧠 Acompanhar métricas das aplicações de IA.

Serviços relacionados:

- 📊 Amazon CloudWatch.
- 🧾 AWS CloudTrail.
- ⚙️ AWS Config.
- 🚨 Amazon GuardDuty.
- 🛡️ AWS Security Hub.

<h3><strong style='color: skyblue'>👁️ Observabilidade (Observability)</strong></h3>

<p align="justify">Observabilidade é a capacidade de compreender o estado interno e o comportamento de um sistema a partir das informações que ele produz, como logs, métricas e rastreamentos.</p>

Três pilares importantes:

- 🧾 **Logs:** registros detalhados de eventos e operações.
- 📊 **Métricas:** indicadores quantitativos, como latência, erros e utilização.
- 🔗 **Traces (Rastreamentos):** acompanham o caminho de uma solicitação através de diferentes serviços e componentes.

<h3><strong style='color: skyblue'>📦 Exemplo em uma aplicação de IA</strong></h3>

Um chatbot utiliza uma API, um banco vetorial e um modelo de linguagem.

Se uma resposta demora muito, a observabilidade pode ajudar a identificar:

- 🌐 Tempo de resposta da API.
- 🔎 Tempo gasto na recuperação de documentos.
- 🧠 Tempo de inferência do modelo.
- 🚨 Erros em serviços intermediários.
- 📊 Gargalos no processamento.

<h3><strong style='color: skyblue'>⚖️ Monitoramento × Observabilidade</strong></h3>

| Conceito | Objetivo |
|---|---|
| 📊 Monitoramento | Acompanhar indicadores e detectar problemas conhecidos |
| 👁️ Observabilidade | Investigar e compreender o comportamento interno do sistema |
| 🧾 Logging | Registrar eventos |
| 📈 Métricas | Quantificar o comportamento |
| 🔗 Tracing | Acompanhar o percurso de uma solicitação |

<h3><strong style='color: skyblue'>🗑️ Retenção de dados (Data Retention)</strong></h3>

<p align="justify">Retenção determina por quanto tempo os dados e registros devem ser mantidos antes de serem excluídos ou arquivados. O período precisa considerar requisitos legais, regulatórios, contratuais e necessidades operacionais.</p>

Práticas:

- 📅 Definir prazos de retenção.
- ⚖️ Observar obrigações legais.
- 🔐 Proteger dados durante o período de armazenamento.
- 📦 Arquivar informações que precisam ser preservadas.
- 🗑️ Excluir dados quando o prazo terminar e não houver obrigação de mantê-los.
- 📋 Documentar as políticas de retenção.

<h3><strong style='color: skyblue'>☁️ Recursos AWS para retenção</strong></h3>

- 📦 **Amazon S3 Lifecycle:** automatiza transições de armazenamento e exclusões conforme regras configuradas.
- 🧊 **Amazon S3 Glacier:** oferece classes de armazenamento para arquivamento de longo prazo.
- 🧾 **AWS CloudTrail:** registra atividades que podem ser armazenadas conforme políticas de retenção.
- 📊 **Amazon CloudWatch Logs:** permite configurar períodos de retenção para grupos de logs.

> **DECORA:** Ciclo de vida = etapas dos dados. Logging = registro de eventos. Residência = localização. Monitoramento = acompanhamento. Observabilidade = investigação do comportamento. Retenção = tempo de armazenamento.

---

### 4️⃣ 📋 Processos para seguir protocolos de governança

<h3><strong style='color: skyblue'>📜 Políticas de governança (Governance Policies)</strong></h3>

<p align="justify">Políticas de governança estabelecem regras, responsabilidades, critérios e procedimentos para garantir que dados e sistemas de IA sejam utilizados de maneira segura, ética e conforme os requisitos da organização.</p>

Exemplos:

- 🔐 **Política de acesso:** define quem pode acessar dados e modelos.
- 📂 **Política de dados:** estabelece regras de coleta, classificação, utilização e compartilhamento.
- 🧠 **Política de IA:** determina quais aplicações podem ser utilizadas e em quais situações.
- ⚖️ **Política de conformidade:** estabelece como atender às leis e regulamentações.
- 🧾 **Política de auditoria:** define os registros e evidências necessários.
- 👥 **Política de responsabilidade:** define os responsáveis por decisões e controles.

<h3><strong style='color: skyblue'>🧭 Exemplo de política corporativa</strong></h3>

Uma empresa determina que funcionários não podem inserir dados confidenciais de clientes em ferramentas públicas de IA generativa sem autorização.

A política deve definir:

- 🚫 Quais dados não podem ser compartilhados.
- 👥 Quem pode autorizar exceções.
- 🔐 Quais ferramentas são aprovadas.
- 📋 Como registrar o uso de IA.
- ⚖️ Quais consequências existem para violações.
- 🎓 Qual treinamento os funcionários precisam realizar.

<h3><strong style='color: skyblue'>📅 Cadência de revisão (Review Cadence)</strong></h3>

<p align="justify">Cadência de revisão é a frequência definida para revisar políticas, controles, riscos, permissões, modelos e procedimentos de governança.</p>

Exemplos:

- 📅 **Mensal:** revisar indicadores, alertas e problemas recorrentes.
- 📅 **Trimestral:** revisar permissões, políticas e riscos relevantes.
- 📅 **Semestral:** revisar controles, documentação e treinamentos.
- 📅 **Anual:** realizar avaliação abrangente do programa de governança.

⚠️ Esses períodos são exemplos de planejamento. A frequência real deve ser definida conforme o risco, a regulamentação e as necessidades da organização.

<h3><strong style='color: skyblue'>🚨 Revisões extraordinárias</strong></h3>

Além da periodicidade estabelecida, uma revisão pode ser necessária quando ocorrer:

- 🔓 Incidente de segurança.
- ⚖️ Mudança regulatória.
- 🧠 Alteração significativa do modelo.
- 📂 Mudança nas fontes de dados.
- 🔄 Alteração na finalidade da aplicação.
- 🚨 Identificação de viés ou comportamento prejudicial.
- 🏢 Mudança nos processos da organização.

<h3><strong style='color: skyblue'>🔎 Estratégias de revisão (Review Strategies)</strong></h3>

<p align="justify">Estratégias de revisão determinam como a organização verifica se os controles e procedimentos estão sendo cumpridos.</p>

Principais abordagens:

- 🤖 **Revisão automatizada:** ferramentas verificam configurações e requisitos continuamente.
- 👤 **Revisão humana:** especialistas avaliam políticas, decisões e resultados.
- 📋 **Auditoria interna:** equipes da organização verificam os controles.
- 🏢 **Auditoria externa:** avaliadores independentes verificam evidências e processos.
- 📊 **Avaliação de riscos:** identifica ameaças e prioriza controles.
- 🔄 **Melhoria contínua:** corrige problemas e atualiza procedimentos.

<h3><strong style='color: skyblue'>🛡️ Frameworks de governança</strong></h3>

<p align="justify">Frameworks de governança fornecem estruturas organizadas de princípios, controles, processos e responsabilidades para orientar a gestão de riscos e a conformidade.</p>

Exemplos:

- 🌐 ISO/IEC 42001: sistema de gestão de inteligência artificial.
- 🔐 ISO/IEC 27001: sistema de gestão de segurança da informação.
- 📋 SOC 2: critérios de controles de serviços de confiança.
- 🏛️ NIST AI Risk Management Framework: estrutura para gerenciar riscos de sistemas de IA.
- 🛡️ AWS Generative AI Security Scoping Matrix: estrutura para classificar casos de uso de IA generativa e orientar controles de segurança.

<h3><strong style='color: skyblue'>🧩 AWS Generative AI Security Scoping Matrix</strong></h3>

<p align="justify">A Matriz de escopos de segurança da IA generativa é um framework da AWS que ajuda as organizações a classificar soluções de IA generativa conforme o nível de controle que possuem sobre a aplicação, o modelo e os dados associados.</p>

A matriz apresenta cinco escopos:

<h3><strong style='color: skyblue'>🌐 Escopo 1 — Aplicação para consumidores</strong></h3>

<p align="justify">A organização utiliza uma aplicação pública de IA generativa fornecida por terceiros, geralmente sem controlar o modelo ou seus dados de treinamento.</p>

Exemplo:

Um funcionário utiliza um chatbot público para gerar ideias de marketing.

Principais preocupações:

- 🔐 Evitar inserir informações confidenciais.
- 📜 Verificar os termos de serviço.
- ⚖️ Avaliar os riscos de privacidade.
- 📋 Definir regras internas de utilização.

<h3><strong style='color: skyblue'>🏢 Escopo 2 — Aplicação empresarial</strong></h3>

<p align="justify">A organização utiliza uma aplicação empresarial de terceiros que possui recursos de IA generativa integrados e uma relação comercial com o fornecedor.</p>

Exemplo:

Uma empresa utiliza uma plataforma corporativa de produtividade que possui um assistente de IA integrado.

Principais preocupações:

- 📜 Avaliar contratos e licenças.
- 🔐 Verificar proteções de dados empresariais.
- 📋 Avaliar políticas de retenção.
- 👥 Controlar acessos dos funcionários.

<h3><strong style='color: skyblue'>🧠 Escopo 3 — Modelos pré-treinados</strong></h3>

<p align="justify">A organização desenvolve sua própria aplicação utilizando um modelo de base fornecido por terceiros, acessado geralmente por API.</p>

Exemplo:

Uma empresa cria um chatbot próprio utilizando um modelo disponibilizado pelo Amazon Bedrock e adiciona seus documentos internos por meio de RAG.</p>

Principais preocupações:

- 🔐 Proteger dados enviados ao modelo.
- 🛡️ Proteger a aplicação e suas APIs.
- 📋 Controlar permissões.
- 🔎 Avaliar entradas e saídas.

<h3><strong style='color: skyblue'>⚙️ Escopo 4 — Modelos ajustados (Fine-tuned)</strong></h3>

<p align="justify">A organização utiliza um modelo de terceiros e realiza ajustes ou personalizações, como fine-tuning, para atender a requisitos específicos.</p>

Exemplo:

Uma empresa ajusta um modelo pré-treinado utilizando dados próprios para melhorar respostas em um domínio especializado.</p>

Principais preocupações:

- 📚 Proteger dados utilizados no ajuste.
- ⚖️ Avaliar riscos relacionados aos dados de treinamento.
- 🔐 Controlar acesso aos modelos personalizados.
- 🧪 Avaliar o comportamento após o ajuste.

<h3><strong style='color: skyblue'>🏗️ Escopo 5 — Modelo desenvolvido do zero</strong></h3>

<p align="justify">A organização desenvolve seu próprio modelo de IA, assumindo maior responsabilidade sobre os dados, arquitetura, treinamento, avaliação e implantação.</p>

Exemplo:

Uma empresa desenvolve e treina um modelo de base próprio utilizando infraestrutura e conjuntos de dados sob seu controle.</p>

Principais preocupações:

- 📂 Governança dos dados de treinamento.
- 🧠 Segurança do modelo e dos pesos.
- 🔐 Proteção da infraestrutura.
- ⚖️ Gestão de riscos e conformidade.
- 🧪 Avaliação e monitoramento contínuos.

<h3><strong style='color: skyblue'>📊 Comparação dos cinco escopos</strong></h3>

| Escopo | Solução | Controle da organização |
|---|---|---|
| 🌐 1 | Aplicação pública de IA | Muito limitado |
| 🏢 2 | Aplicação empresarial de terceiros | Limitado, com proteções contratuais |
| 🧠 3 | Aplicação própria com modelo pré-treinado | Maior controle sobre a aplicação |
| ⚙️ 4 | Aplicação com modelo ajustado | Controle adicional sobre personalização |
| 🏗️ 5 | Modelo desenvolvido do zero | Maior controle e responsabilidade |

<h3><strong style='color: skyblue'>🛡️ Cinco disciplinas de segurança da matriz</strong></h3>

A matriz considera cinco áreas que devem ser avaliadas:

- 📋 **Governança e conformidade:** políticas, procedimentos e requisitos regulatórios.
- ⚖️ **Jurídico e privacidade:** contratos, licenças, direitos e proteção de dados.
- 🚨 **Gerenciamento de riscos:** identificação e mitigação de ameaças.
- 🔐 **Controles:** implementação de medidas de segurança.
- 🏗️ **Resiliência:** disponibilidade, recuperação e continuidade do sistema.

> **DECORA:** Quanto maior o escopo, maior tende a ser o controle da organização sobre o modelo e os dados — e também sua responsabilidade pela proteção e governança.

<h3><strong style='color: skyblue'>📢 Padrões de transparência (Transparency Standards)</strong></h3>

<p align="justify">Padrões de transparência estabelecem quais informações devem ser comunicadas sobre sistemas de IA, seus objetivos, limitações, dados, riscos e formas de utilização.</p>

Boas práticas:

- 🤖 Informar quando o usuário está interagindo com IA.
- 🎯 Explicar a finalidade do sistema.
- 📋 Documentar as capacidades e limitações.
- ⚠️ Comunicar riscos e incertezas.
- 🔗 Apresentar fontes quando aplicável.
- 👥 Informar quando existe revisão humana.
- 🧾 Manter documentação para auditorias.

Exemplo:

Um chatbot de atendimento deve informar que é um assistente automatizado, apresentar suas limitações e oferecer encaminhamento para atendimento humano quando necessário.

<h3><strong style='color: skyblue'>🎓 Requisitos de treinamento da equipe</strong></h3>

<p align="justify">As pessoas envolvidas no desenvolvimento, implantação, operação e utilização de sistemas de IA precisam receber treinamento adequado para compreender os riscos, as políticas e suas responsabilidades.</p>

Temas importantes:

- 🔐 **Segurança:** proteção de credenciais e dados confidenciais.
- 📜 **Conformidade:** leis, normas e políticas internas.
- 🧠 **Uso responsável:** limitações, vieses e alucinações.
- 🎭 **Privacidade:** tratamento adequado de dados pessoais.
- 🚨 **Incidentes:** identificação e comunicação de problemas.
- 🛡️ **Engenharia segura:** práticas para desenvolver e operar sistemas protegidos.
- 👥 **Supervisão humana:** quando revisar ou interromper decisões automatizadas.

<h3><strong style='color: skyblue'>🔄 Processo completo de governança</strong></h3>

<pre>
Definir políticas e responsabilidades
              |
              v
Identificar leis e padrões aplicáveis
              |
              v
Classificar riscos e escopo da IA
              |
              v
Definir controles e procedimentos
              |
              v
Treinar as equipes
              |
              v
Implementar monitoramento e auditoria
              |
              v
Revisar evidências e conformidade
              |
              v
Corrigir problemas identificados
              |
              v
Melhoria contínua
              |
              +------> Nova revisão
</pre>

> **DECORA:** Governança não é uma configuração única. É um processo contínuo de políticas, controles, treinamento, auditoria, revisão e melhoria.

---

## 🧠 DECORAÇÃO FINAL

| Serviço / Conceito | Associação para a prova |
|---|---|
| ⚙️ AWS Config | Configurações e regras de conformidade |
| 🔎 Amazon Inspector | Identificação de vulnerabilidades |
| 📄 AWS Artifact | Relatórios e documentos de conformidade da AWS |
| 📋 AWS Audit Manager | Coleta e organização de evidências de auditoria |
| 🧾 AWS CloudTrail | Registro de chamadas de API e atividades |
| ⭐ AWS Trusted Advisor | Recomendações de boas práticas |
| 🌐 ISO 27001 | Gestão de segurança da informação |
| 🧠 ISO 42001 | Gestão de sistemas de IA |
| 📋 SOC 1 | Controles relacionados a relatórios financeiros |
| 🛡️ SOC 2 | Critérios de confiança |
| 📊 SOC 3 | Relatório de uso geral sobre controles de confiança |
| 🇧🇷 LGPD | Proteção de dados pessoais no Brasil |
| 🇪🇺 GDPR | Proteção de dados pessoais na União Europeia |
| 🔄 Data Lifecycle | Etapas da vida dos dados |
| 🧾 Logging | Registro de eventos |
| 🌎 Data Residency | Localização dos dados |
| 📊 Monitoring | Acompanhamento contínuo |
| 👁️ Observability | Compreensão do comportamento interno |
| 🗑️ Data Retention | Tempo de armazenamento |
| 📜 Governance Policies | Regras e responsabilidades |
| 📅 Review Cadence | Frequência de revisão |
| 🔎 Review Strategies | Formas de verificar controles |
| 🛡️ Security Scoping Matrix | Classificação dos casos de uso de IA generativa |
| 📢 Transparency Standards | Comunicação de finalidade, limitações e riscos |
| 🎓 Team Training | Capacitação das equipes |

## ⚠️ PEGADINHAS DE PROVA

1. **AWS Config × CloudTrail:** Config verifica como os recursos estão configurados; CloudTrail registra as atividades e chamadas de API.
2. **Inspector × Config:** Inspector identifica vulnerabilidades; Config avalia configurações e regras de conformidade.
3. **Artifact × Audit Manager:** Artifact fornece documentos de conformidade da AWS; Audit Manager coleta e organiza evidências de auditoria da organização.
4. **CloudTrail × CloudWatch:** CloudTrail registra atividades e chamadas de API; CloudWatch monitora métricas, logs e eventos.
5. **Trusted Advisor × Inspector:** Trusted Advisor recomenda melhorias de boas práticas; Inspector identifica vulnerabilidades.
6. **ISO × SOC:** ISO publica padrões; SOC corresponde a relatórios de auditoria sobre controles de organizações prestadoras de serviços.
7. **SOC 1 × SOC 2:** SOC 1 está relacionado a controles relevantes para relatórios financeiros; SOC 2 trata dos critérios de confiança.
8. **Residência × Retenção:** residência é onde os dados ficam; retenção é por quanto tempo permanecem armazenados.
9. **Logging × Monitoring:** logging registra eventos; monitoring acompanha indicadores e identifica problemas.
10. **Monitoring × Observability:** monitoramento acompanha o estado do sistema; observabilidade ajuda a investigar seu comportamento interno.
11. **Audit Manager não é o auditor:** ele auxilia na organização de avaliações e evidências, mas não substitui o auditor independente.
12. **AWS Artifact não certifica a aplicação do cliente:** disponibiliza documentos sobre a conformidade da AWS e seus serviços.
13. **Governança é contínua:** não basta criar políticas; é necessário revisar, treinar, monitorar e corrigir.
14. **Escopo 1 não é o mais controlado:** é o uso de aplicações públicas de terceiros; o Escopo 5 envolve desenvolvimento do próprio modelo.
15. **Maior controle implica maior responsabilidade:** nos escopos mais avançados, a organização assume mais responsabilidades sobre modelo, dados e infraestrutura.

## 🗺️ MAPA MENTAL

<pre>
          GOVERNANÇA E CONFORMIDADE DE IA
                         |
       +-----------------+------------------+
       |                 |                  |
    SERVIÇOS          PADRÕES            DADOS
       |                 |                  |
       |                 |                  |
    AWS Config          ISO               Ciclo de vida
    Inspector           SOC               Logging
    Artifact            LGPD              Residência
    Audit Manager       GDPR              Monitoramento
    CloudTrail          ISO 42001         Observabilidade
    Trusted Advisor     ISO 27001         Retenção
       |                 |
       +-----------------+------------------+
                         |
                    PROTOCOLOS
                         |
       +-----------------+------------------+
       |                 |                  |
    Políticas          Revisões          Frameworks
       |                 |                  |
    Responsáveis      Cadência           Scoping Matrix
    Regras             Auditorias         Transparência
    Controles          Avaliações         Treinamento
       |                 |                  |
       +-----------------+------------------+
                         |
                         v
                 MELHORIA CONTÍNUA
</pre>
