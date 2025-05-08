# fiap_ia_2025_f_3_cap_1_Enterprise_Challenge_Reply

# Projeto Plataforma SaaS de Manutenção Preditiva Industrial com IA na AWS

Este projeto descreve o design e a implementação de uma plataforma SaaS (Software-as-a-Service) multi-tenant para manutenção preditiva industrial, utilizando Inteligência Artificial (IA) e Machine Learning (ML) em dados coletados em tempo real por sensores IoT. A solução visa prever falhas em equipamentos, otimizar cronogramas de manutenção e reduzir custos operacionais para clientes industriais.

Este README foi gerado com base no documento "Entrega 1 Design Fundamental - Metodologia, Tecnologias e Conceito de Pipeline.pdf".

## 1. Introdução

A indústria moderna enfrenta desafios significativos com a manutenção de equipamentos críticos, onde falhas inesperadas resultam em paradas não planejadas, perdas de produtividade e aumento de custos. As abordagens tradicionais de manutenção reativa e preventiva frequentemente se mostram ineficientes. Este projeto propõe uma solução de Manutenção Preditiva (PdM) baseada em IA e ML para superar essas limitações.

**Objetivo Principal:** Desenvolver uma plataforma SaaS que utilize dados de sensores em tempo real para prever potenciais falhas em equipamentos industriais, otimizar a manutenção, reduzir o tempo de inatividade e prolongar a vida útil dos ativos.

## 2. Contexto do Projeto

Este projeto é desenvolvido no âmbito do curso de graduação em Inteligência Artificial da FIAP, em resposta a um desafio ("Enterprise Challenge - Sprint 1 - Reply") que simula o desenvolvimento desta plataforma pela Hermes Reply, uma empresa especializada em soluções para a Indústria 4.0.

## 3. Solução Proposta

Uma plataforma SaaS multi-tenant de Manutenção Preditiva que integra:
* Coleta de dados de sensores IoT (ESP32).
* Processamento e armazenamento em nuvem (AWS).
* Modelos avançados de IA/ML para análise preditiva (estimativa de Vida Útil Remanescente - RUL e classificação de falhas).
* Dashboards interativos para visualização de dados e alertas.
* Alertas automatizados sobre falhas iminentes.

## 4. Metodologia Adotada

O projeto utiliza a metodologia **CRISP-DM** (Cross-Industry Standard Process for Data Mining), um processo iterativo composto pelas seguintes fases:
1.  **Business Understanding** (Entendimento do Negócio)
2.  **Data Understanding** (Entendimento dos Dados)
3.  **Data Preparation** (Preparação dos Dados)
4.  **Modeling** (Modelagem)
5.  **Evaluation** (Avaliação)
6.  **Deployment** (Implantação)

## 5. Stack Tecnológico Principal

| Categoria             | Tecnologia Escolhida          | Justificativa                                                                                                |
| :-------------------- | :---------------------------- | :----------------------------------------------------------------------------------------------------------- |
| Linguagem             | Python 3.x                    | Amplo ecossistema de bibliotecas para dados/ML, forte suporte comunitário, integração com AWS.                 |
| Análise de Dados      | Pandas, NumPy, Matplotlib/Seaborn | Padrão da indústria para manipulação, computação numérica e visualização.                                     |
| Banco de Dados        | PostgreSQL (AWS RDS)          | Banco de dados relacional robusto, suporte a SQL, particionamento avançado.                                  |
| Plataforma de Nuvem   | AWS (Amazon Web Services)     | Serviços abrangentes para IoT, dados, ML, serverless; escalabilidade e confiabilidade.                         |
| Machine Learning    | Scikit-learn, TensorFlow/Keras | Scikit-learn para baselines/pré-processamento; TF/Keras para Deep Learning (LSTMs).                             |
| Hardware IoT          | ESP32                         | Microcontrolador de baixo custo com Wi-Fi/Bluetooth integrados, adequado para coleta de dados.                 |

## 6. Design do Pipeline de Dados

O projeto contempla uma evolução desde um MVP local até a arquitetura final na nuvem AWS.

**6.1. Pipeline do MVP Local (Conceitual):**
ESP32 (Sensores) -> Máquina Local (Script Python) -> Banco de Dados SQL Local (PostgreSQL) -> Modelo ML Local (Scikit-learn/TF) -> Saída (Log/Console).

**6.2. Pipeline Alvo na Nuvem (Conceitual):**
ESP32 (Sensores via MQTT) -> AWS IoT Core -> IoT Rule -> Lambda/Kinesis -> Lambda/Glue (ETL) -> RDS (Estruturado) / S3 (Bruto/Processado) -> SageMaker (Treinamento/Avaliação/Deploy) -> API Gateway -> Dashboards (QuickSight/Grafana) & Alertas (CloudWatch/SNS).

## 7. Estrutura do Projeto e Entregas (Challenge)

O desenvolvimento está organizado em quatro entregas principais, alinhadas com as fases do CRISP-DM:

* **Entrega 1: Design Fundamental**
    * **Atividades:** Definição do problema, pesquisa de tecnologias, design inicial da arquitetura, seleção da metodologia, cronograma, análise de riscos.
    * **Foco CRISP-DM:** Business Understanding, Data Understanding (inicial).
* **Entrega 2: Aquisição e Preparação de Dados**
    * **Atividades:** Montagem do circuito ESP32, desenvolvimento do código de coleta de dados, ingestão inicial (local), definição de User Stories, limpeza de dados e EDA.
    * **Foco CRISP-DM:** Data Understanding, Data Preparation.
* **Entrega 3: Armazenamento e Estrutura de Dados**
    * **Atividades:** Modelagem do banco de dados, implementação do schema, desenvolvimento de scripts para carga de dados, refinamento da estratégia de particionamento e multi-tenancy.
    * **Foco CRISP-DM:** Data Preparation.
* **Entrega 4: Implementação na Nuvem, Integração de IA e Implantação do MVP**
    * **Atividades:** Implementação da arquitetura AWS completa, treinamento e avaliação dos modelos de ML no SageMaker, implantação do modelo, desenvolvimento do dashboard, configuração de logs/alertas, geração de relatórios inteligentes, finalização do MVP e documentação.
    * **Foco CRISP-DM:** Modeling, Evaluation, Deployment.

## 8. Análise de Pontos Fortes e Riscos

**Pontos Fortes:**
* Expertise relevante da equipe (simulada pela Hermes Reply).
* Utilização de tecnologias padrão de mercado (Python, AWS).
* Alto potencial de impacto da manutenção preditiva.
* Escalabilidade do modelo SaaS.
* Riqueza de dados provenientes de múltiplos sensores.

**Principais Riscos e Estratégias de Mitigação:**
* **Qualidade dos Dados dos Sensores:** Validação rigorosa, limpeza de dados, monitoramento dos sensores.
* **Precisão e Generalização do Modelo ML:** Avaliação rigorosa, ajuste de hiperparâmetros, MLOps.
* **Complexidade da Arquitetura Multi-Tenant na Nuvem:** Planejamento cuidadoso, IaC, testes extensivos, AWS Well-Architected Framework (SaaS Lens).
* **Segurança (IoT, Nuvem, Dados):** Melhores práticas de segurança AWS (IAM, VPC, criptografia), proteção de dispositivos IoT.
* **Conformidade com LGPD:** Estratégia clara de conformidade, gestão de direitos, segurança, definição de papéis.

## 9. Plano de Desenvolvimento e Divisão de Responsabilidades

A coordenação de cada entrega do projeto foi definida da seguinte forma:

| Entrega                                                               | Coordenador | RM     | Contribuição |
| :-------------------------------------------------------------------- | :---------- | :----- | :----------- |
| 1. Design Fundamental - Metodologia, Tecnologias e Conceito de Pipeline | Omar        | 561375 | TODOS        |
| 2. Aquisição e Preparação de Dados                                  | Paulo       | 564262 | TODOS        |
| 3. Armazenamento e Estrutura de Dados                                 | Deivisson   | 565095 | TODOS        |
| 4. Implementação na Nuvem, Integração de IA e Implantação do MVP      | Renan       | 566175 | TODOS        |

*(Tabela baseada na seção 2.6 do documento fornecido)*

## 10. Detalhes das Entregas Futuras (Resumido)

* **Entrega 2 - Aquisição e Preparação de Dados:** Foco na integração dos sensores ESP32 (MPU6050, DHT22, Sensor de Gás MQ-XXX, PIR, LDR), código de coleta (MicroPython/Arduino), limpeza de dados, Análise Exploratória de Dados (EDA) e criação de User Stories detalhadas para guiar o desenvolvimento das funcionalidades da plataforma.
* **Entrega 3 - Armazenamento e Estrutura de Dados:** Abrange a modelagem do banco de dados (Conceitual, Lógico e Físico usando Oracle SQL Developer Data Modeler), com atenção especial ao tratamento de dados de séries temporais através de particionamento (Range ou Interval Partitioning no PostgreSQL) e à estratégia de isolamento de dados multi-tenancy (modelo Pool com TenantID para o MVP).
* **Entrega 4 - Implementação na Nuvem, IA e MVP:** Detalha a arquitetura completa na AWS (IoT Core, Kinesis/Lambda, S3, RDS, SageMaker, API Gateway, QuickSight, CloudWatch), a implementação dos modelos de IA/ML (LSTM para RUL, Random Forest para classificação de falhas, engenharia de features, tratamento de dados desbalanceados, pipeline SageMaker, MLOps com MLflow), a estratégia de implantação dos modelos (SageMaker Multi-Model Endpoints - MME), o desenvolvimento do dashboard, a configuração de logging e alertas, e a geração de relatórios inteligentes.

## 11. Segurança e Conformidade

* **LGPD (Brasil):** Aderência aos princípios da LGPD, definição de bases legais, papéis de controlador (cliente) e processador (Hermes Reply), Contratos de Tratamento de Dados (DPAs), gestão dos direitos dos titulares, e atenção às decisões automatizadas por IA/ML.
* **Melhores Práticas de Segurança na AWS:** Utilização de IAM com princípio do menor privilégio, segurança de dados em S3 e RDS (isolamento, criptografia), segurança de rede com VPC (sub-redes privadas/públicas, Security Groups, NACLs, VPC Endpoints), criptografia em repouso e em trânsito, segurança em SageMaker, e logging/monitoramento com CloudTrail, GuardDuty, Security Hub e CloudWatch.
* **Frameworks Relevantes:** Consideração de frameworks como ISO/IEC 27001, NIST Cybersecurity Framework (CSF), SOC 2, e o AWS Well-Architected Framework (SaaS Lens) para uma postura de segurança robusta.

## 12. Conclusão e Próximos Passos

O projeto estabelece uma base sólida para uma plataforma SaaS de manutenção preditiva. O MVP funcional demonstrará os principais aspectos da solução. Melhorias futuras podem incluir modelagem ML mais avançada, integração com CMMS, edge computing, análise de causa raiz aprimorada, e personalização avançada por tenant.

## Como Usar este Repositório

*(Esta seção normalmente conteria instruções sobre como clonar, configurar o ambiente, rodar o projeto, etc. Como o documento foca no design, esta seção pode ser adaptada conforme o código real do projeto for desenvolvido).*

* **Documentação:** A principal documentação de design e planejamento encontra-se no arquivo `Entrega 1 Design Fundamental - Metodologia, Tecnologias e Conceito de Pipeline.pdf` e nos documentos subsequentes de cada entrega.
* **Código Fonte:** O código-fonte do projeto (scripts Python, configurações IaC, notebooks SageMaker, código ESP32, etc.) estará organizado em suas respectivas pastas.
* **Acesso ao Protótipo:** (Se aplicável, fornecer link e credenciais de acesso ao protótipo SaaS implantado).

## Contribuições

Este é um projeto acadêmico desenvolvido pelo Grupo 83. Para contribuições ou dúvidas, por favor, entre em contato com os membros do grupo.

*(Os nomes dos membros do grupo podem ser listados aqui se desejado, baseando-se na seção de divisão de responsabilidades)*
* Omar Cali Abido Mustafá Assem (Coordenador Entrega 1)
* Paulo (Coordenador Entrega 2)
* Deivisson (Coordenador Entrega 3)
* Renan (Coordenador Entrega 4)
