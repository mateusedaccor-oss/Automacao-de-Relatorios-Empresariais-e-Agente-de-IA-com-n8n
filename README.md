# 🚀 Enterprise Data Automation & AI Agent Ecosystem (n8n)

Uma solução completa de automação de processos de negócios e integração de sistemas desenvolvida na plataforma **n8n**. O ecossistema resolve gargalos reais de reporte financeiro, unificação de dados de CRM/Legacy Data Warehouses e atendimento inteligente via IA.

---

## 📊 Arquitetura das Soluções

O projeto é dividido em fluxos lógicos complementares:

### 1. Fluxo Principal de Processamento de Vendas (`Nathan's workflow`)
* **Gatilho:** Execução agendada (`Cron` semanal às segundas 9h) ou acionamento manual.
* **Coleta & Filtragem:** Consumo de APIs REST de Data Warehouse legado e roteamento condicional com base no status do pedido (`Booked` vs `Processing`).
* **Tratamento de Dados:** Cálculo consolidado de vendas confirmadas e preparação de lista de pendências para acompanhamento da equipe comercial.
* **Notificação:** Envio automático de relatórios consolidados diretamente em canais do **Discord**.

---

### 2. Agente de Atendimento Inteligente com IA (`Customer Service Agent`)
* **Engine:** Agente autônomo baseado em LLM (OpenAI Chat Model).
* **Memory & Tools:** Sistema com memória de curto prazo (`Simple Memory`) integrado a ferramentas personalizadas (`GetCustomers` e `GetOrderData`).
* **Capacidade:** Responde a consultas complexas em linguagem natural (ex: *"Qual a região do cliente com ID 10?"*), consultando dinamicamente endpoints externos em tempo real.

---

### 3. Consolidação e Geração de Relatórios Avançados (`Generating Reports` & `Merging Data`)
* **Merge de Dados:** Unificação de dados dispersos de clientes, regiões e ordens de compra provenientes de múltiplas fontes.
* **Transformação & Exportação:** Agrupamento por região, ordenação por faturamento, conversão para formato CSV e upload automático em repositório web.

---

### 4. Gestão de Resiliência e Monitoramento de Erros (`Monitor Report Errors`)
* **Error Handling:** Captura proativa de falhas via `Error Trigger`.
* **Alertas de Sistema:** Formatação e envio imediato da mensagem de erro tratada para os desenvolvedores via Discord.

---

## 🛠️ Tecnologias e Ferramentas Utilizadas

* **Workflow Engine:** n8n (Self-hosted)
* **Inteligência Artificial:** OpenAI API (LLMs), AI Agent, Memory, Custom Tools
* **Integrações & APIs:** REST APIs, HTTP Requests, Discord Webhooks
* **Lógica & Manipulação de Dados:** JavaScript (Data Transformation / Code Nodes), JSON Parsing, CSV Generation

---

## ⚙️ Como Executar o Projeto

1. Certifique-se de ter o **n8n** instalado localmente ou via Docker:
   ```bash
   n8n start
