# 🎓 Guia de Estudos: AWS Certified AI Practitioner (AIF-C01)

Este repositório contém um compilado estruturado de conceitos, serviços e estratégias para a certificação fundacional de IA da AWS.

**Última atualização:** 09/04/2026

-----

## 📑 Sumário

1. [Visão Geral do Exame e Materiais Extras](#1-visão-geral-do-exame-e-materiais-de-apoio)
2. [Fundamentos de AI, ML e GenAI](#2-fundamentos-de-ai-ml-e-genai)
3. [Amazon Bedrock e Foundation Models](#3-amazon-bedrock-e-foundation-models)
4. [Amazon SageMaker e MLOps](#4-amazon-sagemaker-e-mlops)
5. [Amazon Q e Serviços Gerenciados](#5-amazon-q-e-serviços-gerenciados)
6. [Agentes (Amazon Bedrock)](#6-agentes-amazon-bedrock)
7. [Prompt Engineering](#7-prompt-engineering)
8. [Segurança e Responsible AI](#8-segurança-e-responsible-ai)
9. [Modelos de Precificação](#9-modelos-de-precificação)

<br>

-----

<br>

## 1. Visão Geral do Exame e Materiais de Apoio

<br>

A certificação foca em entender, escolher e explicar soluções de IA. Não é necessário saber programar modelos complexos, mas sim saber qual ferramenta resolve qual problema de negócio.

<br>

| Domínio | Peso | Foco Principal |
| :--- | :--- | :--- |
| **Fundamentos de AI/ML** | 20% | Conceitos básicos e ciclo de vida. |
| **Generative AI** | 24% | LLMs, custos e limitações. |
| **Aplicações de FMs** | 28% | Bedrock, RAG, Agentes e Embeddings. |
| **Responsible AI** | 14% | Viés, ética e explicabilidade. |
| **Segurança/Compliance** | 14% | IAM, Guardrails e Governança. |

<br>

### Materiais Extras

* 📝 [Exam Guide Oficial](https://docs.aws.amazon.com/aws-certification/latest/ai-practitioner-01/ai-practitioner-01.html) - Guia oficial do exame.
* 🛠️ [AWS Skillbuilder](https://skillbuilder.aws/learning-plan/3NRN71QZR2/exam-prep-plan-aws-certified-ai-practitioner-aifc01--portugus/FD3EQCAJ5Y) - Plano de estudos oficial e gratuito.
* 📚 [Guia Harikiran Vusirikala](https://harikiranvusirikala.github.io/aws-certified-ai-practitioner/) - Resumo técnico.
* 🎓 [Udemy - AWS AI Practitioner](https://www.udemy.com/course/aws-ai-practitioner-certified/) - Curso preparatório com simulado.

<br>

---

<br>

## 2. Fundamentos de AI, ML e GenAI

<br>

### Diferenciação de Conceitos

**Inteligência Artificial (AI):** É o conceito mais amplo. Refere-se a qualquer sistema capaz de realizar tarefas que normalmente exigiriam inteligência humana (raciocínio, visão, tomada de decisão). Uma IA pode funcionar apenas baseada em regras lógicas rígidas criadas por humanos (If/Else).

Exemplo: Um sistema de regras de negócio que bloqueia uma transação no cartão de crédito simplesmente porque o valor ultrapassou o limite diário estabelecido no código.

**Machine Learning (ML):** É um subconjunto da IA. Em vez de ser explicitamente programado com regras lógicas, o sistema recebe algoritmos e um grande volume de dados. Ele aprende sozinho a identificar padrões estatísticos para fazer predições.
  
Exemplo: Um modelo analítico que estuda anos de histórico financeiro de clientes para prever o *credit score* de novos usuários ou identificar o risco de *churn* (cancelamento de conta).

**Deep Learning (DL):** É um subconjunto muito avançado do ML. Utiliza arquiteturas complexas chamadas de Redes Neurais Artificiais (com múltiplas "camadas profundas" de processamento, inspiradas no cérebro humano). É a melhor abordagem para lidar com dados não estruturados (imagens, áudios e textos longos).

Exemplo: O sistema de visão computacional que valida a *selfie* e a foto da identidade de um cliente, ou os modelos baseados na arquitetura Transformer que tornam a IA Generativa e o Amazon Bedrock possíveis.

**Generative AI (GenAI):** É um subconjunto especializado do Deep Learning. Enquanto o ML/DL tradicionais são *analíticos* (classificam ou prevêem algo que já existe), a GenAI é *criativa*. Ela usa Foundation Models (FMs) treinados em bases de dados massivas para **gerar conteúdo inédito** (texto, imagem, áudio, código).

### Tipos de Aprendizado

* **Supervisionado:** Dados rotulados.
* **Não Supervisionado:** Dados sem rótulos.
* **Por Reforço:** Aprendizado por tentativa e erro (Recompensas).

<br>

---

<br>

## 3. Amazon Bedrock e Foundation Models

<br>

O **Amazon Bedrock** é o serviço da AWS que permite a criação de modelos de GenAI, fornecendo acesso gerenciado a diversos foundation models de forma centralizada por meio de uma API, sem necessidade de gerenciar infraestrutura.

* Serverless 
* Vários modelos em um só lugar
* Privacidade de dados
* Ferramentas low-code para não desenvolvedores 
* Ferramentas para customizar os modelos, se necessário

<br>

### Foundation Models (FMs)
São modelos de larga escala pré-treinados em grandes volumes de dados não rotulados (imagens, vídeos, documentos, etc) com o objetivo de aprender padrões gerais da linguagem e do mundo.

Esses modelos servem como base reutilizável sem a necessidade de criar um modelo do zero a cada demanda. Você pode usar o modelo "as is" ou adaptar de forma privada.

<br>

### Principais FMs no Bedrock:

| Provedor | Modelo | Uso Principal |
| :--- | :--- | :--- |
| **Anthropic** | Claude 3 | Raciocínio avançado, resumos e análise de documentos. |
| **Meta** | Llama 3 | Versátil, bom para aplicações customizadas. |
| **Mistral AI** | Mistral/Mixtral | Eficiência e geração de código. |
| **Amazon** | Titan / **Nova** | Multimodalidade (texto, imagem, vídeo) e custo-benefício. |
| **Stability AI**| Stable Diffusion | Geração de imagens. |

<br>

### Customização e Avaliação

**Fine-tuning:** Ajustar o modelo com seus próprios dados para tarefas específicas.

**Model Evaluation:** Permite avaliar automaticamente a qualidade das respostas sem intervenção humana. As métricas são: corretude, completude e similaridade.
**Automated Metrics:**
* **ROUGE (ROUGE-N ou ROUGE-L):** Focado em Recall (resumos). "O texto conseguiu cobrir os principais pontos esperados do texto?"
* **BLEU:** Focado em Precisão (tradução). "Quanto do que o modelo gerou está correto em relação ao texto esperado?"
* **BERT-SCORE**: Usa embeddings e avalia similaridade/sinônimos e não tokens/palavras exatas como no Rouge e Bleu.
* **Perplexity:** Mede o quanto o modelo fica "surpreso" ao ver o texto gerado (baixa é melhor, se o modelo não ficou surpreso com o resultado, é porque modelou bem).

**Judge Modelo**: Usa técnica LLM-as-a-Judge, onde um modelo avalia outro modelo, podendo dar nota para as métricas e gerar textos explicativos. Exemplos de modelos que podem ser usados como Judge: Amazon Nova, Anthropic Claude, Meta LLama e Mistral.

**Benchmark Datasets**: São conjuntos de dados padronizados usados como referência para avaliar, comparar e medir o desempenho de modelos de ML.
    * "Régua comum"/ dados de teste padronizados usados para comparar modelos;
    * Não substitui teste com dados de negócios;
    * Usados para discovery inicial e escolha do Foundation Model.

**Business Metrics:** * User satisfaction: O usuário vê utilidade e confia na resposta gerada;
    * Average Revenue: impacto financeiro;
    * Cross-domain performance: consistência em contextos diferentes;
    * Conversion rate: o modelo é capaz de influenciar ações desejadas.

<br>

### RAG e Bases de Conhecimento

**RAG (Retrieval-Augmented Generation)** é um padrão arquitetural que conecta o LLM aos seus dados privados sem precisar retreinar o modelo, recuperando documentos e trechos relevantes. Ele ajuda a reduzir alucinações e aumentar a factualidade.

**Knowledge Base:** Repositório estruturado que armazena os documentos que irão alimentar o RAG. Os documentos viram **Embeddings** (vetores numéricos), para que as informações sejam recuperadas por similaridade semântica.
* *Opções AWS:* **OpenSearch Service**, **Aurora (pgvector)**, **Neptune (GraphRAG)** ou **S3 Vectors**.

<br> 

---

<br>


## 4. Amazon SageMaker e MLOps

<br>

O Amazon SageMaker é um serviço gerenciado ponta a ponta (PaaS) projetado para cientistas de dados e desenvolvedores que precisam de **controle total** sobre a infraestrutura, os dados e o treinamento dos modelos de Machine Learning.

Enquanto o *Amazon Bedrock* é como alugar um carro pronto para dirigir (Serverless API), o *SageMaker* é a fábrica onde você constrói o carro, ajusta o motor e define como ele vai rodar.

### O Ciclo de Vida do ML (As Três Fases)

1. **Build (Construção e Preparação):**
    * **SageMaker Studio:** A IDE (Interface de Desenvolvimento) unificada baseada na web para todas as tarefas de ML.
    * **SageMaker Data Wrangler:** Ferramenta visual que reduz o tempo de agregação e preparação de dados (Data Prep) de semanas para minutos.
    * **SageMaker Feature Store:** Um repositório central para armazenar, atualizar e compartilhar *features* (variáveis) de ML entre diferentes equipes, evitando retrabalho.

2. **Train (Treinamento e Otimização):**
    * **Training Jobs:** A AWS provisiona os servidores (instâncias EC2), treina o modelo com seus dados e desliga os servidores automaticamente ao terminar, para você pagar apenas pelos minutos usados.
    * **Automatic Model Tuning (HPO):** Executa vários treinamentos simultâneos testando diferentes parâmetros (Hyperparameters) para encontrar a versão mais precisa do modelo.

3. **Deploy (Implantação e Inferência):**
    * **Real-time (Tempo Real):** Para aplicações que precisam de respostas imediatas (milissegundos). O servidor fica ligado 24/7. *Ex: Sistema de detecção de fraude na hora do pagamento.*
    * **Serverless (Sem Servidor):** A infraestrutura liga e desliga sozinha. Ideal para tráfego intermitente ou imprevisível. *Ex: Um chatbot que não recebe acessos de madrugada, mas tem picos ao meio-dia.*
    * **Asynchronous (Assíncrono):** Para requisições pesadas que demoram minutos para processar (limite de até 1 hora) e payloads grandes (até 1GB).

<br>

-----

<br>

## 5. Amazon Q e Serviços Gerenciados

<br>

### Família Amazon Q

Assistente de GenIA totalmente gerenciado da AWS (Bedrock+RAG):
* **Q Business:** Responde sobre dados da empresa (respeita permissões/ACLs).
* **Q Developer:** Ajuda a escrever e debugar código na IDE.
* **Q Apps:** Permite que funcionários criem aplicativos de IA generativa (no-code/sem código) baseados nos dados da empresa, usando apenas instruções em linguagem natural.

<br>

### Serviços de IA "Prontos" (Managed)

* **Rekognition:** Visão computacional (análise de imagens, vídeos, objetos e reconhecimento facial).
* **Polly:** Conversão de Texto para Fala (Text-to-Speech) com vozes realistas.
* **Transcribe:** Conversão de Fala para Texto (Speech-to-Text).
* **Lex:** Criação de Chatbots conversacionais (usa Intents, Utterances e Slots).
* **Textract:** Extração inteligente de dados e textos de documentos (OCR avançado).
* **Comprehend:** Processamento de Linguagem Natural (NLP) para descobrir sentimentos, entidades e idiomas em textos.
* **Translate:** Tradução automática e fluente de textos entre diversos idiomas.
* **Personalize:** Criação de sistemas de recomendação personalizados (mesma tecnologia da loja Amazon.com).
* **Kendra:** Motor de busca corporativa inteligente baseado em ML, para encontrar respostas exatas em documentos da empresa.
* **Mechanical Turk (MTurk):** Plataforma de crowdsourcing para tarefas que exigem inteligência humana (muito usado para rotular dados de treinamento).
* **Augmented AI (A2I):** Facilita a implementação de revisão humana (*Human-in-the-loop*) para validar predições de modelos de ML com baixa confiança.
* **Comprehend Medical:** NLP especializado para extrair entidades médicas (medicamentos, condições, dosagens) de textos não estruturados.
* **Transcribe Medical:** Fala para texto otimizado para reconhecer jargões e termos da área médica.
* **AWS HealthScribe:** IA generativa que transcreve e resume automaticamente consultas médicas, criando notas clínicas prontas para o prontuário.

<br>

### Experimentação e Prototipagem (No-Code)

* **PartyRock:** É um "playground" (ambiente de testes práticos) sem código (no-code) impulsionado pelo Amazon Bedrock. 
    * **Para que serve:** Permite que qualquer pessoa crie aplicativos simples de IA generativa em minutos apenas escrevendo prompts, testando diferentes modelos na prática.
    * **Vantagem no Exame:** Lembre-se de que ele **não exige** uma conta da AWS ou cartão de crédito para ser usado. É focado na educação, na democratização da GenAI e no aprendizado prático de Prompt Engineering - exploração e não produtização.

<br>

-----

<br>

## 6. Agentes (Amazon Bedrock)

<br>

Enquanto um modelo de linguagem tradicional (Chatbot) apenas "conversa" e gera texto, um **Agente dá "mãos" à IA**. Ele permite que o modelo planeje tarefas em várias etapas e **execute ações** em sistemas externos de forma autônoma utilizando o framework **ReAct** (*Reason and Act* - Raciocinar e Agir).

Para criar e operar um Agente no Amazon Bedrock, você utiliza os seguintes componentes e integrações:


* **Foundation Model (O Cérebro):** Você seleciona um modelo base (ex: Claude 3, Amazon Nova) que será o motor de raciocínio. Ele interpreta o pedido do usuário, quebra o problema em etapas e decide qual ferramenta usar.
* **Instructions (A Persona e Regras):** É o prompt de sistema onde você define o papel do agente e suas diretrizes de negócio. *Ex: "Você é um agente de suporte de TI. Você pode redefinir senhas, mas nunca deve aprovar a compra de novos equipamentos sem consultar a política de TI."*
* **Action Groups (As Mãos):** É o componente que permite ao agente interagir com o mundo exterior. Você fornece ao agente as definições de uma API (geralmente via OpenAPI schema) e, quando ele decide que precisa agir, ele aciona uma função do **AWS Lambda** para executar o código real (ex: consultar um banco de dados, enviar um e-mail ou processar um reembolso).
* **Knowledge Bases (A Memória de Apoio):** Você pode conectar o agente a Bases de Conhecimento (RAG). Assim, ele pode pesquisar as políticas internas da empresa, manuais ou históricos *antes* de executar uma ação no Lambda.

<br>

### Recursos Avançados e Operação

* **Multi-Agent Collaboration:** Permite criar uma arquitetura onde um Agente "Supervisor" roteia e delega tarefas para vários subagentes especializados. *Exemplo: Um Agente de Onboarding recebe um novo funcionário e coordena com um "Agente de TI" (para criar o e-mail) e um "Agente de RH" (para cadastrar benefícios), unindo as respostas no final.*
* **Integração com Amazon CloudWatch:** Para garantir transparência e facilitar o *debugging*, o Bedrock envia **Trace Logs** (logs de rastreamento) para o CloudWatch. Isso permite que os desenvolvedores vejam exatamente a cadeia de pensamento (Chain-of-Thought) do agente, verificando o que ele planejou, quais Action Groups ele chamou e quais respostas obteve das APIs.

<br>

> **Dica para a prova:** Se a questão falar de uma IA que precisa *"interagir com APIs de terceiros"*, *"completar transações"* ou *"tomar ações baseadas na intenção do usuário"*, a resposta correta será **Agents for Amazon Bedrock**.

<br>

----

<br> 

## 7. Prompt Engineering

<br>

Prompt Engineering (ou Engenharia de Prompt) é a técnica de projetar, testar e refinar as instruções textuais (os "prompts") que você envia para modelos de Inteligência Artificial Generativa para obter resultados mais precisos, relevantes e com a formatação desejada.

<br>

### Técnicas 
* **Zero-shot:** Instrução direta sem exemplos.
* **Few-shot:** Fornece alguns exemplos no prompt para guiar o formato.
* **Chain-of-thought:** "Pense passo a passo" (melhora o raciocínio lógico).

<br>

### Parâmetros de Inferência
* **Temperature:** Controla a criatividade (0.1 = factual; 0.8 = criativo).
* **Top-P / Top-K:** Filtram as palavras mais prováveis para evitar respostas sem nexo.
* **Max Tokens:** Limita o tamanho da resposta (controla custo e latência).
* **Length (Tamanho da Resposta):** Define a extensão limite da saída desejada. Em muitas APIs e no Bedrock, funciona em conjunto ou como sinônimo de *Max Tokens* para evitar que o modelo gere textos excessivamente longos.
* **Prompt Latency (Latência do Prompt):** Embora não seja um botão que você "configura", é uma métrica crucial afetada pelos parâmetros acima. É o tempo que o modelo leva para processar a sua entrada e começar a responder. Prompts gigantescos ou limites de tokens muito altos aumentam a latência.

<br>

### Prompt Template
É como uma "receita" ou um formulário padronizado com espaços em branco (variáveis) que você preenche dinamicamente antes de enviar a instrução para o modelo de Inteligência Artificial.

Em vez de escrever um texto novo do zero toda vez que for interagir com o LLM, você cria uma estrutura fixa de instruções e deixa apenas os dados específicos mudarem.

* **System Prompt / Persona:** Quem a IA deve ser (ex: "Você é um auditor financeiro").
* **Instruções / Regras:** O que ela pode ou não fazer (ex: "Seja conciso, não use jargões").
* **Few-Shot Examples (Opcional):** Exemplos inseridos fixamente no template para ensinar o formato esperado.
* **Variáveis / Input:** Os {espaços} onde os dados dinâmicos do usuário entram.

<br>

---

<br>

## 8. Segurança e Responsible AI

<br>

Garantir que os sistemas de IA sejam transparentes, confiáveis e seguros durante todo o ciclo de vida, mitigando riscos e alinhando-se a regulamentações e governança.

<br>

### Dimensões da IA Responsável
* **Justiça (Fairness) e Viés:** Evitar discriminação promovendo inclusão. Vieses podem vir dos dados de treino ou dos criadores.
* **Explicabilidade:** Entender *como* e *por que* o modelo decide. Existe um trade-off: Modelos muito precisos (Redes Neurais) são "caixas-pretas" com baixa interpretabilidade. Ferramentas como **PDP (Partial Dependence Plots)** ajudam a analisar essas decisões.
* **Privacidade e Governança:** Proteger dados sensíveis (PETs - Privacy-Enhancing Technologies, como mascaramento) e manter a **Linhagem de Dados (Data Lineage)** para auditoria e rastreabilidade.

<br>

### Desafios e Ameaças em GenAI
* **Alucinações:** O modelo gera afirmações incorretas de forma muito confiante.
* **Toxicidade:** Geração de conteúdo ofensivo ou inadequado.
* **Prompt Injection / Hijacking:** Usuário manipula o prompt para alterar o comportamento do modelo e contornar regras.
* **Data Poisoning (Envenenamento):** Inserção de dados maliciosos no treinamento do modelo.
* **Prompt Leaking (Exposição):** O modelo revela acidentalmente dados sensíveis de seu corpus de treinamento.
* **Jailbreaking:** Uso intencional de técnicas para burlar travas de segurança e éticas do modelo.

<br>

### Ferramentas AWS para Segurança e Compliance
* **Guardrails for Amazon Bedrock:** Implementa filtros de conteúdo tóxico, bloqueia tópicos indesejados e mascara dados pessoais (PII) antes de chegarem ao usuário.
* **Amazon SageMaker Clarify:** Avalia modelos quanto a métricas de justiça, explicabilidade, toxicidade e detecta vieses.
* **Amazon SageMaker Data Wrangler:** Corrige problemas de viés balanceando datasets.
* **Model Cards / AI Service Cards:** Documentação padronizada na AWS com uso pretendido, limitações e riscos de um modelo (essencial para auditoria).
* **Amazon A2I (Augmented AI):** Adiciona revisão humana (Human-in-the-loop) para predições de IA que precisam de validação.

<br>

### Responsabilidade Compartilhada e Monitoramento
* **Modelo de Responsabilidade Compartilhada:** A AWS cuida da segurança **DA** nuvem (infraestrutura e serviços base). O Cliente cuida da segurança **NA** nuvem (configuração de IAM, guardrails, criptografia dos próprios dados).
* **GenAI Security Scoping Matrix:** Classifica o nível de controle e risco da sua aplicação (Escopo 1: Usar app de terceiros -> Escopo 5: Treinar o próprio modelo do zero).
  
<br>

-----

<br>

## 9. Modelos de Precificação

A AWS cobra de forma diferente dependendo se você usa APIs gerenciadas, infraestrutura dedicada ou subscrições.

<br>

### Precificação em Generative AI (Amazon Bedrock)
No Bedrock, você não gerencia nem paga por servidores (EC2). O custo primário é atrelado ao uso dos Foundation Models.
* **On-Demand (Sob Demanda):** Baseado no volume de **Tokens**. Você paga separadamente por *Input Tokens* (o texto/prompt que você envia) e *Output Tokens* (o texto gerado pela IA). A geração (*Output*) costuma ser mais cara. Ideal para cargas de trabalho imprevisíveis.
* **Provisioned Throughput (Taxa de Transferência Provisionada):** Você reserva capacidade de processamento garantida na nuvem e paga um valor fixo por hora/mês. Ideal para produção com alto volume e onde a latência não pode oscilar. **Atenção:** É obrigatório comprar *Provisioned Throughput* para usar um modelo customizado (Fine-tuned).
* **Model Customization (Fine-Tuning):** O treinamento é cobrado com base no número de tokens contidos no seu conjunto de dados de treino.

<br>

### Custos de Recursos Adicionais do Bedrock 
Muitos recursos avançados do Bedrock não possuem uma "taxa de ativação", mas você paga pelos serviços subjacentes que eles consomem:
* **Knowledge Bases (RAG):** Não há cobrança pela "orquestração" da base de conhecimento em si. O seu custo será a soma de dois fatores: 
  1. O **Banco de Dados Vetorial** escolhido (ex: você paga pelas unidades de computação do *OpenSearch Serverless* ou armazenamento no *Aurora*).
  2. Os **Tokens de Embeddings** (quando você converte seus PDFs em vetores) e os tokens do LLM ao responder a pergunta.
* **Agents for Amazon Bedrock:** A orquestração do agente (o *Agent Core*) não possui uma tarifa avulsa da AWS. O custo de um agente é composto por:
  1. Os **Tokens do LLM** usados durante o raciocínio (o agente consome *muitos* tokens "pensando" nas etapas antes de responder ao usuário).
  2. O custo do **AWS Lambda** cada vez que ele aciona um *Action Group* para interagir com uma API externa.
* **Guardrails for Amazon Bedrock:** É cobrado separadamente com base no volume de texto que precisa ser avaliado pelas suas políticas de segurança (calculado a cada 1.000 registros de texto processados no input e no output).

<br>

### Precificação no Amazon SageMaker
No SageMaker, o custo está fortemente atrelado à **infraestrutura** (instâncias computacionais EC2).
* **Fase de Treinamento:** Cobrado pelo tipo de instância (CPU/GPU) e pelo tempo exato (em milissegundos) que a máquina ficou ligada executando o *Training Job*.
* **Fase de Inferência (Deploy):**
    * **Real-time:** Paga-se por hora que o endpoint fica ligado (24/7), independentemente de receber requisições ou não. 
    * **Serverless:** Paga-se pelo tempo de computação exato gasto durante a requisição e a quantidade de memória usada (escala para zero se não houver acessos).

<br>

### Serviços Prontos e Família Amazon Q
* **Serviços de IA Gerenciados (Rekognition, Textract, Lex, Translate, etc):** Modelo "Pay-as-you-go" baseado em chamadas de API. Você paga por imagem analisada, página extraída, minuto de áudio processado ou milhão de caracteres traduzidos.
* **Família Amazon Q:** Trabalha com um modelo de assinatura de licença mensal corporativa por usuário (*Per User / Per Month*), aplicável para o Q Business, Q Developer e Q Apps.

> **Dica para a prova:** Se o cenário da questão pedir para "minimizar custos em um sistema com acessos esporádicos e imprevisíveis", a resposta envolverá opções **Serverless** (no SageMaker) ou **On-Demand** (no Bedrock). Se o cenário exigir "latência garantida, sem surpresas na fatura e altíssimo volume de interações", a resposta apontará para **Provisioned Throughput**.
