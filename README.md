# Pechincha.ai para o Claude Code: promoções, cupons e histórico de preço no seu assistente de IA

[![Plugin do Claude Code](https://img.shields.io/badge/Claude_Code-plugin-D97757)](#instalar-no-claude-code)
[![Servidor MCP](https://img.shields.io/badge/MCP-pechincha.ai%2Fmcp-2563EB)](https://pechincha.ai/ia)
[![Adicionar ao Cursor](https://img.shields.io/badge/Cursor-adicionar-000000)](https://cursor.com/install-mcp?name=pechincha&config=eyJ1cmwiOiJodHRwczovL3BlY2hpbmNoYS5haS9tY3AifQ==)
[![Instalar no VS Code](https://img.shields.io/badge/VS_Code-instalar-0098FF)](https://vscode.dev/redirect/mcp/install?name=pechincha&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fpechincha.ai%2Fmcp%22%7D)

Plugin oficial do [Pechincha.ai](https://pechincha.ai) para o **Claude Code**. Com ele, o Claude busca **promoções e ofertas das lojas online do Brasil**, mostra o **histórico de preço** do produto e diz se o desconto é de verdade, encontra **cupons de desconto** ativos e compara o mesmo produto entre lojas. Tudo dentro da conversa, com preços em reais.

O plugin instala o **servidor MCP público do Pechincha.ai** (`https://pechincha.ai/mcp`). É grátis, não pede conta nem chave de API, e as ferramentas só leem dados: nada é comprado ou alterado em seu nome.

## Sumário

- [O que dá pra fazer](#o-que-dá-pra-fazer)
- [Instalar no Claude Code](#instalar-no-claude-code)
- [Exemplos de pergunta](#exemplos-de-pergunta)
- [Ferramentas do servidor MCP](#ferramentas-do-servidor-mcp)
- [Usar em outras IAs](#usar-em-outras-ias-claudeai-cursor-vs-code-gemini-cli-chatgpt)
- [Como funciona](#como-funciona)
- [Perguntas frequentes](#perguntas-frequentes)
- [English](#english)

## O que dá pra fazer

- **Buscar promoções ativas** por produto, loja, categoria, tema ou faixa de preço ("até R$ 3.000", "entre R$ 100 e R$ 200").
- **Ver os destaques do momento**, o menor preço primeiro ou as ofertas mais vistas.
- **Saber se o preço está bom**: o histórico de preço traz mínimo, média e máximo e os preços registrados dia a dia.
- **Conferir um link de loja**: cole a URL de um produto e veja se há promoção ativa e qual é o menor preço entre as lojas.
- **Achar cupons de desconto** de uma loja, ou os cupons que valem para uma promoção específica.
- **Comparar alternativas**: outras marcas, modelos e lojas do mesmo tipo de produto.
- **Explorar temas e datas**, como Black Friday, Dia das Crianças, ideias de presente e nichos.
- **Abrir listas de presentes** compartilhadas no site (`pechincha.ai/lista/<slug>`).
- **Ler guias de compra** do blog do Pechincha.ai.

## Instalar no Claude Code

Requisito: [Claude Code](https://code.claude.com/docs/pt/overview) instalado (terminal, app desktop ou extensão de IDE).

**1. Adicione o marketplace do Pechincha.ai:**

```
/plugin marketplace add pechincha-ai/pechincha-claude-plugin
```

**2. Instale o plugin:**

```
/plugin install pechincha@pechincha
```

**3. Confira a conexão:** rode `/mcp` e procure `plugin:pechincha:pechincha` como conectado. Se o Claude Code já estava aberto, reinicie a sessão.

Pelo terminal, fora de uma sessão, os mesmos passos são:

```bash
claude plugin marketplace add pechincha-ai/pechincha-claude-plugin
claude plugin install pechincha@pechincha
```

**Atualizar:** `claude plugin update pechincha@pechincha`. **Remover:** `claude plugin uninstall pechincha@pechincha`.

### Sem plugin

O plugin só registra o servidor MCP. Se preferir, adicione o servidor direto:

```bash
claude mcp add --transport http pechincha https://pechincha.ai/mcp
```

## Exemplos de pergunta

Escreva como falaria com uma pessoa, em português:

- "Tem alguma promoção boa de air fryer até R$ 400?"
- "Esse preço está bom? https://…" (com o link do produto na loja)
- "Quais são as melhores ofertas de hoje?"
- "Me mostra o histórico de preço desse produto nos últimos 30 dias."
- "Tem cupom de desconto pra essa promoção?"
- "Acha uma alternativa mais barata a esse fone."
- "Ideias de presente de Dia das Crianças até R$ 150."
- "Quais lojas estão com cupom ativo agora?"
- "Tem guia de compra de notebook no blog do Pechincha?"

## Ferramentas do servidor MCP

São 14 ferramentas, todas só de leitura:

| Ferramenta | O que faz |
| --- | --- |
| `search_deals` | Busca promoções ativas por palavras, loja, categoria, tema e faixa de preço, ordenadas por relevância, novidade, destaque, menor preço ou mais vistas. |
| `get_deal` | Detalhes de uma promoção: foto, preço, desconto, loja, cupom, link de compra, histórico de 30 dias, prós e contras, ficha técnica e perguntas frequentes. |
| `get_product` | O produto em todas as lojas: ofertas atuais, menor preço, estatísticas de 30 dias e resumo das avaliações. |
| `get_price_history` | Histórico de preço para julgar se o desconto é real: mínimo, média, máximo e até 30 preços com data. |
| `check_product_url` | Recebe a URL de um produto numa loja e diz se há promoção ativa e qual o menor preço entre as lojas. |
| `get_similar_deals` | Promoções parecidas (outras marcas, modelos e lojas) para comparar ou achar opção mais barata. |
| `list_deal_coupons` | Cupons ativos da loja de uma promoção, com a regra de cada um e a validade. |
| `list_store_coupons` | Cupons de desconto ativos de uma loja. |
| `list_coupon_stores` | Lojas que estão com cupom ativo. |
| `list_stores` | Lojas do Pechincha.ai (mais de mil), com filtro por nome. |
| `list_categories` | Categorias, para filtrar a busca. |
| `list_themes` | Temas: datas sazonais (Black Friday, Dia das Crianças…), ideias de presente e nichos. |
| `get_list` | Uma lista pública do site, como uma lista de presentes compartilhada, com faixa de preço e promoções ativas. |
| `search_guides` | Guias de compra e artigos do blog do Pechincha.ai. |

## Usar em outras IAs (claude.ai, Cursor, VS Code, Gemini CLI, ChatGPT)

O mesmo servidor MCP funciona em qualquer cliente compatível com MCP por HTTP (Streamable HTTP). O endereço é sempre:

```
https://pechincha.ai/mcp
```

- **claude.ai e app do Claude:** [adicionar o conector em 1 clique](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Pechincha.ai&connectorUrl=https%3A%2F%2Fpechincha.ai%2Fmcp) (Personalizar → Conectores). No claude.ai, as promoções aparecem num painel visual com foto e preço.
- **Cursor:** [adicionar ao Cursor](https://cursor.com/install-mcp?name=pechincha&config=eyJ1cmwiOiJodHRwczovL3BlY2hpbmNoYS5haS9tY3AifQ==).
- **VS Code:** [instalar no VS Code](https://vscode.dev/redirect/mcp/install?name=pechincha&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fpechincha.ai%2Fmcp%22%7D).
- **Gemini CLI:** `gemini mcp add --transport http pechincha https://pechincha.ai/mcp`
- **Outros clientes (`mcp.json`):**

  ```json
  {
    "mcpServers": {
      "pechincha": { "url": "https://pechincha.ai/mcp" }
    }
  }
  ```

O passo a passo de cada IA, inclusive ChatGPT e Grok, está em **[pechincha.ai/ia](https://pechincha.ai/ia)**. O servidor também está no [MCP Registry oficial](https://registry.modelcontextprotocol.io/v0/servers?search=ai.pechincha) como `ai.pechincha/deals`.

## Como funciona

O [Pechincha.ai](https://pechincha.ai) é um agregador de promoções: reúne ofertas das lojas online do Brasil e guarda o preço de cada produto ao longo do tempo. O servidor MCP expõe esses dados para o assistente de IA:

- **Promoções expiram 7 dias depois de publicadas.** A busca só traz as ativas.
- **O veredito de preço precisa de histórico.** Só há avaliação quando existem preços de pelo menos 3 dias diferentes; antes disso, a ferramenta avisa que ainda não dá pra julgar.
- **Conteúdo em português do Brasil e preços em reais (BRL).** Pergunte em português para a busca funcionar melhor.
- **Links levam ao Pechincha.ai e à loja.** A compra acontece no site da loja, nunca dentro da IA.

## Perguntas frequentes

**É grátis?**
Sim. O plugin e o servidor MCP são gratuitos e não pedem cadastro.

**Preciso de conta no Pechincha.ai?**
Não. Para alertas de preço, listas e favoritos, crie uma conta em [pechincha.ai](https://pechincha.ai).

**O plugin compra alguma coisa ou mexe nos meus arquivos?**
Não. Ele só adiciona um servidor MCP remoto, e todas as ferramentas são de leitura. Não há comandos, hooks nem código rodando na sua máquina.

**Funciona fora do Brasil?**
Funciona em qualquer lugar, mas as promoções são de lojas brasileiras, com preços em reais.

**Por que no terminal a resposta vem em texto e no claude.ai vem com fotos?**
O painel visual (MCP App) aparece nos clientes que o suportam, como o claude.ai. No terminal do Claude Code, as mesmas informações chegam em texto, com links.

**Quero integrar promoções no meu site ou app. Tem API?**
Tem a API para parceiros, documentada em [pechincha.ai/desenvolvedores](https://pechincha.ai/desenvolvedores).

**Achei um problema ou tenho uma sugestão.**
Abra uma [issue](https://github.com/pechincha-ai/pechincha-claude-plugin/issues) neste repositório.

## English

**Pechincha.ai for Claude Code** is the official plugin that connects Claude Code to [Pechincha.ai](https://pechincha.ai), a Brazilian deals aggregator. It installs the public, read-only MCP server at `https://pechincha.ai/mcp` (no account or API key), with 14 tools to search active deals in Brazilian online stores, check a product's price history, find coupon codes, compare stores and browse seasonal themes. Content is in Brazilian Portuguese and prices are in BRL.

```
/plugin marketplace add pechincha-ai/pechincha-claude-plugin
/plugin install pechincha@pechincha
```

---

Feito pelo [Pechincha.ai](https://pechincha.ai): promoções, cupons e histórico de preço das lojas online do Brasil.
