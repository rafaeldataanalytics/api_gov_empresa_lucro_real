# Análise de CNPJs via API Pública

Este projeto automatiza a consulta de CNPJs utilizando a API `publica.cnpj.ws`, salvando os dados em planilhas Excel com verificação de duplicatas.

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


