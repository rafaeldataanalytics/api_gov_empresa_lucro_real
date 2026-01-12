

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
## Licença

MIT - Livre para uso e modificação.


