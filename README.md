# 📰 PLN News Analyzer — Sumarização e Análise de Sentimentos

Pipeline de Processamento de Linguagem Natural que busca os **5 artigos mais recentes** de um país selecionado pelo usuário, realiza sumarização automática e classifica o sentimento geral de cada texto — tudo traduzido para o português.

---

## 📌 Objetivo

Dado um país e idioma fornecidos pelo usuário, o sistema:
1. Busca os 5 artigos mais recentes via **Google News**
2. Processa cada artigo com um pipeline LangChain + Gemini
3. Gera um **resumo**, uma **classificação de sentimento** e uma **tradução** para cada artigo
4. Apresenta os resultados em um relatório formatado

---

## ⚙️ Técnicas Utilizadas

- **Normalização das entradas** do usuário (país e idioma)
- **LLM (Gemini 2.5 Flash)** via LangChain para sumarização e análise
- **Extração de dados de URLs** com a biblioteca GNews
- **Sumarização de textos** com LangChain chains
- **Classificação de sentimentos** (positivo / negativo / neutro)
- **Saída estruturada** com Pydantic + JsonOutputParser

---

## 🏗️ Pipeline

```
Entrada do usuário (país + idioma)
        ↓
   GNews API — busca os 5 artigos
        ↓
  LangChain Mega-Chain
  ├── Sumarização (Gemini 2.5 Flash)
  ├── Classificação de sentimento
  └── Tradução para o idioma alvo
        ↓
  Relatório formatado (Markdown/HTML)
```

---

## 🛠️ Tecnologias

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white)
![Google Gemini](https://img.shields.io/badge/Gemini%202.5%20Flash-4285F4?style=for-the-badge&logo=google&logoColor=white)
![Google Colab](https://img.shields.io/badge/Google%20Colab-F9AB00?style=for-the-badge&logo=google-colab&logoColor=black)

**Bibliotecas principais:** `langchain`, `langchain-google-genai`, `gnews`, `pydantic`, `python-dotenv`

---

## 🔑 Obtendo as chaves de API

O projeto requer duas chaves de API gratuitas. Siga os passos abaixo:

---

### Google Gemini API Key

1. Acesse [aistudio.google.com](https://aistudio.google.com) e faça login com sua conta Google
2. Clique em **"Get API Key"** no menu lateral esquerdo
3. Clique em **"Create API Key"**
4. Copie a chave gerada — ela tem o formato `AIzaSy...`

> ✅ O plano gratuito é suficiente para rodar o projeto. Não é necessário cartão de crédito.

---

### GNews API Key

1. Acesse [gnews.io](https://gnews.io) e clique em **"Get API Key"**
2. Crie uma conta gratuita (nome, e-mail e senha)
3. Confirme o e-mail recebido
4. Sua chave estará disponível no painel após o login

> ✅ O plano gratuito permite até 100 requisições por dia, suficiente para uso do projeto.

---

## 🚀 Como executar

> ⚠️ Tenha em mãos as duas chaves de API antes de executar (veja a seção acima).

1. Abra o notebook no Google Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](SEU_LINK_DO_COLAB_AQUI)

2. Execute as células em ordem. Na célula de configuração, insira sua chave de API quando solicitado.

3. Quando perguntado, informe:
   - O **código do país** (ex: `br`, `us`, `jp`, `fr`)
   - O **idioma** da notícia que será traduzida

---

## 📁 Estrutura do Repositório

```
pln-news-analyzer/
├── Projeto_PLN.ipynb     # Notebook principal com todo o pipeline
└── README.md
```

---

## 📚 Contexto

Projeto desenvolvido como trabalho acadêmico na disciplina de **Processamento de Linguagem Natural (PLN)** no curso de **Ciência da Computação** da **Universidade Federal do ABC (UFABC)**.
