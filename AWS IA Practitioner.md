# 🎓 Guia de Estudos: AWS Certified AI Practitioner (AIF-C01)

Este repositório contém um compilado estruturado de conceitos, serviços e estratégias para a certificação fundacional de IA da AWS.

**Última atualização:** 03/04/2026

-----

## 📑 Sumário

1.  [Materiais de Apoio](https://www.google.com/search?q=%231-materiais-de-apoio)
2.  [Visão Geral do Exame](https://www.google.com/search?q=%232-vis%C3%A3o-geral-do-exame)
3.  [Fundamentos de AI e ML](https://www.google.com/search?q=%233-fundamentos-de-ai-e-ml)
4.  [Generative AI e Foundation Models](https://www.google.com/search?q=%234-generative-ai-e-foundation-models)
5.  [Amazon Bedrock e Aplicações](https://www.google.com/search?q=%235-amazon-bedrock-e-aplica%C3%A7%C3%B5es)
6.  [Técnicas de Prompt Engineering](https://www.google.com/search?q=%236-t%C3%A9cnicas-de-prompt-engineering)
7.  [RAG e Bases de Conhecimento](https://www.google.com/search?q=%237-rag-e-bases-de-conhecimento)
8.  [Amazon SageMaker e MLOps](https://www.google.com/search?q=%238-amazon-sagemaker-e-mlops)
9.  [Amazon Q e Serviços Gerenciados](https://www.google.com/search?q=%239-amazon-q-e-servi%C3%A7os-gerenciados)
10. [Segurança e Responsible AI](https://www.google.com/search?q=%2310-seguran%C3%A7a-e-responsible-ai)
11. [Glossário de Termos Técnicos](https://www.google.com/search?q=%2311-gloss%C3%A1rio-de-termos-t%C3%A9cnicos)

-----

## 1\. Materiais de Apoio

  * 📚 [Guia Harikiran Vusirikala](https://harikiranvusirikala.github.io/aws-certified-ai-practitioner/) - Excelente resumo técnico.
  * 🎓 [Udemy - AWS AI Practitioner](https://www.google.com/search?q=https://www.udemy.com/course/aws-ai-practitioner-certified/) - Curso preparatório focado em simulados.
  * 📝 [Exam Guide Oficial](https://docs.aws.amazon.com/aws-certification/latest/ai-practitioner-01/ai-practitioner-01.html) - Leia para entender o escopo.
  * 🛠️ [AWS Skillbuilder](https://skillbuilder.aws/learning-plan/3NRN71QZR2/exam-prep-plan-aws-certified-ai-practitioner-aifc01--portugus/FD3EQCAJ5Y) - Plano de estudos oficial e gratuito.

-----

## 2\. Visão Geral do Exame

A certificação foca em **entender, escolher e explicar** soluções de IA. Não é necessário saber programar modelos complexos, mas sim saber qual ferramenta resolve qual problema de negócio.

| Domínio | Peso | Foco Principal |
| :--- | :--- | :--- |
| **Fundamentos de AI/ML** | 20% | Conceitos básicos e ciclo de vida. |
| **Generative AI** | 24% | LLMs, custos e limitações. |
| **Aplicações de FMs** | 28% | Bedrock, RAG, Agentes e Embeddings. |
| **Responsible AI** | 14% | Viés, ética e explicabilidade. |
| **Segurança/Compliance** | 14% | IAM, Guardrails e Governança. |

-----

## 3\. Fundamentos de AI e ML


### Diferenciação de Conceitos

  * **Inteligência Artificial (AI):** Sistemas que mimetizam inteligência humana.
  * **Machine Learning (ML):** Aprendizado através de padrões em dados (subconjunto de AI).
  * **Deep Learning:** Uso de redes neurais profundas (Transformers, RNNs, CNNs).

### Paradigmas de Aprendizado

  * **Supervisionado:** Dados rotulados (Ex: Prever preço de casas - Regressão).
  * **Não Supervisionado:** Dados sem rótulos (Ex: Agrupar clientes - Clustering).
  * **Por Reforço:** Aprendizado por tentativa e erro (Recompensas).

-----

## 4\. Generative AI e Foundation Models


A **GenAI** cria conteúdo novo (texto, imagem, código). Ela é baseada em **Foundation Models (FMs)**: modelos de larga escala pré-treinados.

### Principais FMs no Bedrock

| Provedor | Modelo | Uso Principal |
| :--- | :--- | :--- |
| **Anthropic** | Claude 3 | Raciocínio avançado, resumos e análise de documentos. |
| **Meta** | Llama 3 | Versátil, bom para aplicações customizadas. |
| **Mistral AI** | Mistral/Mixtral | Eficiência e geração de código. |
| **Amazon** | Titan / **Nova** | Multimodalidade (texto, imagem, vídeo) e custo-benefício. |
| **Stability AI**| Stable Diffusion | Geração de imagens. |

-----

## 5\. Amazon Bedrock e Aplicações

O Bedrock é um serviço **Serverless**. Você acessa modelos via API sem gerenciar servidores.

### Customização e Avaliação

  * **Fine-tuning:** Ajustar o modelo com seus próprios dados para tarefas específicas.
  * **Model Evaluation:** Avaliação automática ou humana da qualidade das respostas.
      * **ROUGE:** Focado em Recall (resumos).
      * **BLEU:** Focado em Precisão (tradução).
      * **Perplexity:** Mede a incerteza do modelo (baixa é melhor).

-----

## 6\. Técnicas de Prompt Engineering

  * **Zero-shot:** Instrução direta sem exemplos.
  * **Few-shot:** Fornece alguns exemplos no prompt para guiar o formato.
  * **Chain-of-thought:** "Pense passo a passo" (melhora o raciocínio lógico).

### Parâmetros de Inferência

  * **Temperature:** Controla a criatividade (0.1 = factual; 0.8 = criativo).
  * **Top-P / Top-K:** Filtram as palavras mais prováveis para evitar respostas sem nexo.
  * **Max Tokens:** Limita o tamanho da resposta (controla custo e latência).

-----

## 7\. RAG e Bases de Conhecimento

**RAG (Retrieval-Augmented Generation)** conecta o LLM aos seus dados privados sem precisar retreinar o modelo.

  * **Knowledge Base:** Repositório que armazena seus documentos.
  * **Vector Database:** Onde os documentos viram **Embeddings** (vetores numéricos).
      * *Opções AWS:* **OpenSearch Service**, **Aurora (pgvector)**, **Neptune (GraphRAG)** ou **S3 Vectors**.

-----

## 8\. Amazon SageMaker e MLOps

O SageMaker é para o cientista de dados que quer **controle total**.

  * **Fases:** Build (Studio), Train (Training Jobs), Deploy (Endpoints).
  * **Modos de Inferência:**
      * **Real-time:** Baixa latência, 24/7 (mais caro).
      * **Serverless:** Escala para zero (ideal para tráfego instável).
      * **Asynchronous:** Para tarefas longas (minutos).
      * **Batch Transform:** Processamento de grandes volumes offline.

-----

## 9\. Amazon Q e Serviços Gerenciados

### Família Amazon Q

  * **Q Business:** Responde sobre dados da empresa (respeita permissões/ACLs).
  * **Q Developer:** Ajuda a escrever e debugar código na IDE.

### Serviços de IA "Prontos" (Managed)

  * **Rekognition:** Visão computacional (objetos/faces).
  * **Polly:** Texto para Fala.
  * **Transcribe:** Fala para Texto.
  * **Lex:** Criação de Chatbots (Intents/Slots).
  * **Textract:** Extração de dados de documentos (OCR inteligente).

-----

## 10\. Segurança e Responsible AI

  * **Guardrails for Bedrock:** Filtra conteúdo tóxico, PII (dados pessoais) e temas proibidos.
  * **CloudWatch:** Monitora latência, uso de tokens e erros.
  * **Clarify:** Detecta viés e explica decisões do modelo.
  * **Scoping Matrix:** Define o nível de responsabilidade (Scope 1 - App de Consumidor até Scope 5 - Modelo Treinado do zero).

-----

## 11\. Glossário de Termos Técnicos

  * **BERT:** Bidirecional. Focado em **entendimento** (Classificação/Sentiment Analysis).
  * **GPT:** Unidirecional. Focado em **geração** de texto.
  * **RNN:** Lida com sequências, mas tem memória curta.
  * **Hallucination:** Quando o modelo inventa fatos com confiança.
  * **Token:** Unidade básica de processamento (palavra ou pedaço dela).
  * **TTFT (Time to First Token):** Medida crucial de latência (tempo até a primeira letra aparecer).

-----

> **Dica para a prova:** Se a questão pedir agilidade e pouco código, a resposta costuma ser **Bedrock** ou **Amazon Q**. Se pedir controle total de infraestrutura e treinamento próprio, a resposta é **SageMaker**.
