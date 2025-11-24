# Assistente Clínica Veterinária
Objetivo: Assistente de Clínica Veterinária para realização de orçamento de serviços.

## 📌  Visão Geral
O que é o assistente é capaz de fazer?
* Realizar atendimento para serviços como BANHO, TOSA ou CONSULTA para gatos ou cachorros.

## 🧩 Problema
Demora no atendimento para obtenção de informaçao sobre valores de serviços ofertados pela clínica gerava grande descontentamento dos clientes e/ou futuros clientes.

## ⚙️ Solução
Agente inteligente que realiza o cálculo de serviços e informa no momento os valores.

## 🤖 Agente 
  
### Tela 01
- Primeiro contato: gostaria de realizar um orçamento
  <img width="1052" height="733" alt="Agents playground - Microsoft Foundry 4" src="https://github.com/user-attachments/assets/7911d615-1614-4a44-a911-26892d57e49a" />

### Tela 02
- Fornecimento de mais informaçoes
<img width="1106" height="771" alt="Agents playground - Microsoft Foundry 5" src="https://github.com/user-attachments/assets/11919c73-757d-4a20-aec5-2b497c13fa3d" />

### Tela 03
- Orçamento realizado
<img width="1066" height="586" alt="Agents playground - Microsoft Foundry 3" src="https://github.com/user-attachments/assets/df923a81-9055-4af7-8188-127046c8d01f" />

## ⚒️ Componentes utilizados
| Componente | Descrição |
| --- | --- |
| Azure AI Foundry | Agente  |
| Modelo implementado | gpt-4.1-nano |
| Action | code interpreter|

## 💻 Código utilizado
Código python:

```python
import pandas as pd

def calcular_orcamento_veterinaria(itens_solicitados):
    """
    Calcula o orçamento baseada em uma lista de serviços padronizados.
    itens_solicitados: Lista de dicionários [{'servico': 'chave', 'qtd': 1}]
    """
    
    # Tabela de Preços
    TABELA_PRECOS = {
        "tosa_gato": {"preco": 145.00, "desc": "Tosa (Gato)"},
        "tosa_cachorro": {"preco": 95.00, "desc": "Tosa (Cachorro)"},
        "banho_gato": {"preco": 75.00, "desc": "Banho (Gato)"},
        "banho_cachorro": {"preco": 120.00, "desc": "Banho (Cachorro)"},
        "consulta": {"preco": 250.00, "desc": "Consulta Veterinária"},
        "racao_gato": {"preco": 90.00, "desc": "Ração Gato (4kg)"},
        "racao_cachorro": {"preco": 100.00, "desc": "Ração Cachorro (10kg)"}
    }

    detalhes_orcamento = []
    total_geral = 0

    for item in itens_solicitados:
        chave = item.get('servico')
        qtd = item.get('qtd', 1)
        
        if chave in TABELA_PRECOS:
            servico_info = TABELA_PRECOS[chave]
            subtotal = servico_info['preco'] * qtd
            total_geral += subtotal
            
            detalhes_orcamento.append({
                "Serviço": servico_info['desc'],
                "Valor Unit.": servico_info['preco'],
                "Quantidade": qtd,
                "Subtotal": subtotal
            })
        else:
            # Caso o agente passe uma chave errada
            detalhes_orcamento.append({
                "Serviço": f"Item não identificado ({chave})",
                "Valor Unit.": 0.0,
                "Quantidade": qtd,
                "Subtotal": 0.0
            })

    # Criação de DataFrame 
    df_orcamento = pd.DataFrame(detalhes_orcamento)
    
    # Formatação para exibição
    print("=== ORÇAMENTO CLÍNICA VETERINÁRIA ===")
    if not df_orcamento.empty:
        print(df_orcamento.to_markdown(index=False, floatfmt=".2f"))
        print(f"\nVALOR TOTAL A PAGAR: R$ {total_geral:.2f}")
    else:
        print("Nenhum serviço válido identificado.")
pedido_cliente = [
    {'servico': 'banho_cachorro', 'qtd': 2},  # "Dois banhos nos meus labradores"
    {'servico': 'racao_gato', 'qtd': 1},      # "E um saco de ração pro gato"
    {'servico': 'consulta', 'qtd': 1}         # "Aproveita e marca uma consulta"
]

calcular_orcamento_veterinaria(pedido_cliente)
```

## ✅ Passo a passo
1. Criação da conta gratuita no Azure;
2. Criação do grupo de recurso;
3. Ativação do recurso Microsoft Foundry;
4. Deploy do modelo utilizado - gpt-4.1-nano;
5. Criação do Agent;
6. Criação do script em python para cálculo dos serviços ofertados;
7. Adição do script ao Action Code Interpreter;

## 🔗 Links de referência 
- AzureFrontierGirls AI Challenge: [https://github.com/Miyake-Diogo/AzureFrontierGirls-AI-Challenge/tree/main](https://github.com/Miyake-Diogo/AzureFrontierGirls-AI-Challenge/tree/main)
- AI Agent for beginners: [https://github.com/microsoft/ai-agents-for-beginners](https://github.com/microsoft/ai-agents-for-beginners)
