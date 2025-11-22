# Assistente Clínica Veterinária
Objetivo: Assistente de Clínica Veterinária com conhecimento sobre os serviços agendados e base de clientes com histórico de gastos.

## 📌  Visão Geral
O que é o assistente é capaz de fazer?
* Consultar como está agenda de serviços marcados;
* Consultar base de clientes com histórico de gastos;

## 🧩 Problema
Clínica Veterinária de bairro que não possui um sistema de consulta ágil de serviços e contabilidade. 

## ⚙️ Solução
Agente inteligente que consulta base de dados de clientes e agenda de serviços marcados.

## 🤖 Agente 
  
### Tela 01
- O que o assistente pode fazer para ajudar?
<img width="840" height="688" alt="Captura de Tela 2025-11-21 às 19 10 29" src="https://github.com/user-attachments/assets/7e989125-f3e0-49eb-b88d-42907daec73c" />

### Tela 02
- Consulta sobre os agendamentos para os próximos dias
<img width="1199" height="663" alt="Captura de Tela 2025-11-21 às 19 15 28" src="https://github.com/user-attachments/assets/f4204632-ca49-4bed-b31c-be98cb56b965" />

### Tela 03
- Consulta sobre histórico de gastos de um cliente em específico
<img width="833" height="708" alt="Captura de Tela 2025-11-21 às 19 11 40" src="https://github.com/user-attachments/assets/a355116b-93e7-49e5-8a7e-d9d4914c24ec" />

## ⚒️ Componentes utilizados
| Componente | Descrição |
| --- | --- |
| Azure AI Foundry | Agente  |
| Modelo implementado | gpt-4.1-nano |
| Knowledge | base_agendamento_clinica_veterinaria.pdf |
| Action | code interpreter|
| Action | base_clientes_clinica_veterinaria.csv |


## 📚 Bases utilizadas
| Base | Nome | Módulo
| --- | --- |--- |
| base_agendamento_clinica_veterinaria.pdf | Base de Agendamentos | Knowledge|
| base_clientes_clinica_veterinaria.csv  | Base de cadastro e histórico de gastos  dos clientes | Action |


## ✅ Passo a passo
1. Criação da conta gratuita no Azure;
2. Criação do grupo de recurso;
3. Ativação do recurso Microsoft Foundry;
4. Deploy do modelo utilizado - gpt-4.1-nano;
5. Criação do Agent;
6. Inclusão de uma base de conhecimento em Knowledge;
7. Inclusão de uma action "code interpreter" a partir da inclusão de uma base .csv de dados sintéticos de histórico de gastos de clientes;

## 🔗 Links de referência 
- AzureFrontierGirls AI Challenge: [https://github.com/Miyake-Diogo/AzureFrontierGirls-AI-Challenge/tree/main](https://github.com/Miyake-Diogo/AzureFrontierGirls-AI-Challenge/tree/main)
- AI Agent for beginners: [https://github.com/microsoft/ai-agents-for-beginners](https://github.com/microsoft/ai-agents-for-beginners)
