# 📊 Pipeline de Cotações Cambiais com Python + LLM (Google Colab)

Projeto desenvolvido no **MBA Data Engineering - Projeto Final**, com objetivo de criar um **pipeline de ingestão, transformação, carga e análise de cotações cambiais**, enriquecido com **insights automáticos gerados via LLM (Google Gemini/OpenAI)**.

Autor: **Gabriel Morais Simonini Sussmann**  
Versão: **2.0 - com configuração automática do `.env`**

---

## 🚀 Funcionalidades

- **Ingestão** de cotações cambiais em tempo real via **ExchangeRate API**  
- **Transformação** e validação dos dados em múltiplas camadas:  
  - **RAW** (JSON)  
  - **SILVER** (CSV)  
  - **GOLD** (Parquet otimizado)  
- **Análise inteligente** com geração de insights automáticos (LLM via API Google/OpenAI)  
- **Visualizações interativas** com Plotly (gráficos de barras, pizza e estatísticas resumidas)  
- **Configuração automática do arquivo `.env`** (com atualização de chaves diretamente do script)  

---

## 📂 Estrutura de Pastas

```
/content/currency_data/
│── raw/     # Dados brutos (JSON)
│── silver/  # Dados processados (CSV)
│── gold/    # Dados finais (Parquet + insights)
.env         # Arquivo de configuração de APIs
```

---

## 🔑 Configuração

As chaves de API são configuradas automaticamente no arquivo `.env`.  

- **ExchangeRate API** → [Obter chave gratuita](https://www.exchangerate-api.com/)  
- **Google Gemini API** (opcional, para insights avançados) → [Documentação](https://ai.google.dev/)  

### Comandos úteis
```python
show_env_status()              # Mostra status atual das chaves
update_exchange_key('nova')    # Atualiza a chave ExchangeRate
update_openai_key('nova')      # Atualiza a chave OpenAI
```

---

## ⚙️ Instalação de Dependências

Execute no Google Colab:

```bash
!pip install -q requests pandas pyarrow openai python-dotenv plotly
```

---

## ▶️ Como Executar

No Google Colab, basta rodar a função principal:

```python
main()
```

O pipeline executa automaticamente todas as etapas:

1. **Ingestão** → Coleta cotações da API  
2. **Transformação** → Normaliza e valida os dados  
3. **Carga** → Salva em formato otimizado (Parquet)  
4. **Insights** → Gera análise executiva com LLM (ou fallback básico)  
5. **Visualizações** → Exibe gráficos e estatísticas  

---

## 📊 Exemplo de Saída

### Resumo Estatístico
```
target_currency   Taxa    Posição
GBP               0.7387  7
CHF               0.7984  4
EUR               0.8542  6
CAD               1.3859  3
AUD               1.5116  1
BRL               5.4311  2
CNY               7.1216  5
JPY             147.3705  8
```

### Insights Automáticos (LLM)
- Resumo executivo do cenário cambial  
- Impactos para empresas brasileiras (importadores/exportadores)  
- Recomendações táticas (hedge, precificação, cadeias de suprimento)  
- Alertas importantes (volatilidade, inflação, competitividade)  

---

## 🛠 Tecnologias Utilizadas

- **Python 3.x**  
- **Google Colab**  
- **Requests** – Coleta de dados via API  
- **Pandas & PyArrow** – Processamento e carga de dados  
- **Plotly** – Visualizações interativas  
- **dotenv** – Gerenciamento de variáveis de ambiente  
- **LLM (Google Gemini / OpenAI)** – Geração de insights executivos  

---

## 📌 Observações

- O projeto foi desenvolvido para rodar em **Google Colab**, mas pode ser adaptado para execução local.  
- Caso a API de LLM não esteja configurada, o pipeline gera **insights básicos automaticamente**.  
- Estrutura modular, permitindo expansão para novas moedas, fontes de dados ou integrações.  

---

🔹 **Execução rápida:**  
👉 Configure suas chaves no `.env` e rode `main()` para processar os dados e gerar os insights.  
