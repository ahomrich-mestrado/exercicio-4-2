# Exercício 4.2 — MCP Server para TODO List

MCP server que expõe as tools `criar_tarefa` e `listar_tarefas`,
implementadas como chamadas HTTP para a API REST do exercício 4.1.

## Como rodar

1. Suba a API do 4.1:
   ```bash
   uvicorn app.main:app --port 8000
   ```

2. Instale as dependências:
   ```bash
   pip install -r requirements.txt
   ```

3. Execute o cliente de teste:
   ```bash
   python cliente_teste.py
   ```

## Estrutura

- `servidor_mcp.py` — MCP server com as tools `criar_tarefa` e `listar_tarefas`
- `cliente_teste.py` — sobe o server como subprocesso via stdio e imprime o resultado em JSON
- `requirements.txt` — dependências: `mcp` e `httpx`

## Reflexão

O MCP tornou irrelevante para o agente o **protocolo de transporte**:
quem chama `criar_tarefa(titulo)` não precisa saber que por baixo
existe um endpoint HTTP com método POST, Content-Type JSON e
tratamento de status code — esses detalhes ficam encapsulados no server.
