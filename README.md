# 🤖 Assistente Inteligente para Análise de Avaliações de E-commerce com LLMs + RAG

![Python](https://img.shields.io/badge/Python-3.11-blue)
![LLM](https://img.shields.io/badge/LLM-Llama%203.2-green)
![RAG](https://img.shields.io/badge/Architecture-RAG-orange)
![Status](https://img.shields.io/badge/Status-Finalizado-success)

Projeto final da disciplina **Sistemas Cognitivos com Large Language Models**.

Este projeto implementa uma aplicação cognitiva baseada em **Large Language Models (LLMs)** capaz de analisar avaliações de clientes de e-commerce, identificar padrões de reclamações e gerar respostas fundamentadas utilizando:

- Prompt Engineering  
- Embeddings Semânticos  
- Busca Vetorial  
- Pipeline RAG (Retrieval-Augmented Generation)

---

# 📌 Objetivo

Construir um sistema inteligente capaz de:

✅ Receber perguntas em linguagem natural  
✅ Buscar avaliações relevantes de clientes  
✅ Recuperar contexto semanticamente similar  
✅ Utilizar um LLM para gerar respostas fundamentadas  
✅ Auxiliar análises de negócio baseadas em feedbacks reais  

### Exemplo de pergunta

```text
Quais são as principais reclamações dos clientes?
```

### Exemplo de resposta

- Atrasos na entrega  
- Produtos danificados  
- Problemas de atendimento  
- Falta de atualização sobre pedidos  

---

# 📂 Dataset Utilizado

Dataset público utilizado:

**Olist Brazilian E-Commerce Public Dataset**

https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

Arquivo principal:

```text
olist_order_reviews_dataset.csv
```

Coluna analisada:

```text
review_comment_message
```

Essa coluna contém comentários reais escritos por clientes após compras.

Exemplos:

```text
Produto chegou atrasado.
Veio quebrado.
Atendimento muito ruim.
Entrega rápida e produto excelente.
```

---

# 🛠 Tecnologias Utilizadas

## Linguagem
- Python 3.11

## Bibliotecas
- Pandas
- Ollama
- Sentence Transformers
- ChromaDB
- Jupyter Notebook

## Modelo LLM
- Llama 3.2 (executado localmente)

---

# 🧠 Arquitetura do Sistema

Fluxo completo da aplicação:

```text
Pergunta do usuário
        ↓
Embedding da consulta
        ↓
Busca vetorial no ChromaDB
        ↓
Recuperação de documentos
        ↓
Construção de contexto
        ↓
Prompt aumentado (RAG)
        ↓
LLM gera resposta final
```

---

# 📁 Estrutura do Projeto

```bash
.
├── projeto_llm_rag.ipynb
├── olist_order_reviews_dataset.csv
├── requirements.txt
├── README.md
└── relatorio_tecnico.pdf
```

---

# 🚀 Etapas Implementadas

## 1. Aplicação NLP com LLMs

Uso do modelo **Llama 3.2** para:

- Classificação de reclamações  
- Sumarização  
- Question Answering  
- Análise textual  

---

## 2. Prompt Engineering

Foram utilizadas 3 estratégias:

### Zero-shot Prompting
O modelo recebe apenas instruções.

### Few-shot Prompting
Exemplos são fornecidos antes da tarefa.

### Structured Prompting
Uso de:

- papel  
- contexto  
- formato de saída  

---

## 3. Embeddings Semânticos

Modelo utilizado:

```python
sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2
```

Função:

Converter textos em vetores semânticos.

Isso permite busca por **significado**, e não apenas por palavras exatas.

---

## 4. Banco Vetorial

Vector store utilizado:

### ChromaDB

Responsável por:

- armazenar embeddings  
- indexar documentos  
- realizar busca por similaridade  

---

## 5. Pipeline RAG

Pipeline implementado com:

- carregamento dos documentos  
- chunking  
- embeddings  
- indexação vetorial  
- recuperação top-k  
- geração de resposta com contexto  

---

# ⚙️ Instalação

Clone o repositório:

```bash
git clone SEU_LINK_AQUI
cd nome-do-repositorio
```

Instale as dependências:

```bash
pip install -r requirements.txt
```

---

# 💻 Instalação do Ollama

Baixe o Ollama:

https://ollama.com/download

Baixe o modelo:

```bash
ollama pull llama3.2
```

Teste:

```bash
ollama run llama3.2
```

---

# ▶️ Como Executar

## 1. Inicie o Ollama

```bash
ollama run llama3.2
```

## 2. Abra o notebook

```bash
projeto_llm_rag.ipynb
```

## 3. Execute as células em ordem

---

# 📊 Resultados Obtidos

O sistema identificou padrões relevantes nas avaliações:

- Reclamações sobre atraso na entrega  
- Produtos danificados  
- Falhas no atendimento  
- Problemas de logística  

### Observações

✅ RAG reduziu alucinações  
✅ Respostas ficaram mais fundamentadas  
✅ Contexto melhorou a qualidade das respostas  

---

# ⚠️ Limitações

O projeto possui algumas limitações:

- Amostra reduzida de documentos  
- Modelo local pequeno  
- Sem interface gráfica  
- Sem fine-tuning  

---

# 🔮 Melhorias Futuras

Possíveis evoluções:

- Interface web com Streamlit  
- Aumento do corpus  
- Busca híbrida (BM25 + vetorial)  
- Reranking  
- Guardrails de segurança  
- Dashboard analítico  

---

# 📚 Aprendizados

Este projeto consolidou conhecimentos em:

- Large Language Models  
- Prompt Engineering  
- Embeddings  
- Busca Vetorial  
- RAG  
- Inferência Local  

Também permitiu entender desafios reais como:

- custo computacional  
- gerenciamento de contexto  
- alucinações  
- segurança de prompts  

---

# 👩‍💻 Autora

**Fernanda**  
Projeto acadêmico — Sistemas Cognitivos com Large Language Models
