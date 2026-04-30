# 🚀 Projeto: Coleta e Estruturação de Dados de Empresas via API (CNPJ)

Este projeto foi desenvolvido com foco em **automação e análise de dados reais**, realizando a coleta de informações públicas de empresas brasileiras via API e estruturando esses dados para uso em análises e tomada de decisão.

A solução simula um cenário comum em ambientes corporativos:  
📊 necessidade de integrar dados externos, tratar inconsistências e gerar bases confiáveis para análise.

---

## 🎯 Objetivo

- Automatizar a coleta de dados públicos de empresas (CNPJ)  
- Garantir integridade e evitar duplicidade de registros  
- Estruturar dados para análise em Excel ou ferramentas de BI  
- Simular um pipeline de dados aplicável a cenários reais  

---

## 💡 Aplicação prática

Este tipo de solução pode ser aplicado em:

- Enriquecimento de bases de dados empresariais  
- Análise de fornecedores e parceiros  
- Apoio à tomada de decisão baseada em dados  
- Integração de dados externos em sistemas internos  

---

## ⚙️ Principais funcionalidades

- Integração com API pública de CNPJ  
- Tratamento e organização dos dados  
- Sistema de checkpoint para retomada de processamento  
- Controle de duplicidade automatizado  
- Exportação contínua para Excel  
- Monitoramento de progresso com `tqdm`  

---

## 🧠 Tecnologias utilizadas

- Python  
- Pandas  
- Requests  
- Openpyxl  
- Tqdm  

---

## 📂 Estrutura do projeto

```bash
├─ input_data/          # Arquivos de entrada (CNPJs)
├─ output_data/         # Arquivos de saída (Excel)
├─ data_origins/        # Dados brutos
├─ data_etl/            # Dados tratados
├─ data_finals/         # Dados finais
├─ scripts_python/      # Scripts principais
├─ scripts_ipynb/       # Exploração e testes
├─ checkpoint/          # Controle de processamento
├─ utils.py             # Funções auxiliares
├─ main.py              # Script principal
├─ requirements.txt     # Dependências
└─ README.md


⚙️ Instalação
git clone https://github.com/rafaeldataanalytics/api_gov_empresa_lucro_real.git
cd api_gov_empresa_lucro_real
pip install -r requirements.txt


▶️ Como usar
Adicione os CNPJs no arquivo:
input_data/cnpj_limpos.csv


O arquivo deve conter colunas como: Ano e Cnpj

Execute o projeto:
python main.py

🔄 Fluxo de processamento
Leitura dos CNPJs do CSV
Verificação de registros já processados
Remoção de duplicidades
Consulta dos dados via API
Salvamento progressivo em Excel
Atualização de checkpoint
Limpeza periódica de duplicados
Finalização com base consolidada





⚙️ Lógica principal

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



📊 Diferenciais do projeto
Trabalha com dados reais (API pública)
Simula um pipeline de dados completo
Implementa controle de execução com checkpoint
Pensado para cenários de grande volume de dados
Estruturado para fácil adaptação em ambientes corporativos

📈 Possíveis evoluções
Integração com banco de dados (PostgreSQL)
Criação de dashboards no Power BI
Deploy como API (FastAPI / Flask)
Aplicação em cenários industriais (ex: análise de fornecedores, contratos e performance)

📌 Contato
GitHub: https://github.com/rafaeldataanalytics
LinkedIn: https://www.linkedin.com/in/rafael-da-silva-rfs/
Email: rafael.data.analytics@gmail.com

📝 Licença

MIT License © Rafael Silva
