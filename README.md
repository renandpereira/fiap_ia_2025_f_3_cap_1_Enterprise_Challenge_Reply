

# 📦 Projeto SaaS de Manutenção Preditiva Industrial com IA na AWS

## 🧠 Descrição Geral

Este projeto propõe o design e desenvolvimento de uma plataforma SaaS (multi-tenant) para manutenção preditiva industrial, utilizando sensores IoT e algoritmos de Inteligência Artificial (IA) e Machine Learning (ML). A proposta prevê a coleta de dados em tempo real, análise preditiva, alertas inteligentes e visualizações interativas.

## 🎯 Objetivo

Prever falhas em equipamentos industriais, reduzir custos com manutenção corretiva, otimizar cronogramas preventivos e aumentar a eficiência operacional.

## 🧱 Contexto do Projeto

Desenvolvido como parte do curso de IA da FIAP, em parceria com a Hermes Reply no desafio "Enterprise Challenge". A Hermes Reply é especializada em soluções de Indústria 4.0 com foco em IoT, IA, automação e transformação digital.

## 💡 Solução Proposta

- Coleta de dados com ESP32 e sensores industriais.
- Armazenamento em nuvem via AWS (IoT Core, RDS, S3).
- Modelos de ML para previsão de falhas (Random Forest, LSTM).
- Dashboards interativos e alertas automatizados (SNS/WhatsApp).
- Arquitetura multi-tenant e escalável.

## 🧩 Metodologia Adotada

Base: **CRISP-DM** com abordagem iterativa:

- ✅ Business Understanding  
- ✅ Data Understanding  
- ✅ Data Preparation (limpeza, features)  
- ✅ Modeling (RF, LSTM, tuning)  
- ✅ Evaluation (F1, RUL score)  
- 🔜 Deployment (MVP local → cloud)

## 🧰 Stack Tecnológico

| Categoria             | Tecnologia                   | Justificativa |
|-----------------------|------------------------------|----------------|
| Linguagem             | Python 3.x                   | Robustez e comunidade ampla |
| Análise de Dados      | Pandas, NumPy, Seaborn       | EDA e manipulação numérica |
| Banco de Dados        | PostgreSQL (AWS RDS)         | Relacional, suporte multi-tenant |
| Nuvem                 | AWS (IoT, Lambda, RDS, S3)   | Escalável e segura |
| ML/IA                 | Scikit-learn, TensorFlow     | Modelos tradicionais e deep learning |
| Visualização          | QuickSight, Grafana          | Dashboards e relatórios |
| Hardware IoT          | ESP32 + Sensores             | Custo-benefício e flexibilidade |

## 🔄 Pipeline de Dados

| Etapa               | Descrição |
|---------------------|-----------|
| **Coleta**          | ESP32 envia dados via MQTT |
| **Ingestão**        | AWS IoT Core aplica regras |
| **Processamento**   | ETL via Lambda/Glue |
| **Armazenamento**   | S3 (bruto), PostgreSQL (estruturado) |
| **Modelagem ML**    | SageMaker executa Random Forest e LSTM |
| **Visualização**    | Dashboards com KPIs e alertas |
| **Notificações**    | Envio automático via SNS / WhatsApp |

## 📊 Estratégia de Coleta de Dados

- **Dispositivo:** ESP32 com sensores (MPU6050, DHT22, MQ-x, LDR)  
- **Protocolo:** MQTT via Wi-Fi  
- **Frequência:** 10s (ajustável)  
- **Simulação:** Scripts Python para dados artificiais realistas

## 🧠 Modelos de Machine Learning

| Tipo                    | Modelo         | Métricas |
|-------------------------|----------------|----------|
| Classificação de falhas | Random Forest  | F1, Precision, Recall, ROC AUC |
| Regressão (RUL)         | LSTM           | RMSE, MAE, R², PH |

## 🧪 Estratégia de Treinamento ML

- Features: Rolling mean, FFT, tendências  
- Balanceamento: SMOTE  
- Avaliação: Cross-validation + hold-out  
- Versionamento: MLflow + SageMaker Registry

## 👥 Plano de Desenvolvimento


| Entrega                                                               | Coordenador | RM     | Contribuição |
| :-------------------------------------------------------------------- | :---------- | :----- | :----------- |
| 1. Design Fundamental - Metodologia, Tecnologias e Conceito de Pipeline | Omar        | 561375 | TODOS        |
| 2. Aquisição e Preparação de Dados                                  | Paulo       | 564262 | TODOS        |
| 3. Armazenamento e Estrutura de Dados                                 | Deivisson   | 565095 | TODOS        |
| 4. Implementação na Nuvem, Integração de IA e Implantação do MVP      | Renan       | 566175 | TODOS        |

## ✨ Diferenciais da Solução

- 🔮 Previsão com Vida Útil Remanescente (RUL)  
- 💬 Alertas automatizados  
- 📊 Dashboard inteligente com prioridades   
- 🔁 Benchmark e replicabilidade  
- ☁️ Totalmente escalável em nuvem AWS

## 🔐 Segurança e LGPD

- Criptografia em trânsito e repouso (IoT e dados)  
- Controle de acesso (IAM, VPC, Roles)  
- Isolamento por TenantID (PostgreSQL + RLS)  
- Aderência à LGPD (dados pessoais e sensíveis)

## 👨‍💻 Colaboradores

- **Omar** – Coordenação Técnica  
- **Paulo** – Aquisição de Dados  
- **Deivisson** – Banco de Dados e Multi-tenant  
- **Renan** – Arquitetura AWS e ML

## 📌 Conclusão

A proposta apresenta uma solução viável, escalável e inovadora para a manutenção preditiva industrial, com base em tecnologias modernas e práticas de arquitetura em nuvem. O próximo passo será a implementação completa do MVP utilizando dados reais dos sensores.

---

**Grupo 81 | FIAP IA 2025 | Desafio Hermes Reply**
