# Assistente-Inteligente-para-An-lise-de-Avalia-es-de-Clientes-de-E-commerce-com-LLMs-e-Pipeline-RAG


Projeto final da disciplina Sistemas Cognitivos com Large Language Models.

Este projeto implementa uma aplicação cognitiva baseada em Large Language Models (LLMs) capaz de analisar avaliações de clientes de e-commerce, identificar padrões de reclamações e gerar respostas fundamentadas utilizando Prompt Engineering, Embeddings Semânticos e Pipeline RAG (Retrieval-Augmented Generation).

Objetivo

Construir um sistema inteligente capaz de:

Receber perguntas em linguagem natural;
Buscar avaliações relevantes de clientes;
Recuperar contexto semanticamente similar;
Utilizar um LLM para gerar respostas fundamentadas;
Auxiliar na análise de feedbacks de clientes para suporte à decisão.

Exemplo de pergunta ao sistema:

Quais são as principais reclamações dos clientes?

Exemplo de resposta:

Atrasos na entrega
Produtos danificados
Problemas no atendimento ao cliente
Falta de atualização sobre pedidos
Dataset Utilizado

Foi utilizado o dataset público:

Olist Brazilian E-Commerce Public Dataset
Kaggle - Olist Dataset

Arquivo principal utilizado:

olist_order_reviews_dataset.csv

Coluna analisada:

review_comment_message

Essa coluna contém comentários reais escritos por clientes após compras em um marketplace brasileiro.

Tecnologias Utilizadas
Python 3.11
Pandas
Ollama
Sentence Transformers
ChromaDB
Jupyter Notebook / VS Code
Modelo de Linguagem Utilizado

LLM principal:

Llama 3.2

O modelo roda localmente usando Ollama.

Vantagens da inferência local:

maior privacidade
sem custo por token
sem dependência de API externa
maior controle do pipeline
Arquitetura do Sistema

Fluxo completo da aplicação:

Pergunta do usuário
       ↓
Embedding da consulta
       ↓
Busca vetorial no ChromaDB
       ↓
Recuperação de documentos relevantes
       ↓
Construção de contexto
       ↓
Prompt aumentado (RAG)
       ↓
LLM gera resposta final
Estrutura do Projeto
.
├── projeto_llm_rag.ipynb
├── olist_order_reviews_dataset.csv
├── requirements.txt
├── README.md
└── relatorio_tecnico.pdf
Etapas Implementadas
1. Aplicação NLP com LLMs

Uso do modelo Llama 3.2 para:

classificação de reclamações
sumarização
question answering
análise textual
2. Prompt Engineering

Foram utilizadas múltiplas estratégias:

Zero-shot Prompting

O modelo recebe apenas instruções.

Few-shot Prompting

Exemplos são fornecidos antes da tarefa.

Structured Prompting

Uso de:

papel
contexto
formato de saída
3. Embeddings Semânticos

Modelo utilizado:

sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2

Função:

Converter textos em vetores semânticos.

Isso permite busca por significado e não apenas por palavras exatas.

4. Banco Vetorial

Foi utilizado:

ChromaDB

Funções:

armazenar embeddings
indexar documentos
realizar busca por similaridade
5. Pipeline RAG

Pipeline implementado com:

carregamento dos documentos
chunking
embeddings
indexação vetorial
recuperação top-k
geração de resposta com contexto
Instalação

Clone o repositório:

git clone <seu-repositorio>
cd <seu-repositorio>

Instale as dependências:

pip install -r requirements.txt
Instalação do Ollama

Baixe o Ollama:

Download Ollama

Baixe o modelo:

ollama pull llama3.2

Teste:

ollama run llama3.2
Como Executar
Inicie o Ollama:
ollama run llama3.2
Abra o notebook:
projeto_llm_rag.ipynb
Execute as células em ordem.
Resultados Obtidos

O sistema conseguiu identificar padrões relevantes nas avaliações, incluindo:

reclamações sobre atraso na entrega
produtos danificados
falhas no atendimento
problemas de logística

Observações:

RAG reduziu alucinações do modelo
respostas ficaram mais fundamentadas
contexto melhorou significativamente a qualidade das respostas
Limitações

O projeto possui algumas limitações:

amostra reduzida de documentos
modelo local pequeno
sem interface gráfica
sem fine-tuning
Melhorias Futuras

Possíveis evoluções:

interface web com Streamlit
aumento do corpus
busca híbrida (BM25 + vetorial)
reranking
guardrails de segurança
dashboard analítico
Aprendizados

Este projeto consolidou conhecimentos em:

Large Language Models
Prompt Engineering
Embeddings
Busca Vetorial
RAG
Inferência Local

Também permitiu entender desafios reais de aplicações cognitivas, incluindo:

custo computacional
gerenciamento de contexto
alucinações
segurança de prompts
Autora

Fernanda
Projeto acadêmico — Disciplina de Sistemas Cognitivos com LLMs
