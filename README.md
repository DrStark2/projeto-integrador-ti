# Automação de Inventário de Hardware para TI

Este projeto foi desenvolvido como parte do **Projeto Integrador** do curso de **Ciência de Dados**. O objetivo é demonstrar a integração entre automação de suporte técnico e estruturação de dados.

## 🚀 Objetivo
O script coleta metadados essenciais de hardware (CPU, RAM, Disco) e exporta para um formato `.csv`, facilitando a ingestão desses dados em ferramentas de BI, como Power BI ou SQL.

## 🛠️ Tecnologias Utilizadas
- **Python 3.x**
- **Pandas**: Para estruturação e exportação de dados.
- **Psutil**: Para interface direta com as métricas do sistema.

## 📊 Como o projeto funciona?
O script identifica as especificações da máquina atual e gera um arquivo chamado `inventario_hardware.csv` pronto para análise.
---
## 🛠️ Instalação e Execução
Para reproduzir este projeto e gerar seus próprios dados de inventário, instale as bibliotecas necessárias utilizando o comando abaixo:

```bash
pip install pandas psutil
