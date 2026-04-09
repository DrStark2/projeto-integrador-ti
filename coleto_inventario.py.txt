import psutil
import platform
import pandas as pd
from datetime import datetime

def coletar_dados_sistema():
    print("Coletando informações de hardware...")
    
    dados = {
        "Data_Coleta": [datetime.now().strftime("%d/%m/%Y %H:%M:%S")],
        "Hostname": [platform.node()],
        "SO": [f"{platform.system()} {platform.release()}"],
        "Processador": [platform.processor()],
        "RAM_Total_GB": [round(psutil.virtual_memory().total / (1024**3), 2)],
        "RAM_Uso_Percent": [psutil.virtual_memory().percent],
        "Disco_Total_GB": [round(psutil.disk_usage('/').total / (1024**3), 2)],
        "Disco_Livre_GB": [round(psutil.disk_usage('/').free / (1024**3), 2)]
    }
    return pd.DataFrame(dados)

if __name__ == "__main__":
    df = coletar_dados_sistema()
    
    # Salva o arquivo CSV
    nome_arquivo = "inventario_hardware.csv"
    df.to_csv(nome_arquivo, index=False, encoding='utf-8')
    
    print("-" * 30)
    print(f"Relatório gerado: {nome_arquivo}")
    print(df.head())
    print("-" * 30)