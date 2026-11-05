# emissaoja for Cursor: issue Brazilian NFS-e (API de NFS-e nacional)

[![Install in Cursor](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/install-mcp?name=emissaoja&config=eyJ1cmwiOiJodHRwczovL2VtaXNzYW9qYS5jb20uYnIvbWNwIn0=) [![Install in VS Code](https://img.shields.io/badge/VS_Code-Install_emissaoja_MCP-0098FF?logo=visualstudiocode&logoColor=white)](https://vscode.dev/redirect/mcp/install?name=emissaoja&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Femissaoja.com.br%2Fmcp%22%7D)

Issue, track, download and cancel Brazilian service invoices (**NFS-e**) inside [Cursor](https://cursor.com), through the national **Emissor Nacional** and without a digital certificate, using the [emissaoja](https://emissaoja.com.br/emitir-nota-fiscal-por-ia) MCP server.

## What's included

- **MCP server** (`mcp.json`): `https://emissaoja.com.br/mcp`, Streamable HTTP. Cursor asks you to sign in to emissaoja (OAuth with Google) on the first call that needs your account. Tools and details: [emissaoja-mcp](https://github.com/Easymovel/emissaoja-mcp).
- **Rule** (`rules/emissaoja-nfse.mdc`): teaches the agent the emissaoja REST API (auth, idempotent issuing, polling with `proxima_consulta_ms`, error codes, sandbox) when you write NFS-e integration code.

## Manual install

Add to `~/.cursor/mcp.json` or `.cursor/mcp.json` in your project:

```json
{
  "mcpServers": {
    "emissaoja": { "url": "https://emissaoja.com.br/mcp" }
  }
}
```

For tests without tax effect, use `https://sandbox.emissaoja.com.br/mcp` with an `ej_test_` key (`"headers": { "Authorization": "Bearer ej_test_..." }`).

## Em português

Emita NFS-e pelo Cursor: o agente consulta a sua empresa, cadastra clientes pelo CNPJ, emite a nota no Emissor Nacional sem certificado digital e acompanha a autorização, sempre confirmando com você antes de emitir ou cancelar. Para MEI e empresas do Simples Nacional. Crie a conta em [emissaoja.com.br](https://emissaoja.com.br/?origem=cursor-plugin). Documentação da API: [emissaoja.com.br/docs](https://emissaoja.com.br/docs/).

## Links

- Docs: https://emissaoja.com.br/docs/ · OpenAPI: https://emissaoja.com.br/v1/openapi.json · llms.txt: https://emissaoja.com.br/llms.txt
- SDKs: [Node.js](https://github.com/Easymovel/emissaoja-js) · [Python](https://github.com/Easymovel/emissaoja-py) · [PHP](https://github.com/Easymovel/emissaoja-php) · [.NET](https://github.com/Easymovel/emissaoja-dotnet) · [Go](https://github.com/Easymovel/emissaoja-go) · [Ruby](https://github.com/Easymovel/emissaoja-ruby)
- Support: suporte@emissaoja.com.br

emissaoja is a private service, operated by BINOBO LTDA, with no affiliation with Receita Federal or Emissor Nacional.
