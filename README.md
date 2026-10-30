# 🤖 Oráculo — Assistente de IA para Análise de Documentos e Mídias

O **Oráculo** é uma aplicação interativa de chat com Inteligência Artificial construída em Python com **Streamlit** e **LangChain**. O agente permite carregar diferentes fontes de dados (sites, vídeos do YouTube e arquivos PDF, CSV ou TXT) e conversar diretamente com o conteúdo utilizando modelos de linguagem (LLMs) da **Groq**, **OpenAI** ou **Google Gemini**.

---

## ✨ Funcionalidades

- **Múltiplas Fontes de Conhecimento:**
  - 🌐 **Sites (URL):** Extração de texto de páginas web com rotação de *User-Agent*.
  - ▶️ **YouTube:** Extração automática da transcrição/legenda em português de vídeos do YouTube.
  - 📄 **PDF:** Leitura e extração de texto de documentos PDF.
  - 📊 **CSV:** Carregamento estruturado de bases de dados em CSV.
  - 📝 **TXT:** Leitura de arquivos de texto puro.
- **Múltiplos Provedores de LLM:** Alternância fácil na interface entre modelos da **Groq**, **OpenAI** e **Gemini (Google)**.
- **Memória de Conversação:** Mantém o histórico do diálogo durante a sessão (`ConversationBufferMemory`).
- **Respostas em Streaming:** Exibição da resposta da IA em tempo real na interface do chat.

---

## 🛠️ Tecnologias e Ferramentas Utilizadas

- **[Python 3.13+](https://www.python.org/)** — Linguagem base do projeto
- **[Streamlit](https://streamlit.io/)** — Criação da interface web interativa e gerenciamento de estado da sessão
- **[LangChain](https://www.langchain.com/)** (`langchain`, `langchain-community`) — Orquestração de prompts (`ChatPromptTemplate`), chains (LCEL), memória de conversa e *Document Loaders*
- **[LangChain Groq](https://python.langchain.com/docs/integrations/chat/groq/) & [LangChain OpenAI](https://python.langchain.com/docs/integrations/chat/openai/)** — Integração com os provedores de LLMs
- **[BeautifulSoup4](https://www.crummy.com/software/BeautifulSoup/) & [Unstructured](https://unstructured.io/)** — Parsing e extração de conteúdo de páginas web (`WebBaseLoader`)
- **[Fake UserAgent](https://pypi.org/project/fake-useragent/)** — Geração de cabeçalhos `User-Agent` dinâmicos para requisições web
- **[PyPDF](https://pypdf.readthedocs.io/)** — Extração de texto de arquivos PDF (`PyPDFLoader`)
- **[YouTube Transcript API](https://pypi.org/project/youtube-transcript-api/)** — Coleta de transcrições de vídeos do YouTube (`YoutubeLoader`)
- **[Python-dotenv](https://pypi.org/project/python-dotenv/)** — Gerenciamento de variáveis de ambiente

---

## 📂 Estrutura do Projeto

```text
├── arquivos/               # Arquivos de exemplo para testes (PDF, CSV, TXT)
├── app.py                  # Aplicação principal (interface Streamlit e lógica da Chain)
├── loaders.py              # Funções de carregamento de dados (Site, YouTube, PDF, CSV, TXT)
├── requirements.txt        # Dependências do projeto
├── .gitignore              # Arquivos e pastas ignorados pelo Git
└── README.md               # Documentação do projeto
```

---

## 🚀 Como Executar o Projeto

### 1. Criar e ativar o ambiente virtual

No terminal (PowerShell), na pasta do projeto:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

### 2. Instalar as dependências

```powershell
pip install -r requirements.txt
```

### 3. Executar a aplicação no Streamlit

```powershell
streamlit run app.py
```

### 4. Utilizar na interface
1. Na barra lateral, na aba **Upload de Arquivos**, escolha o tipo de fonte (`Site`, `Youtube`, `Pdf`, `Csv` ou `Txt`) e informe a URL, o ID do vídeo ou faça o upload do arquivo.
2. Na aba **Seleção de Modelos**, escolha o provedor (**Groq** ou **OpenAI**), selecione o modelo desejado e insira sua **API Key**.
3. Clique em **Inicializar Oráculo** e envie suas perguntas no chat!

