# Pechincha.ai para o Claude Code

Plugin que conecta o Claude Code ao [Pechincha.ai](https://pechincha.ai): promoções, histórico de preço e cupons das lojas online do Brasil, direto na conversa.

## Instalar

```
/plugin marketplace add pechincha-ai/pechincha-claude-plugin
/plugin install pechincha@pechincha
```

Depois é só perguntar, por exemplo: "tem alguma promoção boa de air fryer?" ou "esse preço está bom?" com o link do produto.

## Sem plugin

O plugin só registra o servidor MCP público `https://pechincha.ai/mcp`. Dá pra adicionar direto:

```
claude mcp add --transport http pechincha https://pechincha.ai/mcp
```

No claude.ai, ChatGPT, Cursor e outras IAs, veja o passo a passo em [pechincha.ai/ia](https://pechincha.ai/ia).
