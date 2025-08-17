# create_tool_for_llm

Este projeto demonstra como criar um **agente de chat** que utiliza **ferramentas (function calling)** para responder perguntas sobre preços de passagens aéreas.  

Ele usa o modelo **LLaMA 3** via **Ollama** e implementa uma ferramenta personalizada `get_ticket_price` para consultar valores de passagens.

---

## 📂 Estrutura do Notebook

- **Configuração do modelo**
  - Importa `ollama`
  - Define o modelo usado: `llama3.1:8b`

- **Mensagem de sistema**
  - Define o papel da IA como um assistente de uma companhia aérea chamada **FlightAI**

- **Tabela de preços**
  - Um dicionário com valores de passagens de ida e volta para algumas cidades (`London`, `Paris`, `Tokyo`, `Berlin`).

- **Ferramenta: `get_ticket_price`**
  - Função que recebe uma cidade e retorna o preço da passagem correspondente.

- **Descrição da ferramenta**
  - Estrutura JSON que informa ao modelo como usar a função (`name`, `description`, `parameters`).

- **Registro das ferramentas**
  - Lista `tools` que conecta a função ao modelo.

- **Função de chat**
  - Controla a conversa com o usuário, decide quando chamar a ferramenta e retorna a resposta final.

- **Manipulação de chamadas de ferramenta**
  - Função `handle_tool_call` que executa a função Python real quando o modelo solicita.

- **Interface com usuário**
  - Uso de `gr.ChatInterface` para criar uma interface interativa de chat.
