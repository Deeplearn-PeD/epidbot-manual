# Manual do Usuário do EpiDBot

![EpiDBot Logo](screenshots/epidbot-logo.png)

**Análise de Dados de Saúde Pública com Inteligência Artificial**

Versão 2.8.0 | Kwar-AI

---

## Índice

1. [Boas-vindas](#boas-vindas)
2. [Primeiros Passos](#primeiros-passos)
3. [Sua Primeira Análise](#sua-primeira-análise)
4. [A Interface de Chat](#a-interface-de-chat)
5. [Fontes de Dados](#fontes-de-dados)
6. [Meus Dados](#meus-dados)
7. [Analisando Dados](#analisando-dados)
8. [Editor de Código no Navegador (IDE)](#editor-de-código-no-navegador-ide)
9. [Visualizações e Gráficos](#visualizações-e-gráficos)
10. [Meus Gráficos](#meus-gráficos)
11. [Projetos](#projetos)
12. [Blipper — O Feed de Compartilhamento de Dados](#blipper)
13. [Malaria Atlas](#malaria-atlas)
14. [Plugin QGIS do EpiDBot](#plugin-qgis-do-epidbot)
15. [Relatórios](#relatórios)
16. [Sessões](#sessões)
17. [Busca](#busca)
18. [Base de Conhecimento](#base-de-conhecimento)
19. [Configurações](#configurações)
20. [Planos de Assinatura e Recursos por Plano](#planos-de-assinatura-e-recursos-por-plano)
21. [Dicas e Boas Práticas](#dicas-e-boas-práticas)
22. [Idiomas Suportados](#idiomas-suportados)
23. [Resolução de Problemas](#resolução-de-problemas)
24. [Glossário](#glossário)

---

## Boas-vindas

O EpiDBot é um assistente de IA que ajuda você a explorar, analisar e visualizar dados de saúde pública do mundo todo. Seja você um pesquisador estudando tendências de doenças no Brasil, comparando indicadores de saúde entre países ou gerando relatórios para sua pesquisa, o EpiDBot coloca ferramentas epidemiológicas poderosas ao seu alcance através de uma interface conversacional simples.

### O Que o EpiDBot Pode Fazer?

- **Baixar e consultar** conjuntos de dados de saúde pública do Brasil (DATASUS, ANVISA), OMS, ECDC, Banco Mundial, OPAS e mais
- **Executar análises estatísticas** com desdobramentos temporais, espaciais e demográficos
- **Gerar gráficos, mapas e visualizações** automaticamente a partir dos seus dados — incluindo mapas mentais e mapas coropléticos com classificação inteligente
- **Executar código Python e SQL personalizado** em um ambiente sandbox seguro
- **Criar relatórios PDF para download** com modelos integrados (Surto, Avaliação de Risco, Científico, etc.) e temas CSS personalizados
- **Enviar seus próprios conjuntos de dados** (CSV, Excel, GeoJSON e mais) para análise privada junto com dados públicos
- **Enviar seus próprios modelos de relatório** (Markdown + CSS) e compartilhá-los com outros usuários
- **Compartilhar gráficos e relatórios no Blipper** — nosso feed interno de compartilhamento de dados (curtir, responder, seguir colegas)
- **Pesquisar uma base de conhecimento** de documentos e referências epidemiológicas, e explorar cada coleção como uma wiki com grafo de conhecimento interativo
- **Organizar seu trabalho em projetos** — agrupe sessões, relatórios, gráficos e conjuntos de dados relacionados em espaços de trabalho compartilháveis
- **Escrever e executar Python no navegador** com o editor de código integrado — sem precisar instalar nada
- **Conversar com o EpiDBot dentro do QGIS** — instale o [plugin QGIS](https://github.com/Deeplearn-PeD/epidbot-qgis-plugin) para fazer perguntas a partir do seu SIG e carregar respostas GeoJSON direto no mapa (consulte [Plugin QGIS do EpiDBot](#plugin-qgis-do-epidbot))
- **Responder perguntas de esclarecimento** — quando um pedido é ambíguo, o EpiDBot pausa a análise e faz perguntas estruturadas
- **Ficar em dia** com um boletim semanal bilíngue opcional de publicações e atualizações de dados de saúde pública
- **Lembrar suas conversas** entre sessões para que você possa retomar de onde parou

![EpiDBot Welcome Screen](screenshots/welcome-screen.png)

---

## Primeiros Passos

### Criando uma Conta

EpiDBot is currently in beta testing. To request access:

1. Visit the EpiDBot login page
2. Click the **"Request an invitation"** link in the beta notice banner
3. Fill out the registration form
4. Once approved, you will receive your credentials

![Login Page with Beta Notice](screenshots/login-beta-notice.png)

### Fazendo Login

1. Navigate to the EpiDBot login page
2. Enter your **username** and **password**
3. Click **Sign In**

You will be redirected to the chat interface. Your session is secured with JWT authentication.

### Verificação de Email

After registration, you will receive a verification email. Click the link to activate your account. If you did not receive it, go to **Settings > Profile** and click **Resend verification email**.

### Escolhendo Seu Idioma

EpiDBot supports five interface languages:

| Language | Code |
|---|---|
| English | `en` |
| Portugues (Brasil) | `pt-BR` |
| Espanol | `es` |
| 简体中文 | `zh-CN` |
| العربية | `ar` |

EpiDBot automatically detects your browser language on your first visit. You can change it at any time in **Settings > Language** (see [Settings](#settings)).

You can also set the **AI response language** independently — for example, using the interface in English while receiving analysis responses in Portuguese.

### Visão Geral da Navegação

The sidebar (left side on desktop, hamburger menu on mobile) provides access to all sections:

| Icon | Section | Description |
|---|---|---|
| MessageSquare | **Chat** | Start a new analysis conversation |
| FolderOpen | **Sessions** | Browse and manage past conversations |
| Search | **Search** | Search across messages and code snippets |
| Database | **My Data** | Upload and manage your own datasets |
| FileText | **Reports** | Download generated PDF/Markdown reports |
| Image | **My Plots** | Browse and manage your generated and uploaded plots |
| FolderKanban | **Projetos** | Organize sessions, reports, figures, and datasets into workspaces |
| Blipper | **Blipper** | The data storytelling feed |
| BookOpen | **Knowledge Base** | Manage documents and references |
| Star | **Favoritos** | Seus relatórios, gráficos e datasets favoritados |
| Settings | **Settings** | Profile, API keys, plans, Git, Zotero, voz, newsletter, language preferences |

![Sidebar Navigation](screenshots/sidebar-navigation.png)

---

## Sua Primeira Análise

When you open the chat for the first time, EpiDBot will greet you with an onboarding tutorial to help you get started. The welcome screen also displays **analysis starter templates** — clickable suggestion cards with common analysis prompts such as "Analyze dengue trends" or "Compare health indicators." Click any card to immediately start an analysis, or type your own question in the input field.

![Welcome screen with suggestion cards](screenshots/welcome-suggestions.png)

Here is a quick walkthrough:

### Passo 1: Explore os Dados Disponíveis

Type a question like:

> What datasets are available?

EpiDBot will list the data sources you can access, including Brazilian DATASUS systems (SINAN, SIM, SINASC), WHO indicators, ECDC surveillance data, and more.

### Step 2: Download Data

Ask EpiDBot to download a specific dataset:

> Download dengue data for Sao Paulo in 2023

EpiDBot will fetch the data, store it as a parquet file, and confirm when it is ready for analysis.

### Passo 3: Analise e Visualize

> Show me a bar chart of dengue cases by month

EpiDBot will query the data, generate the chart, and display it directly in the chat.

![First Analysis Example](screenshots/first-analysis.png)

---

## A Interface de Chat

The chat is your primary workspace in EpiDBot. It is a full-featured conversational interface with real-time streaming, tool execution feedback, and rich content rendering.

![Chat Interface](screenshots/chat-interface.png)

### Sending Messages

- Type your message in the input field at the bottom
- Press **Enter** to send (Shift+Enter for a new line)
- During streaming, you can type a new message to interrupt and redirect the analysis
- Use **voice input** by clicking the microphone button inside the input field. Speak naturally and your words will be transcribed in real-time. Click the microphone again to stop recording. Voice input uses your browser's built-in speech recognition.

### Respostas em Streaming

EpiDBot streams responses in real-time. You will see:

1. **Analyzing animation** — the EpiDBot avatar pulses with a complexity indicator:
   - "Quick answer" — simple factual questions
   - "Standard analysis" — single data lookups
   - "Detailed analysis" — multi-step analysis with plots
   - "Deep analysis" — complex modeling or cross-dataset work

2. **Tool execution** — when EpiDBot uses a tool (downloading data, running SQL, generating a plot), you will see:
   - The tool name and a progress bar
   - Elapsed time counter
   - Status messages ("Processing...", "Analyzing data...")
   - Expandable code preview showing what code is running

3. **Response text** — the answer streams in character by character with a typing cursor

### Interrompendo uma Resposta

While EpiDBot is processing or streaming, you can:

- Type a new message to **interrupt and redirect** the analysis
- Click the **Cancel** button (red square icon) to stop the current response entirely

When you interrupt, any partial results are saved, and a new conversation turn begins with your new message.

### Respondendo Perguntas de Esclarecimento

Às vezes um pedido pode ser interpretado de mais de uma forma. Em vez de adivinhar, o EpiDBot pode pausar a análise no meio do caminho e mostrar um **cartão de perguntas** com uma ou mais perguntas estruturadas (até quatro de uma vez). Cada pergunta tem:

- Um **cabeçalho** curto descrevendo o tema
- **Botões de opção** — de escolha única (botões redondos) ou " marque todos que se aplicam" (caixas de seleção quadradas), cada um com uma breve descrição
- Um **campo de texto livre** para digitar sua própria resposta se nenhuma das opções servir

Selecione suas respostas para todas as perguntas e clique em **Enviar respostas** — o EpiDBot retoma a análise usando-as. Se você não responder em cerca de cinco minutos, o EpiDBot continua com escolhas padrão razoáveis.

### Avatares e Atribuição de Remetente

Cada mensagem de usuário exibe o **avatar do remetente** ao lado dela. Em sessões compartilhadas, cada mensagem mostra o avatar de quem realmente a escreveu — então, quando colegas contribuem para uma conversa compartilhada, você vê de relance quem disse o quê. Usuários sem foto de perfil são exibidos com suas iniciais.

### Editando Mensagens

You can edit your last sent message by hovering over it and clicking the **pencil icon** that appears below. Edit the text in the inline editor and press **Enter** to resubmit. EpiDBot will discard the previous response and generate a new one based on your edited message. Press **Escape** to cancel editing.

### Conteúdo Rico in Messages

EpiDBot renders responses with full formatting support:

- **Markdown** — headings, bold, italic, lists, links
- **Tables** — sortable data tables with styled headers
- **Code blocks** — syntax-highlighted with a dark theme; hover to reveal a **copy button** that copies the code to your clipboard
- **Math/LaTeX** — mathematical notation rendered with KaTeX
- **Images and plots** — charts and maps displayed inline
- **Data tables** — hover to reveal **Copy as TSV** and **Download CSV** buttons for exporting table data

### Copying Messages

Hover over any assistant message to reveal a **copy button** that copies the full response text to your clipboard.

### Unanswered Messages

If a message was sent but never answered (e.g., due to a connection issue), an amber warning banner appears with a **Retry** button.

![Unanswered Message Banner](screenshots/unanswered-message.png)

### Quota Enforcement

Before sending a message, EpiDBot checks your token quota. If you have exceeded your plan limit, an amber banner informs you of the quota status and when your quota resets.

### Exporting Chat as PDF

Click the **Export PDF** button at the top of the chat to download the entire conversation as a formatted PDF document. This includes all messages, plots (embedded as images), tables, and formatting. You can also use the keyboard shortcut `Ctrl+Shift+E`.

### Message Feedback

After EpiDBot responds, you can rate the quality of the answer using the **thumbs up** or **thumbs down** buttons that appear when hovering over an assistant message. Click the same rating again to remove it. This feedback helps improve the system over time.

### Atalhos de Teclado

| Shortcut | Action |
|---|---|
| `Ctrl+K` | Open search |
| `Ctrl+N` | Start new session |
| `Ctrl+Shift+E` | Export chat as PDF |
| `Escape` | Close lightbox / cancel edit |

---

## Fontes de Dados

EpiDBot connects to a wide range of public health data sources worldwide. Ask naturally — EpiDBot will automatically select the right source for your query.

### Brazilian Health Data (DATASUS)

| System | Description |
|---|---|
| **SINAN** | Disease notification system (dengue, Zika, chikungunya, tuberculosis, HIV, etc.) |
| **SIM** | Mortality information system |
| **SINASC** | Live birth information system |
| **SIH/SIA** | Hospital and outpatient information systems |
| **SINAN-NET** | National notifiable diseases network |

You can query data by state, year, municipality, and disease. Example queries:

> Download SINAN dengue data for Rio de Janeiro in 2023

> What is the mortality rate for tuberculosis in the Northeast region?

> List all available datasets for 2024

### Internacional Data Sources

!!! note "Requisito de plano"
    As fontes de dados internacionais abaixo (ECDC, Banco Mundial, OPAS, HealthData.gov, Mosqlimate, ANVISA, Pathoplexus, Malaria Atlas, GADM, GBIF, Eurostat e NZ Health) exigem o plano **Pro** ou superior. Os sistemas brasileiros do DATASUS e os indicadores da OMS estão disponíveis em **todos os planos**, incluindo o Gratuito. Consulte [Planos de Assinatura e Recursos por Plano](#planos-de-assinatura-e-recursos-por-plano).

| Source | Coverage | What You Can Get |
|---|---|---|
| **WHO** (Global Health Observatory) | Global | Health indicators, disease outbreaks, country profiles |
| **ECDC** (European Centre for Disease Prevention and Control) | Europe | Surveillance data, disease reports, epidemiological updates |
| **World Bank** | Global | Health expenditure, life expectancy, immunization rates, demographic indicators |
| **PAHO** (Pan American Health Organization) | Americas | Immunization coverage, malaria/dengue data, health indicators |
| **HealthData.gov** | United States | Hospital capacity, COVID metrics, vaccination data, nursing home data |
| **Malaria Atlas Project** | Global | Plasmodium prevalence, vector occurrence, administrative boundaries, raster surfaces |
| **Pathoplexus** | Global | Genomic sequence counts for organisms of interest |

### Mosqlimate (Brazilian Climate & Epidemiological Data)

- **InfoDengue** — epidemiological reports for dengue and other arboviruses
- **Climate data** — daily and weekly weather observations
- **Mosquito occurrence** — *Aedes aegypti* and *Aedes albopictus* occurrence records
- **EpiScanner** — automated epidemiological surveillance data
- **Prediction models** — browse registered forecasting models for mosquito-borne diseases
- **Predictions** — view submitted predictions and forecasts from the model registry

### Dados Geográficos

- **GADM** — administrative boundaries for any country (states, municipalities, regions)
- **Brazilian municipalities** — IBGE codes, coordinates, state-level listings

### Fontes Mais Especializadas

- **ANVISA** (Agência Nacional de Vigilância Sanitária) — 15 conjuntos de dados abertos cobrindo medicamentos, segurança alimentar, cosméticos, farmacovigilância e mais. Os dados são acessados via portal federal de dados abertos (dados.gov.br).
- **Atlas de Doenças Infecciosas do ECDC** — 59 doenças em 8 categorias (imunopreveníveis, transmitidas por alimentos/água, ISTs, transmitidas por vetores, respiratórias, zoonóticas) com dados de resistência antimicrobiana para todos os países da UE/EEE.
- **Dados de Saúde da Nova Zelândia** — registros de mortalidade, eventos hospitalares, tábuas de vida e cobertura de imunização do Ministério da Saúde da Nova Zelândia.

### Exemplos de Consultas

> What are the latest WHO disease outbreaks?

> Compare life expectancy across South American countries using World Bank data

> Download malaria vector occurrence data for Kenya

> List all ECDC surveillance datasets available

![Data Source Selection](screenshots/data-sources.png)

---

## Meus Dados

The **My Data** page lets you upload, manage, and preview your own datasets for private analysis alongside public data sources.

### Enviando Conjuntos de Dados

1. Navigate to **My Data** in the sidebar
2. Click the **upload area** or drag and drop a file
3. Optionally add a **description** for your dataset
4. Supported formats: **CSV, ODS, XLSX, GeoJSON, Shapefile (.zip), GeoPackage** (max 50 MB per file)

Uploaded datasets are stored privately under your account and can be queried in the chat just like public data.

!!! note "Limites por plano"
    O número de conjuntos de dados enviados e o armazenamento total dependem do seu plano — Gratuito: 1 conjunto / 100 MB, Pro: 10 / 5 GB, Max: 50 / 25 GB, Equipe: ilimitado. Consulte [Planos de Assinatura e Recursos por Plano](#planos-de-assinatura-e-recursos-por-plano).

![My Data page](screenshots/my-data-page.png)

### Browsing and Searching

The dataset list shows each file with its name, row count, file size, and upload date. Use the **search bar** to filter by filename or description. Sort by **Name**, **Rows**, **Size**, or **Date** using the sort controls.

### Previewing Data

Click a dataset to expand it. Two tabs are available:

- **Schema** — shows column names, data types, and nullable flags
- **Preview** — displays the first 10 rows of data in a scrollable table (up to 15 columns shown, with horizontal scroll for wider datasets)

![Dataset preview](screenshots/dataset-preview.png)

### Managing Datasets

- **Edit description** — click the description text to add or modify a description
- **Refresh** — update the dataset metadata
- **Delete** — remove the dataset (with confirmation)

---

## Analisando Dados

EpiDBot provides a comprehensive suite of analysis tools. Once data is downloaded or available in the catalog, you can ask for any type of analysis.

### Análise Estatística

| Analysis Type | Example Query |
|---|---|
| Temporal analysis | "Show me the trend of dengue cases over time in Sao Paulo" |
| Spatial analysis | "Which municipalities have the highest Zika incidence?" |
| Demographic analysis | "Break down tuberculosis cases by age group and sex" |
| Data quality report | "Generate a data quality report for this dataset" |
| Cross-dataset comparison | "Compare dengue and Zika trends in the same region" |

### Consultas SQL

You can ask EpiDBot to run SQL queries directly on downloaded data:

> Query the dengue dataset to find the top 10 municipalities by case count in 2023

EpiDBot translates your request into DuckDB SQL and returns the results as a formatted table.

### Execução de Código no Sandbox

For advanced analysis, EpiDBot can execute custom Python or SQL code in an isolated sandbox environment:

> Run a Python analysis to calculate the rolling 7-day average of dengue cases

The sandbox includes common scientific libraries: pandas, numpy, matplotlib, seaborn, scikit-learn, and more.

### Modelagem Atuarial

!!! note "Requisito de plano"
    A modelagem atuarial exige o plano **Pro** ou superior. Consulte [Planos de Assinatura e Recursos por Plano](#planos-de-assinatura-e-recursos-por-plano).

O EpiDBot inclui um conjunto de ferramentas de modelagem atuarial comumente usadas em seguros e análise de risco, acionadas inteiramente por linguagem natural:

| Capacidade | O Que Você Obtém |
|---|---|
| **Provisão de sinistros** | Métodos chain-ladder, Bornhuetter-Ferguson e Cape Cod em triângulos de run-off, com provisões por período, estimativas de IBNR, erros padrão de Mack e gráficos de desenvolvimento |
| **Modelagem de sinistros** | Ajuste de distribuições de severidade/frequência por máxima verossimilhança, com testes de aderência e precificação de franquias e limites (VaR/TVaR) |
| **Agregação de portfólio** | Combine perdas componentes em uma distribuição de perda total do portfólio (FFT, recursão de Panjer, Monte Carlo) e precifique camadas de resseguro (excesso de perdas, stop-loss, quota share) |
| **Modelagem de tempo de vida** | Ajuste de modelos paramétricos de sobrevivência/mortalidade (exponencial, Weibull, log-normal e mais, opcionalmente com covariáveis), com expectativa de vida, tempo de vida mediano e gráficos de sobrevivência e risco |

Exemplo de consulta:

> Usando este triângulo de run-off de pagamentos de sinistros, estime as provisões IBNR com o método chain-ladder e mostre o gráfico de desenvolvimento

### Exportando Resultados

> Export the analysis results as a CSV file

EpiDBot supports exporting query results in **CSV, JSON, Excel, and Parquet** formats. Ask naturally:

> Export these results as an Excel file

> Save the data as a Parquet file

Exported files are downloaded directly to your computer.

![Analysis Results](screenshots/analysis-results.png)

---

## Editor de Código no Navegador (IDE)

O IDE permite escrever e executar Python **inteiramente no seu navegador** — sem instalação, sem ida e volta ao servidor. Ele é alimentado pelo Pyodide (Python compilado para WebAssembly) e vem com **numpy, pandas, matplotlib e DuckDB** pré-carregados. Pacotes extras em Python puro podem ser instalados na hora com o instalador de pacotes integrado (micropip).

### Abrindo o IDE

- **Página de Busca** — clique em **Editar e Executar** em qualquer trecho de código salvo
- **Meus Gráficos** — clique em **Editar e Executar** em um cartão de gráfico para abrir uma cópia editável do código dele
- **Relatórios** — abra o painel **Código de Análise** de um relatório e clique em **Abrir no IDE** ao lado de qualquer trecho

### Escrevendo e Executando Código

- O editor oferece destaque de sintaxe Python; clique em **Executar** para rodar
- A saída (texto, figuras, DataFrames) aparece no painel de saída abaixo, estilo Jupyter
- Arraste o **divisor** entre o editor e o painel de saída para redimensioná-los (clique duplo restaura a divisão)
- A execução é limitada a **30 segundos** por execução — para trabalhos mais longos, baixe o código e execute localmente

### Carregando Dados

- Clique em **Carregar Dados** para navegar pelos conjuntos de dados do catálogo e inserir a chamada `load_dataset(...)` correspondente no seu código
- Arquivos sob o diretório `/data/` do servidor — incluindo seus envios privados — ficam transparentemente disponíveis nos seus caminhos habituais, então `pandas.read_parquet(...)`, `open(...)` e consultas DuckDB funcionam como são (arquivos de até 300 MB)

### Salvando Trechos de Código

- Clique em **Salvar** para guardar seu código como um trecho reutilizável (pesquisável na página de Busca)
- Os trechos mantêm um **histórico de versões** que você pode navegar e restaurar
- Um trecho em edição fica **bloqueado** por 30 minutos para que colaboradores não sobrescrevam seu trabalho em paralelo

O IDE está disponível em **todos os planos**.

---

## Visualizações e Gráficos

EpiDBot can generate a wide variety of visualizations automatically. Just describe what you want to see.

### Tipos de Gráficos

| Chart Type | Example |
|---|---|
| Bar chart | "Show a bar chart of cases by state" |
| Line chart | "Plot the temporal trend of malaria cases" |
| Choropleth map | "Create a map of dengue incidence by municipality" |
| Histogram | "Show the age distribution of tuberculosis patients" |
| Box plot | "Compare the distribution of cases across regions" |
| Bubble chart | "Plot GDP vs. life expectancy with population as bubble size" |
| Stacked bar | "Show disease cases stacked by age group" |
| Raster/map | "Render the malaria prevalence raster for Africa" |
| Diagram/flowchart | "Create a flowchart showing the epidemiological surveillance workflow" |

### Working with Plots

- Plots are displayed inline in the chat
- All plots are saved and can be referenced later
- You can ask EpiDBot to adjust colors, labels, or chart type
- Use **"List available plots"** to see previously generated visualizations

### Exemplos de Consultas

> Compare dengue cases across Brazilian states for the last 5 years and create a visualization

> Generate a choropleth map of HIV incidence by municipality in Rio de Janeiro

> Plot a time series of WHO-reported cholera outbreaks

![Plot Example](screenshots/plot-example.png)

---

## Meus Gráficos

The **My Plots** page provides a gallery of all your generated and uploaded visualizations in one place.

### Accessing My Plots

Click **My Plots** in the sidebar to browse all your plots displayed as a card grid.

![My Plots page](screenshots/my-plots-page.png)

### Browsing Plots

Each plot card shows a thumbnail, filename, and description. Use the **search bar** to filter plots by filename or description.

### Lightbox Preview

Click any plot image to open a **full-size lightbox preview** that scales to fit your browser window. Press **Escape** or click outside the image to close.

![Plot lightbox preview](screenshots/plot-lightbox.png)

### Gerenciando Gráficos

- **Copy reference** — copy the markdown image reference for use in chat or reports
- **Editar e Executar** — abra o código do gráfico no IDE no navegador para ajustá-lo e regenerá-lo
- **Adicionar ao projeto** — vincule o gráfico a um dos seus [projetos](#projetos)
- **Edit description** — add or modify the plot description
- **Delete** — remove the plot (with confirmation)
- **Upload your own images** (PNG, JPG, WebP, GIF, SVG)
- **Sync from chats** — click the sync button to scan your chat history and register any plots not yet in the gallery

---

## Projetos

Projetos são **espaços de trabalho transversais** que vinculam suas sessões, relatórios, gráficos e conjuntos de dados existentes em torno de um tema comum — por exemplo, "Dengue Recife 2026". Os itens continuam onde vivem (um relatório permanece na página de Relatórios, um gráfico em Meus Gráficos); o projeto simplesmente os reúne em um só lugar. Projetos estão disponíveis em **todos os planos**.

### Criando um Projeto

1. Clique em **Projetos** na barra lateral
2. Clique em **Novo projeto**, informe um **nome** e uma **descrição** opcional e clique em **Criar**

Você também pode gerenciar projetos pelo chat — basta pedir:

> Crie um projeto chamado "Dengue Recife 2026" e adicione meu relatório mais recente de dengue a ele

### Adicionando Itens

Nas páginas **Meus Gráficos**, **Relatórios**, **Meus Dados** e **Sessões**, clique no botão **Adicionar ao projeto** em qualquer cartão e:

- Escolha um dos seus projetos na lista, ou
- Digite o nome de um novo projeto e clique em **Criar e adicionar**

### Navegando pelos Projetos

Cada cartão de projeto mostra o nome, a descrição e a **contagem de itens por tipo** (sessões, relatórios, figuras, conjuntos de dados), além de um selo "Compartilhado por" quando o projeto foi compartilhado com você. Abra um projeto para ver quatro painéis:

- **Sessões** — conversas vinculadas; clique para retomar
- **Relatórios** — relatórios vinculados
- **Figuras** — gráficos vinculados com miniaturas
- **Conjuntos de Dados** — dados vinculados

Cada item aponta de volta para sua página original e pode ser desvinculado com o botão de lixeira (apenas proprietários e editores).

### Compartilhando Projetos

Os proprietários de projetos podem clicar em **Compartilhar** e conceder acesso de **Visualizador** ou **Editor** a outros usuários. Compartilhar um projeto concede aos destinatários acesso de leitura aos itens que ele contém; editar um item individual ainda exige permissão sobre esse item.

---

## Blipper — O Feed de Compartilhamento de Dados

O Blipper é o feed social interno do EpiDBot que permite compartilhar gráficos, relatórios e insights diretamente das suas análises. Pense nele como um feed estilo Twitter construído para compartilhamento de dados de saúde pública.

### Compartilhando Conteúdo no Blipper

Você pode compartilhar conteúdo no Blipper a partir de:

- **Mensagens do chat** — clique no botão de compartilhar em qualquer bolha de mensagem que contenha uma figura ou análise
- **Meus Gráficos** — clique no botão **Enviar para o Blipper** em qualquer cartão de gráfico

### O Feed

O feed do Blipper mostra posts de pessoas que você segue (aba Início) e todos os posts públicos (aba Explorar):

- **Anexos ricos** — gráficos compartilhados aparecem como miniaturas; clique para abrir um visualizador em tela cheia
- **Relatórios** — relatórios compartilhados aparecem como links clicáveis
- **Interaja** — curta posts, responda a discussões e siga colegas
- **Perfis de usuário** — clique em qualquer nome de usuário para ver seu perfil completo e histórico de posts
- **Notificações** — seja notificado quando alguém curte seu post, responde ou segue você

### Compositor de Posts

Quando você compartilha do chat ou dos gráficos, um rascunho é pré-carregado no compositor de posts com o anexo e uma legenda sugerida. Você pode editar o texto, adicionar menções (`@nome de usuário`) e postar diretamente.

---

## Malaria Atlas

EpiDBot includes dedicated tools for accessing the Malaria Atlas Project (MAP) database, providing global data on malaria prevalence, mosquito vectors, and geographic boundaries.

### Available Data

| Data Type | Description |
|---|---|
| Plasmodium prevalence surveys | Point-in-time parasite rate surveys across the world |
| Vector occurrence data | Geolocated records of *Anopheles* mosquito species |
| Administrative boundaries | Shapefiles for countries, provinces, and districts |
| Raster surfaces | Gridded prevalence estimates and risk maps |
| WHO AFRO admin-level data | Administrative-level malaria indicators via API |

### Exemplos de Consultas

> Download malaria prevalence survey data for Nigeria

> List all available Anopheles vector species

> Download administrative boundaries for Tanzania

> Show me the malaria prevalence raster surface for Southeast Asia

> Get malaria indicator data for Mozambique from WHO AFRO

![Malaria Atlas Tools](screenshots/malaria-atlas.png)

---

## Plugin QGIS do EpiDBot

O **plugin QGIS do EpiDBot** traz o chat do EpiDBot diretamente para dentro do [QGIS](https://qgis.org/), o sistema de informação geográfica livre e de código aberto. Faça perguntas epidemiológicas, gere gráficos e carregue resultados geoespaciais no seu mapa — tudo sem sair do seu fluxo de trabalho em SIG.

O plugin conversa com sua conta EpiDBot pela mesma API REST da interface web, então sessões, gráficos e cotas permanecem sincronizados. Ele é desenvolvido em código aberto em [github.com/Deeplearn-PeD/epidbot-qgis-plugin](https://github.com/Deeplearn-PeD/epidbot-qgis-plugin) sob a licença GPL-2.0-or-later.

### Requisitos

- **QGIS 3.28** ou mais recente (Windows, macOS ou Linux)
- Uma conta EpiDBot nos planos **Max ou Equipe** — as chaves de API estão incluídas nos dois
- Uma **chave de API do EpiDBot** pessoal — crie uma na interface web do EpiDBot em **Configurações > Chaves de API** (consulte [Chaves de API](#chaves-de-api))
- Conexão com a internet até o servidor do EpiDBot

O plugin está publicado no **repositório oficial de plugins do QGIS** como [EpidBot](https://plugins.qgis.org/plugins/epidbot/) (ID `6764`).

### Instalando o Plugin

**Pelo repositório oficial de plugins (recomendado):**

1. No QGIS, abra **Complementos > Gerenciar e Instalar Complementos**
2. Busque por **EpidBot** — ou abra a [página do plugin](https://plugins.qgis.org/plugins/epidbot/) no navegador
3. Clique em **Instalar Complemento**
4. Abra o painel **EpiDBot Chat** na barra de ferramentas do QGIS (ou em **Ver > Painéis**)

Instalado assim, o plugin é atualizado pelo próprio gerenciador de complementos do QGIS.

**A partir de um pacote ZIP** — apenas quando precisar de uma versão mais nova do que a já publicada:

1. Baixe o ZIP mais recente do plugin: [epidbot.zip](https://github.com/Deeplearn-PeD/epidbot-qgis-plugin/releases/latest/download/epidbot.zip) — este link sempre aponta para a versão mais recente
2. No QGIS, abra **Complementos > Gerenciar e Instalar Complementos > Instalar a partir de ZIP**
3. Selecione o arquivo baixado e clique em **Instalar Complemento**
4. Abra o painel **EpiDBot Chat** na barra de ferramentas do QGIS

### Configurando o Plugin

Clique no **botão ⚙ (engrenagem)** no painel de chat para abrir as configurações:

| Configuração | Significado |
|---|---|
| **URL do Servidor** | URL base da API do EpiDBot — pré-preenchida com o padrão `https://api.epidbot.kwar-ai.com.br` |
| **Chave de API** | Sua chave de API pessoal do EpiDBot, enviada no cabeçalho `X-API-Key` em cada requisição. Armazenada no cofre de credenciais do sistema quando o pacote opcional `keyring` está disponível |
| **Idioma das respostas** | Idioma das respostas da IA: `en` ou `pt-BR` |
| **Intervalo de sondagem de status** | Segundos entre as consultas de status do trabalho (padrão 1,5 s) |

### Conversando pelo QGIS

O painel de chat **EpiDBot Chat** encaixável funciona como o chat web:

- Digite uma pergunta e pressione Enter — as respostas são renderizadas com formatação Markdown, tabelas e miniaturas de gráficos embutidas
- Escolha uma **sessão existente** no seletor de sessões, inicie uma **nova** ou deixe o servidor criar uma automaticamente; ao trocar de sessão o histórico é recarregado, incluindo os gráficos
- **Exporte uma conversa** para um arquivo Markdown
- A interface do painel está disponível em **inglês e português do Brasil**, e as requisições de chat rodam em uma thread de segundo plano para o QGIS continuar responsivo enquanto o EpiDBot trabalha

### Integração com o Mapa

É aqui que o plugin brilha — o EpiDBot entende o seu projeto do QGIS e pode devolver resultados diretamente no mapa:

- **Injeção de contexto do mapa** — cada pergunta inclui automaticamente suas camadas ativas (com nomes de campos, valores de exemplo e seleções atuais), a extensão do canvas (EPSG:4326) e o SRC do projeto, para que o EpiDBot saiba o que você está vendo
- **Prompts espaciais** — ações de um clique na barra de ferramentas permitem perguntar sobre a **extensão atual do mapa** ou as **feições que você selecionou**
- **"Adicionar ao mapa"** — blocos GeoJSON e URLs de conjuntos de dados nas respostas viram camadas estilizadas no canvas com um único clique

Prompts de exemplo:

> Mapeie a incidência de dengue dos municípios atualmente carregados no meu projeto

> Qual é a população total dos municípios selecionados?

### Trabalhando com Gráficos

Cada gráfico gerado pelo plugin oferece três ações:

- **Salvar no disco** — exportar o arquivo de imagem
- **Abrir no visualizador de imagens**
- **Inserir em layout de impressão** — adicione o gráfico a um layout de impressão *"EpidBot Plots"* para composições cartográficas

### Em Breve

Recursos planejados incluem um **navegador do catálogo de conjuntos de dados** (navegue pelos dados do EpiDBot e carregue-os diretamente como camadas do QGIS) e envio de documentos a partir do QGIS — fique de olho na [página de releases](https://github.com/Deeplearn-PeD/epidbot-qgis-plugin/releases).

---

## Relatórios

EpiDBot can generate comprehensive PDF and Markdown reports from your analyses, using built-in templates with distinct visual styles.

### Modelos de Relatório

O EpiDBot vem com **6 modelos de relatório integrados**, cada um com sua própria estrutura e tema de cores:

| Template | Best for | Style |
|---|---|---|
| **Investigação de Surto** | Relatórios de surtos de doenças | Acento ciano/azul |
| **Avaliação Rápida de Risco** | Pontuação de risco e avaliação de confiança | Indicadores vermelho/laranja |
| **Resumo Epidemiológico** | Resumos operacionais de vigilância | Acento verde, foco em dados |
| **Relatório Científico** | Publicações acadêmicas | Preto/serifado, formal |
| **Investigação de Campo** | Relatórios de investigação de campo de curto prazo | Acento azul, estilo narrativo |
| **Relatório Técnico** | Relatórios técnicos/analíticos gerais | Acento roxo, amigável para código |

Você também pode **enviar seus próprios modelos personalizados** (estrutura Markdown + tema CSS) e compartilhá-los com outros usuários. Os modelos são gerenciados na página de Relatórios — clique no cabeçalho **Modelos** para expandir a galeria de modelos.

Os PDFs gerados incluem o logotipo da Kwar-AI no rodapé ao lado do texto "Gerado por EpidBot".

### Gerando um Relatório

Peça ao EpiDBot para criar um relatório com um modelo específico:

> Gere um relatório estruturado sobre tendências de dengue no Brasil em 2023 usando o modelo de Investigação de Surto

> Crie uma avaliação rápida de risco para o surto atual de chikungunya

O EpiDBot compilará os resultados da análise, gráficos e interpretações em um documento formatado usando o modelo selecionado.

### Baixando Relatórios

1. Navigate to **Reports** in the sidebar
2. Browse your generated reports
3. Click the **Download PDF** or **Download Markdown** icon

Each report card shows the title, type (analysis, summary, data quality, comparison), creation date, file size, and number of images. The card toolbar also provides **Edit**, **Add to project**, **Improve with AI**, **Download LaTeX (ZIP)**, **BibTeX** (when the report has references), and share actions.

### Gerenciando Relatórios

- **Search** reports by title or type
- **Delete** reports you no longer need (with confirmation)
- **Version history** — click a report to open the editor, where you can view all past versions and restore a previous version *(plano Max)*
- **Edit and regenerate** — modify the markdown content and regenerate the PDF
- Admins can toggle between **"All Reports"** and **"My Reports"** to view all users' reports

### Exportação LaTeX

!!! note "Requisito de plano"
    A exportação LaTeX exige o plano **Max**.

Clique no botão **Baixar LaTeX (ZIP)** em um cartão de relatório para obter um arquivo pronto para compilação contendo:

- O **código-fonte `.tex`** — abra-o diretamente no Overleaf ou em qualquer editor LaTeX
- **`figures/`** — todas as figuras referenciadas pelo relatório (convertidas para PNG quando necessário)
- **`references.bib`** — uma bibliografia BibTeX; as citações no texto são reescritas para comandos `\cite{...}` adequados
- **`code/`** — todos os trechos de código de análise vinculados ao relatório, com nomes descritivos e um README

### Manuscritos Científicos

!!! note "Requisito de plano"
    O agente de manuscritos científicos exige o plano **Max**.

Peça ao EpiDBot para escrever um manuscrito completo e ele inicia um pipeline de IA em múltiplas etapas (planejar, analisar, escrever, referenciar, revisar) que produz um relatório no formato IMRaD voltado à publicação:

> Escreva um manuscrito científico sobre tendências de dengue no Rio de Janeiro de 2020 a 2024 usando dados do SINAN

A geração do manuscrito roda como um trabalho em segundo plano (tipicamente 10–15 minutos) — você pode continuar conversando enquanto isso, e um banner **"Manuscrito pronto"** com um link aparece quando estiver concluído. Os manuscritos incluem:

- Uma **seção de Métodos com qualidade de publicação**, com o fluxo completo de proveniência dos dados, especificação formal de cada modelo e métrica, e uma declaração de reprodutibilidade
- **Equações numeradas** que podem ser referenciadas no texto, na tela, no PDF e na exportação LaTeX
- Um **painel de Código de Análise** na página do relatório listando todos os trechos usados, cada um com as ações **Abrir no IDE** e **Copiar**

### Limites por Plano para Relatórios

- **Gratuito** — até **3 relatórios por mês**; os PDFs baixados contêm uma marca d'água discreta "PLANO GRATUITO"
- **Pro** — relatórios ilimitados, sem marca d'água
- O **compartilhamento de relatórios** exige o plano **Pro**; **coautoria**, **publicação no Zenodo**, **histórico de versões**, **exportação LaTeX** e **envio para Overleaf** exigem o plano **Max**

Consulte [Planos de Assinatura e Recursos por Plano](#planos-de-assinatura-e-recursos-por-plano) para a matriz completa.

### Compartilhando Relatórios

Share reports with other EpiDBot users:

1. Click the **share icon** on a report card
2. Enter a **username** and choose **Can view** or **Can edit** permission
3. Shared reports appear in the recipient's Reports page with a shared badge

![Reports Page](screenshots/reports-page.png)

---

## Sessões

Every chat conversation is automatically saved as a **session**. You can view, resume, rename, share, and delete sessions.

### Acessando Sessões

Click **Sessions** in the sidebar to see all your conversations.

The session sidebar in the chat view can be **collapsed** by clicking the collapse button in its header. This gives you more space for the chat. Click the expand button to bring it back.

![Sessions Page](screenshots/sessions-page.png)

### Cartões de Sessão

Each session card displays:

- Session name
- Message count
- Last activity time (e.g., "2 hours ago")
- **Shared** badge if the session has been shared with or by others

### Gerenciando Sessões

| Action | How |
|---|---|
| Create new session | Click the **+** button, type a name, press Enter |
| Rename a session | Click the **pencil** icon on the session card |
| Delete a session | Click the **trash** icon (confirms before deleting) |
| Resume a session | Click the session card to open the conversation |

### Compartilhando Sessões

You can share sessions with other EpiDBot users:

!!! note "Limites por plano"
    O plano **Gratuito** permite **1 link de compartilhamento ativo**; os planos **Pro** e superiores têm links ilimitados. Consulte [Planos de Assinatura e Recursos por Plano](#planos-de-assinatura-e-recursos-por-plano).

1. Click the **share** icon on a session card
2. Type a **username** in the dialog (autocomplete will suggest matches)
3. Choose a permission level:
   - **Can view** — read-only access to the conversation
   - **Can edit** — full access to continue the conversation
4. Click **Share**

To revoke access, open the share dialog and click **Revoke access** next to the user's name.

### Restrições de Sessões Compartilhadas

- Sessions shared with you as "read-only" cannot be modified — the input area is replaced with a lock icon and message
- Sessions received from others cannot be renamed, deleted, or re-shared
- When someone shares a session with you, a blue notification banner appears at the top of your chat

---

## Busca

The search page lets you find content across all your conversations and saved code snippets, with filters to narrow results by type.

### Buscaing

1. Navigate to **Search** in the sidebar
2. Enter your search query in the text field
3. Use as abas do **seletor de tipo** para filtrar os resultados:
   - **Tudo** — busca tanto mensagens de chat quanto trechos de código
   - **Sessões** — busca apenas histórico de conversas do chat
   - **Trechos de Código** — busca apenas código de análise salvo
4. Optionally filter by **session** or **date range**
5. Results appear in two categories:
   - **Code Snippets** — reusable code with language badges and download buttons
   - **Chat Messages** — matching messages with content preview and timestamps

### Busca Results

- Click any chat message result to navigate directly to that conversation
- Code snippets can be expanded to view the full source code
- Export individual messages as Markdown

![Search Page](screenshots/search-page.png)

---

## Base de Conhecimento

The knowledge base stores documents and references that EpiDBot can search when answering your questions. It supports semantic search across embedded documents.

### Checking Status

The knowledge base status card shows whether the service is healthy and displays the current version. Click **Check Status** to refresh.

### Buscaing the Knowledge Base

1. Enter a search query in the **search field**
2. Optionally select a **collection** to narrow results
3. Results show: document name, relevance score, collection, and content preview

### Adicionando Fontes

!!! note "Somente administradores"
    Adicionar fontes à base de conhecimento (páginas web, texto, upload de documentos e publicações do Ministério da Saúde) é restrito a **administradores**. Usuários regulares têm acesso somente leitura: a busca na base de conhecimento e a navegação por coleções, fontes e wikis está disponível em todos os planos.

Administradores podem adicionar conteúdo à base de conhecimento de três formas:

| Method | What to Do |
|---|---|
| **Web Page** | Paste a URL and click "Add Web Page" — EpiDBot will fetch, extract, and embed the content |
| **Text Content** | Provide a document name and paste the text content |
| **Upload Document** | Upload a file (.pdf, .txt, .md, .doc, .docx) |

When adding content, select a target **collection** (or use the default collections: datasus, epidemiology, methodology).

### Gerenciando Coleções

The right panel shows:

- **Collections** — all collections with their document counts
- **Sources** — all documents with name and collection, sortable alphabetically

### Wiki e Grafo de Conhecimento

A aba **Wiki** transforma cada coleção em uma estrutura de conhecimento navegável, estilo Wikipédia, construída automaticamente a partir dos seus documentos:

- **Árvore de páginas** — páginas organizadas por categoria (Fontes, Entidades, Conceitos, Síntese), com `[[wikilinks]]` clicáveis entre páginas relacionadas
- **Pergunte à wiki** — digite uma pergunta e receba uma resposta sintetizada com fontes citadas, nível de confiança e perguntas de acompanhamento sugeridas *(plano Max)*
- **Visão em grafo** — clique no botão **Grafo** para explorar o **grafo de conhecimento** da coleção: nós de páginas, entidades e conceitos, com chips de status mostrando contagens de nós/arestas e as páginas centrais. Disponível em **todos os planos**.

Você também pode consultar a wiki e seu grafo de conhecimento diretamente pelo chat. Administradores podem reconstruir o grafo pelo cartão **Administração > Gerenciamento da Wiki**, que também exibe estatísticas em tempo real do grafo.

![Knowledge Base Page](screenshots/knowledge-base-page.png)

---

## Configurações

The settings page lets you manage your profile, security, API access, subscription, and language preferences.

![Settings Page](screenshots/settings-page.png)

### Perfil

Edit your **username**, **email**, and **CPF/CNPJ** (required for payments in Brazil). Click **Update Profile** to save.

### Alterar Senha

Provide your current password and a new password (minimum 8 characters). The new password must be confirmed.

### Chaves de API

As chaves de API permitem acesso programático à API REST do EpiDBot. **Disponíveis nos planos Max e Equipe** — o Equipe herda todos os recursos do Max (consulte [Planos de Assinatura e Recursos por Plano](#planos-de-assinatura-e-recursos-por-plano)).

As chaves de API são também o que o [plugin QGIS do EpiDBot](#plugin-qgis-do-epidbot) usa para rodar o assistente dentro do QGIS.

- **Criar uma chave**: Digite um nome e clique em criar. A chave é exibida apenas uma vez — copie-a imediatamente, pois não pode ser visualizada novamente.
- **Gerenciar chaves**: Visualize as chaves existentes (mostrando nome e prefixo), exclua as que não precisa mais.

### Agentes Externos

Agentes externos são assistentes de IA compatíveis com OpenClaw (como o [nanobot](https://github.com/HKUDS/nanobot)) executados fora do EpiDBot. Uma vez registrados, o EpiDBot pode **enviar mensagens a eles durante uma conversa** e repassar as respostas de volta para você. Este é o caminho inverso da [skill do EpiDBot](https://github.com/openclaw/clawhub) que permite que agentes externos consultem o EpiDBot — ele permite que o EpiDBot consulte *seus* agentes. **Exige o plano Max ou superior (Max ou Equipe).**

#### Registrando um Agente

Em **Configurações > Agentes Externos**, preencha três campos e clique em **Registrar Agente**:

| Campo | Descrição | Exemplo |
|-------|-----------|---------|
| **Nome** | Um rótulo único para este agente (letras, números, espaços, hífens, underscores; máx. 100 caracteres). Você usará este nome ao pedir ao EpiDBot para contatá-lo. | `meu-nanobot` |
| **URL Base** | O endpoint HTTPS público onde o agente é acessível. Não deve resolver para um IP privado ou de loopback (bloqueado pela proteção SSRF). | `https://meu-agente.exemplo.com` |
| **Token Bearer** | O token de autenticação que o EpiDBot enviará no cabeçalho `Authorization: Bearer`. Este é o token que a API do seu agente espera. Armazenado criptografado no banco de dados. | `sk-abc123...` |

O EpiDBot envia mensagens para o seu agente usando o endpoint padrão **compatível com OpenAI `/v1/chat/completions`**. A maioria dos runtimes de agentes (incluindo o comando `nanobot serve` do nanobot) expõe este endpoint por padrão.

#### Usando Agentes Externos

Uma vez registrado, você pode pedir ao EpiDBot para consultar o agente a qualquer momento durante uma conversa:

> *"Consulte meu agente chamado meu-nanobot e pergunte: qual é a situação atual da dengue no Sudeste Asiático?"*

O EpiDBot chamará a ferramenta `query_external_agent`, que envia sua mensagem para a API do agente e retorna a resposta. Você pode registrar múltiplos agentes e endereçar cada um pelo nome.

#### Gerenciando Agentes

- **Visualizar** — os agentes registrados aparecem em uma lista com nome, URL e uma prévia mascarada do token
- **Excluir** — clique no ícone de lixeira para remover um agente; seu token criptografado é permanentemente excluído do banco de dados
- **API REST** — os agentes também podem ser gerenciados programaticamente via `GET/POST/DELETE /api/v1/external-agents`

#### Segurança

- Os tokens de autenticação são **criptografados com Fernet** em repouso usando o segredo mestre do servidor — nunca são armazenados em texto plano
- As requisições de saída incluem apenas o cabeçalho `Authorization: Bearer <token>` e um corpo JSON
- Requisições para **faixas de IP privadas** (127.x, 10.x, 172.16–31.x, 192.168.x, link-local) são **bloqueadas** para prevenir ataques SSRF

### Plano e Uso de Consultas

Seu plano determina sua cota diária de IA e quais recursos avançados você pode usar. Cada consulta representa uma interação com a IA (1 consulta = aproximadamente 50.000 tokens de processamento).

| Plano | Cota Diária | Consultas/dia | Preço |
|---|---|---|---|
| **Gratuito** | 50.000 tokens | 1 | R$0 |
| **Pro** | 500.000 tokens | 10 | R$97/mês |
| **Max** | 1.500.000 tokens | 30 | R$197/mês |
| **Equipe** | Ilimitada | Ilimitadas | R$1.425/mês |

Para a matriz completa de recursos por plano e os limites de uso (relatórios mensais, links de compartilhamento, armazenamento de dados e mais), consulte [Planos de Assinatura e Recursos por Plano](#planos-de-assinatura-e-recursos-por-plano).

- **Selo do plano atual** — Gratuito, Pro, Max ou Equipe
- **Barra de uso** — mostra consultas usadas vs. limite, com cores (verde < 70%, amarelo 70-90%, vermelho > 90%)
- **Data de reinício** — quando sua cota é renovada

#### Atualizando Seu Plano

1. Click **Upgrade** to open the plan selector
2. Choose between **monthly plans** and **consultation packs**
3. Select a payment method:
   - **PIX** — scan the QR code or copy the PIX code, payment is confirmed automatically
   - **Credit Card** — redirected to a secure payment page
4. Once payment is confirmed, your plan is updated immediately

#### Pacotes de Consulta

Consultation packs are one-time purchases that do not expire. They are consumed after your monthly quota runs out.

#### Desconto Acadêmico (50% de Desconto)

Estudantes, docentes e pesquisadores podem obter **50% de desconto em qualquer plano pago**. Há duas formas de se qualificar:

1. **Automaticamente** — verifique um endereço de email em um domínio acadêmico (`.edu*`, `.ac.<país>`, além de domínios institucionais reconhecidos). O desconto é aplicado assim que o email é verificado.
2. **Por solicitação** — se seu email não é de um domínio acadêmico, clique em **"Solicitar desconto acadêmico"** em **Configurações > Plano**. A solicitação vai para análise dos administradores e você receberá um email quando for aprovada. O selo exibe **"em análise"** nesse intervalo. É necessário ter um email verificado para enviar a solicitação.

Uma vez concedido, o desconto é aplicado **automaticamente no checkout** de qualquer plano (Pro, Max ou Equipe) — sem necessidade de cupom. O EpiDBot também oferece um **desconto anual** (pagamento antecipado de 12 meses); quando ambos se aplicam, vale o melhor desconto único (eles nunca se acumulam).

### Preferências de Idioma

Two independent language settings:

1. **Interface Language** — controls the UI language (sidebar, buttons, labels)
2. **Chat Response Language** — controls the language EpiDBot uses in its analysis responses

You can, for example, set the interface to English while having EpiDBot respond in Portuguese.

### Boletim (Newsletter)

Assine o **boletim semanal bilíngue** (edições em português e inglês) com um resumo de publicações e atualizações de dados de saúde pública, incluindo:

- Publicações do Ministério da Saúde e novos conjuntos de dados do dados.gov.br
- Atualizações do Mosqlimate/InfoDengue e Disease Outbreak News da OMS
- Notícias de saúde de feeds RSS curados

Clique em **Assinar** no cartão **Newsletter** da página de Configurações. Você receberá um email de confirmação e deverá clicar no link dele para ativar a assinatura (**dupla confirmação**). Você pode cancelar a assinatura a qualquer momento no mesmo cartão ou pelo link incluído em cada edição. As edições enviadas também ficam disponíveis em um **arquivo web**, e **feeds RSS** por idioma são vinculados na página de login. Administradores gerenciam o boletim (agenda, fontes, feeds RSS, edições, assinantes e dicas) em **Administração > Newsletter**.

### About

Displays the application version and description.

---

## Planos de Assinatura e Recursos por Plano

O EpiDBot oferece quatro planos de assinatura. Seu plano determina tanto a **cota diária de uso da IA** quanto os **recursos avançados** que você pode acessar. Você pode ver seu plano atual, uso e fazer upgrade a qualquer momento em **Configurações > Plano**.

### Visão Geral dos Planos

| Plano | Cota Diária de IA | Consultas/dia | Preço |
|---|---|---|---|
| **Gratuito** | 50.000 tokens | 1 | R$0 |
| **Pro** | 500.000 tokens | 10 | R$97/mês |
| **Max** | 1.500.000 tokens | 30 | R$197/mês |
| **Equipe** | Ilimitada | Ilimitadas | R$1.425/mês |

*1 consulta ≈ 50.000 tokens de processamento de IA. As cotas diárias reiniciam todos os dias e não acumulam. Os pacotes de consulta (compras únicas que nunca expiram) são consumidos após o esgotamento da cota diária.*

### Descontos

| Desconto | Valor | Como se Qualificar |
|---|---|---|
| **Acadêmico** | 50% em qualquer plano | Email verificado em domínio acadêmico, ou solicitação aprovada (veja [Configurações > Plano](#plano-e-uso-de-consultas)) |
| **Anual** | 30% | Pagamento antecipado de 12 meses (cobrança única) |

Os descontos nunca se acumulam — vale o melhor desconto único, e o desconto acadêmico tem precedência quando ambos se qualificam. Veja [Desconto Acadêmico](#desconto-academico-50-de-desconto) para o fluxo de solicitação.

### Limites de Uso por Plano

| Limite | Gratuito | Pro | Max | Equipe |
|---|---|---|---|---|
| Relatórios por mês | 3 | Ilimitados | Ilimitados | Ilimitados |
| Links de compartilhamento ativos | 1 | Ilimitados | Ilimitados | Ilimitados |
| Marca d'água em relatórios PDF | Sim | Não | Não | Não |
| Relatórios agendados (periódicos) | — | 2 | 10 | Ilimitados |
| Conjuntos de dados enviados | 1 | 10 | 50 | Ilimitados |
| Armazenamento de dados | 100 MB | 5 GB | 25 GB | Ilimitado |

### Matriz de Recursos por Plano

Cada recurso abaixo exige o plano indicado **ou superior**. Qualquer recurso não listado — chat com dados do DATASUS e da OMS, análises e gráficos padrão, execução de código no sandbox, o IDE no navegador, projetos, busca, histórico de sessões, geração de relatórios dentro do limite mensal e o boletim — está disponível em **todos os planos, incluindo o Gratuito**.

#### Pro

| Recurso | O Que Você Obtém |
|---|---|
| **Integração Zotero** | Listar coleções do Zotero, buscar referências e exportar citações |
| **Integrações Git** | Ler repositórios GitHub/GitLab pelo chat (issues, PRs, arquivos, clones) |
| **Web scraping completo** | Extração de múltiplos arquivos de páginas web com renderização JavaScript |
| **Todas as fontes internacionais** | ECDC e Atlas ECDC, Banco Mundial, OPAS, HealthData.gov, ANVISA, Mosqlimate, Pathoplexus, Malaria Atlas, GADM, GBIF, Eurostat e dados da Nova Zelândia |
| **Ferramentas de análise avançada** | DAGs causais, diferença-em-diferenças, séries temporais interrompidas, escore de propensão, regressão em painel, análise multivariada, detecção de anomalias, árvores de decisão, modelos de Markov, custo-efetividade, análise de sensibilidade e modelagem atuarial (provisão de sinistros, modelos de sinistros, agregação de portfólio, modelos de tempo de vida) |
| **Modelos de relatório personalizados** | Envio de seus próprios modelos Markdown + CSS |
| **Compartilhamento de sessões** | Links ilimitados de compartilhamento (Gratuito: 1) |
| **Compartilhamento de relatórios** | Compartilhar relatórios com outros usuários |
| **Relatórios agendados** | Geração automática de relatórios em agenda diária/semanal/mensal |
| **Papéis em projetos** | Controle de acesso por papel dentro de projetos |
| **Feed de atividades** | Acompanhamento de atividades entre projetos |
| **Proveniência de artefatos** | Verificação da origem e do histórico de processamento das análises |
| **Tarefas de análise** | Atribuir análises como tarefas rastreáveis em projetos |

#### Max (inclui tudo do Pro)

| Recurso | O Que Você Obtém |
|---|---|
| **Exportação LaTeX** | Baixar relatórios como LaTeX (.tex ou ZIP com figuras, bibliografia BibTeX e código de análise vinculado) pronto para o Overleaf |
| **Histórico de versões** | Navegar e restaurar versões anteriores de um relatório |
| **Coautoria de relatórios** | Convidar coautores para colaborar em relatórios |
| **Envio para Overleaf** | Enviar relatórios diretamente para seus projetos no Overleaf |
| **Publicação no Zenodo** | Publicar relatórios no Zenodo com DOI |
| **Modelos públicos** | Publicar seus modelos de relatório para toda a comunidade |
| **Agente de manuscrito científico** | Redação de manuscritos assistida por IA, com seções de Métodos com qualidade de publicação, equações numeradas e código de análise vinculado |
| **Enriquecimento CRATE** | Enriquecer conjuntos de dados enviados com metadados CRATE |
| **Consulta à wiki** | Fazer perguntas e receber respostas sintetizadas da wiki da base |
| **Analisador/otimizador da base** | Ferramentas de análise e otimização da base de conhecimento |
| **Chaves de API** | Acesso programático à API REST do EpiDBot |
| **Agentes externos** | Registrar e consultar agentes de IA externos (ex.: nanobot) |
| **Gráficos avançados** | Visualizações raster e geoespaciais (renderização GeoTIFF) |
| **Escrita no Git** | Criar issues, comentar e abrir pull/merge requests |

#### Equipe (inclui tudo do Max)

O plano Equipe inclui todos os recursos do Max para toda a equipe, com limites de uso ilimitados (relatórios, links de compartilhamento, conjuntos de dados, relatórios agendados — veja a tabela acima), além destes recursos **exclusivos do plano Equipe**:

| Recurso | O Que Você Obtém |
|---|---|
| **Workspaces de equipe** | Workspaces compartilhados com recursos em pool |
| **Contexto de workspace (memória de equipe)** | Instruções compartilhadas, glossário e registro de decisões por projeto |
| **Incorporação em massa na base** | Incorporar muitos documentos à base de conhecimento em lote |
| **Comentários em relatórios** | Comentários/anotações em tópicos sobre relatórios |
| **Fluxo de revisão humana** | Revisão por pares estruturada de relatórios antes da publicação |
| **Atestado de verificação** | Atestado criptográfico da proveniência das análises |
| **Sala de crise de incidentes** | Coordenação de surtos: reivindicação de sinais e linhas do tempo compartilhadas |

!!! note "Dados essenciais permanecem gratuitos"
    Os sistemas brasileiros do DATASUS (SINAN, SIM, SINASC, SIH/SIA, CNES, PNI, CIHA) e os indicadores do Observatório Global de Saúde da OMS permanecem disponíveis em **todos os planos, incluindo o Gratuito**.

### Como o Controle de Recursos Funciona na Prática

- **No chat** — se você pedir algo que seu plano não inclui, o EpiDBot explica qual plano é necessário em vez de executar a ferramenta, e sugere fazer upgrade em **Configurações > Plano**
- **Na interface** — botões e cartões bloqueados exibem um selo de cadeado com o plano exigido (ex.: "PRO", "MAX") e um link para a página de upgrade
- **Administradores** contornam todas as restrições de recursos

### Expiração, Período de Carência e Grandfathering

- **Período de carência** — se seu plano pago expira, você mantém acesso completo aos recursos por **7 dias** (o mesmo período de carência da cota de tokens). Após isso, sua conta volta ao comportamento do plano Gratuito.
- **Grandfathering** — usuários que já tinham um plano pago quando o controle de recursos foi introduzido mantêm acesso aos recursos bloqueados por **90 dias**. Quem faz upgrade depois recebe os recursos do plano imediatamente, conforme a matriz acima.
- **Upgrades são imediatos** — assim que o pagamento é confirmado (PIX ou cartão de crédito), os recursos e cotas do novo plano valem na hora, e as novas exportações de PDF deixam de ter a marca d'água do plano Gratuito.
- **Planos que nunca expiram** — administradores podem fixar o plano de um usuário para que ele nunca expire (a data de validade é totalmente ignorada). Se seu plano não mostra data de renovação/validade mas permanece ativo, é por isso — fale com seu administrador em caso de dúvidas.

---

## Dicas e Boas Práticas

### Effective Prompting

EpiDBot works best when you are specific about what you want:

| Instead of | Try |
|---|---|
| "Show me data" | "Download SINAN dengue data for Sao Paulo in 2023 and show monthly case counts" |
| "Make a chart" | "Create a bar chart comparing dengue cases across Brazilian states in 2023" |
| "Analyze this" | "Run a temporal analysis of tuberculosis cases by month, broken down by age group" |

### Working with Datasets

- Start by **listing available datasets** to understand what data you can access
- Use **inspect dataset** to see column names and sample data before querying
- For large datasets, filter by year and region to keep queries manageable
- EpiDBot remembers downloaded data within a session — you do not need to re-download

### Analysis Workflow

1. **Explore** — list datasets, inspect schemas
2. **Download** — fetch the data you need
3. **Query** — ask specific questions about the data
4. **Visualize** — generate charts and maps
5. **Report** — compile findings into a PDF report

### Mid-stream Redirection

If EpiDBot is going in a direction you did not intend, simply type a new message while it is processing. The current analysis will be interrupted and a new turn begins.

### Organizando o Trabalho com Projetos

Para qualquer trabalho que abranja múltiplas sessões — um capítulo de dissertação, uma investigação de surto em andamento — crie um [projeto](#projetos) e adicione suas sessões, relatórios, gráficos e conjuntos de dados a ele conforme avança. Assim você pode compartilhar o espaço de trabalho inteiro com um colega em um único passo, em vez de compartilhar itens individualmente.

### Multi-language Analysis

You can ask questions in any language, and EpiDBot will respond accordingly. You can also mix languages within a session — for example, asking in Portuguese and requesting the output in English.

---

## Idiomas Suportados

EpiDBot supports five languages for both the interface and AI responses:

| Language | Interface | AI Responses |
|---|---|---|
| English | Yes | Yes |
| Portugues (Brasil) | Yes | Yes |
| Espanol | Yes | Yes |
| 简体中文 | Yes | Yes |
| العربية | Yes | Yes |

The interface language is set in **Settings > Language** and can also be auto-detected from your browser. The AI response language is set independently in the same section.

---

## Resolução de Problemas

### Problemas Comuns

| Issue | Solution |
|---|---|
| Chat not responding | Check your internet connection. A "Reconnecting..." banner indicates a WebSocket issue. |
| Plot images not loading | Reload the page. Plot paths may need to be regenerated after long idle periods. |
| "Quota Exceeded" message | You have used your daily token allowance. It resets daily — or upgrade your plan / use a consultation pack. |
| "Este recurso exige o plano Pro/Max/Equipe" | O recurso é exclusivo de um plano superior. Faça upgrade em **Configurações > Plano** — consulte [Planos de Assinatura e Recursos por Plano](#planos-de-assinatura-e-recursos-por-plano). |
| PDF com marca d'água "PLANO GRATUITO" | Marcas d'água se aplicam ao plano Gratuito. Faça upgrade para removê-la; exportações após o upgrade não têm marca d'água. |
| Data download is slow | Large datasets (e.g., national SINAN data) take time to download. Try filtering by state or year. |
| Sandbox execution fails | The sandbox container may be restarting. Retry after a few seconds. |
| External agent not responding | Verify the agent's URL is reachable from the internet, the Bearer token is correct, and the agent is running. Check that the URL does not resolve to a private IP (blocked by SSRF protection). |
| Language not changing | Clear your browser cookies and reload. The language is stored in the `NEXT_LOCALE` cookie. |
| "This message was not answered" | A previous message failed. Click **Retry** to resend it. |
| Email de confirmação do boletim não chega | Verifique sua caixa de spam. Sua assinatura permanece "Confirmação pendente" até você clicar no link do email. Cancele e assine novamente para reenviá-lo. |
| O código para no IDE após 30 segundos | A execução no navegador tem um limite de 30 segundos por design. Baixe o trecho e execute localmente para trabalhos mais longos. |
| Não consigo adicionar itens a um projeto compartilhado | Apenas proprietários e editores do projeto podem adicionar ou remover itens. Peça acesso de editor ao proprietário. |
| O plugin QGIS do EpiDBot mostra "Unauthorized" | Sua chave de API está ausente ou é inválida. Clique no botão **⚙** no painel do plugin e cole uma chave válida criada na interface web (**Configurações > Chaves de API**). |
| O plugin QGIS não consegue acessar o servidor | Verifique a **URL do Servidor** nas configurações do plugin (padrão: `https://api.epidbot.kwar-ai.com.br`) e sua configuração de rede/proxy. Falhas de rede transitórias são repetidas automaticamente. |

### Getting Help

If you encounter an issue not listed here:

1. Check the session history — your previous conversations are always accessible
2. Try starting a new session to isolate the problem
3. Contact the EpiDBot team via the GitHub repository

---

## Glossário

| Term | Definition |
|---|---|
| **DATASUS** | Brazilian Department of Informatics of the Unified Health System — the primary source of Brazilian public health data |
| **SINAN** | Sistema de Informacao de Agravos de Notificacao — Brazil's disease notification system |
| **Parquet** | A columnar storage file format used for efficient data querying |
| **DuckDB** | An in-process analytical database used by EpiDBot to query parquet files |
| **Token** | A unit of AI processing usage. Each message consumes tokens based on length and complexity. |
| **Session** | A conversation thread with EpiDBot. All messages and results are saved within a session. |
| **Knowledge Base** | A collection of embedded documents that EpiDBot can search for relevant information |
| **Dream** | EpiDBot's self-improvement system that analyzes conversations to discover and refine analysis skills |
| **Skill** | A reusable analysis pattern discovered by the Dream system, automatically applied when relevant |
| **Sandbox** | An isolated Docker container for executing Python and SQL code safely |
| **Catalog** | A metadata index of all downloaded datasets, their schemas, and row counts |
| **Raster** | A gridded geospatial data format (e.g., GeoTIFF) used for continuous surface maps |
| **IBGE** | Instituto Brasileiro de Geografia e Estatistica — Brazil's geography and statistics institute |
| **WHO GHO** | World Health Organization Global Health Observatory — a repository of health indicators |
| **ECDC** | European Centre for Disease Prevention and Control |
| **PAHO** | Pan American Health Organization |
| **GADM** | Database of Global Administrative Areas — provides boundary shapefiles |
| **QGIS** | Sistema de Informação Geográfica (SIG) livre e de código aberto. O plugin QGIS do EpiDBot permite conversar com o EpiDBot e mapear seus resultados dentro do QGIS |
| **GeoJSON** | Formato baseado em JSON para codificar feições geográficas como pontos e polígonos; o plugin QGIS pode transformar respostas GeoJSON em camadas de mapa |
| **PIX** | Brazilian instant payment system used for subscription payments |
| **Voice Input** | Browser-based speech recognition for entering messages by voice |
| **Lightbox** | Full-size image overlay for previewing plots at their natural resolution |
| **User Dataset** | A dataset uploaded by a user (CSV, Excel, GeoJSON, etc.), stored privately and queryable like public data |
| **Version History** | A timeline of saved report versions that can be browsed and restored |
| **Projeto** | Um espaço de trabalho que vincula sessões, relatórios, figuras e conjuntos de dados relacionados em torno de um tema comum, e pode ser compartilhado como um todo |
| **Pyodide** | Python compilado para WebAssembly — a tecnologia por trás do editor de código no navegador (IDE) |
| **Boletim (Newsletter)** | Email semanal bilíngue (PT/EN) com publicações, conjuntos de dados e notícias de saúde pública |
| **BibTeX** | Formato de arquivo de bibliografia usado pelo LaTeX; as exportações de relatórios incluem um arquivo references.bib |
| **Grafo de Conhecimento** | Rede de páginas de wiki, entidades e conceitos construída a partir das coleções da base de conhecimento, explorável na visão em Grafo |
| **External Agent** | An OpenClaw-compatible AI assistant (e.g. nanobot) registered by a user, which EpiDBot can send messages to and relay responses from |
| **OpenClaw** | An open agent runtime/platform whose agents can install and invoke "skills" — packaged capabilities described by a SKILL.md manifest |
| **nanobot** | A lightweight, open-source personal AI agent that exposes an OpenAI-compatible `/v1/chat/completions` endpoint for receiving messages |
| **Controle de Recursos (Feature Gate)** | Restrição baseada em plano que limita um recurso a um plano mínimo (Gratuito < Pro < Max < Equipe) |
| **Período de Carência** | Janela de 7 dias após a expiração de um plano pago durante a qual o acesso aos recursos é mantido |
| **Grandfathering** | Janela de 90 dias em que usuários pagantes existentes mantêm acesso a recursos que se tornaram bloqueados |

---

*EpiDBot is developed by Kwar-AI. For technical documentation, visit the [GitHub repository](https://github.com/Deeplearn-PeD/EpiDBot).*
