

# 🚀 Projeto: Análise de CNPJs via API Pública

[![Python](https://img.shields.io/badge/python-3.9+-blue)](https://www.python.org/) 
[![License: MIT](https://img.shields.io/badge/License-MIT-green)](https://opensource.org/licenses/MIT) 
[![GitHub issues](https://img.shields.io/github/issues/rafaeldataanalytics/analise-cnpjs)](https://github.com/rafaeldataanalytics/analise-cnpjs/issues)
[![Build Status](https://img.shields.io/github/actions/workflow/status/rafaeldataanalytics/analise-cnpjs/python-app.yml)](https://github.com/rafaeldataanalytics/analise-cnpjs/actions)

Este projeto automatiza a consulta de CNPJs utilizando a API `publica.cnpj.ws`, salvando os dados em planilhas Excel com verificação de duplicatas. Ideal para análises de dados de empresas brasileiras.

---

## 🎯 Objetivo

- Automatizar a coleta de dados públicos de CNPJs  
- Evitar duplicidade de informações  
- Facilitar análises e relatórios em Excel  

---

## ⚙️ Requisitos

- Python 3.9+  
- Instale as dependências:
```bash
pip install -r requirements.txt


## Requisitos

- Python 3.9+
- `pip install -r requirements.txt`

## Como usar

1. Coloque seus CNPJs em `input_data/cnpj_limpos.csv`
2. Execute:
   ```bash
   python main.py
   ```

## Funcionalidades

- Consulta dados públicos por CNPJ
- Registro de erros
- Checkpoint automático
- Remove duplicatas a cada 150 registros

``` text
- api_gov_empresa_lucro_real/
│
├─ api_gov_empresa_lucro_real/
├─ atributtes/
├─ checkpoint/
├─ data_etl/
├─ data_finals/
├─ data_origins/
├─ ignore_license/
├─ input_data/
├─ output_data/
├─ requirements/
├─ scripts_ipynb/
├─ scripts_python/
├─ temps_project/
└─ README.md
```

# Siga passos abaixo: 


📊 Localizar Dados de Empresas Lucro Real

Automatiza a consulta de CNPJs de empresas do regime Lucro Real, salvando resultados em Excel, evitando duplicatas e permitindo retomar o processamento com checkpoints.

Ideal para Back-end e Análise de Dados com Python.

🚀 Funcionalidades

✅ Consulta de CNPJs de empresas do Lucro Real

✅ Salva resultados em Excel automaticamente

✅ Remove duplicatas a cada 150 registros

✅ Retoma de onde parou com checkpoint

✅ Barra de progresso visual com tqdm

✅ Pausa entre consultas para respeitar limites de API

🗂 Estrutura do Projeto
Pasta / Arquivo	Descrição
input_data/	Arquivos de entrada (CNPJs)
input_data/cnpj_limpos.csv	Lista de CNPJs a consultar
output_data/	Arquivos de saída (Excel)
output_data/resultado_consulta.xlsx	Resultados das consultas
utils.py	Funções auxiliares: ler, salvar, consultar, remover duplicatas
checkpoint.txt	Armazena último CNPJ processado
main.py	Script principal do projeto
⚙️ Instalação
git clone https://github.com/RafaelDataAnalytics/Localizar-CNPJs-Lucro-Real.git
cd Localizar-CNPJs-Lucro-Real
pip install -r requirements.txt


Requisitos: Python 3.x, pandas, tqdm, openpyxl

📝 Como Funciona
1️⃣ Preparação

Ler os CNPJs do CSV

Obs: Csv tem duas colunas Ano e Cnpj

Ler CNPJs já processados no Excel

Carregar o checkpoint, se existir

2️⃣ Filtragem

Remove duplicados

Cria lista de CNPJs novos a processar

3️⃣ Consulta e Salva

Consulta cada CNPJ via função consultar_cnpj()

Salva resultados em Excel a cada 5 registros

Atualiza checkpoint

Remove duplicatas a cada 150 registros

Pausa de 21 segundos entre consultas

4️⃣ Finalização

Termina quando todos os CNPJs forem processados

Excel final contém todos os resultados sem duplicatas

🔄 Fluxo de Processamento
flowchart TD
    A[📄 CSV de entrada] --> B[🔍 Filtra CNPJs já processados]
    B --> C[🌐 Consulta CNPJs via API/Base]
    C --> D[💾 Armazena resultados temporários]
    D --> E[📊 Salva em Excel a cada 5 registros]
    E --> F[⏱ Atualiza checkpoint]
    F --> G[🧹 Remove duplicatas a cada 150 registros]
    G --> H[✅ Fim quando todos os CNPJs forem processados]

💻 Trecho de Código Principal
for i, cnpj in enumerate(tqdm(novos_cnpjs, desc="Consultando CNPJs", unit="cnpj"), 1):
    dados = consultar_cnpj(cnpj)
    resultados.append(dados)
    salvar_checkpoint(cnpj)
    contador_para_remover += 1

    if i % 5 == 0 or i == len(novos_cnpjs):
        salvar_excel(resultados, ARQUIVO_SAIDA)
        resultados = []

    if contador_para_remover >= 150:
        remover_duplicatas_final(ARQUIVO_SAIDA)
        contador_para_remover = 0

    time.sleep(21)

🎯 Dicas de Uso

Sempre mantenha o checkpoint.txt para retomar grandes consultas

Ajuste time.sleep() de acordo com limites da API

Teste com listas pequenas antes de processar grandes volumes

Excel é atualizado continuamente para evitar perda de dados

📈 Visual do Projeto
Antes	Depois
CSV de entrada	Excel final limpo
🟡 Lista de CNPJs	✅ Resultados completos
Sem checkpoint	Checkpoint permite retomar
📌 Contato / Portfólio

GitHub: RafaelDataAnalytics - https://github.com/rafaeldataanalytics

LinkedIn: Rafael Silva

Email: rafae.data.analytics@gmail.com

📝 Licença

MIT License © Rafael Silva


