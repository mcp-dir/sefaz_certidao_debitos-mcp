---
name: sefaz_certidao_debitos-mcp
description: Skill da REST API do SEFAZ: Certidão Negativa de Débitos Estaduais na MCP.AI: 1 endpoint em /api/sefaz_certidao_debitos. SEFAZ: Certidão Negativa de Débitos Estaduais, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# SEFAZ: Certidão Negativa de Débitos Estaduais — REST API skill

Você tem acesso à **SEFAZ: Certidão Negativa de Débitos Estaduais** REST API na MCP.AI.

> SEFAZ: Certidão Negativa de Débitos Estaduais, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/sefaz_certidao_debitos
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/sefaz_certidao_debitos/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"uf":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/sefaz_certidao_debitos/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `sefaz_certidao_debitos_consultar`

SEFAZ: Certidão Negativa de Débitos Estaduais, consulta em fonte oficial. _(POST /api/sefaz_certidao_debitos/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `cnpj` | string | Não | Parâmetro de consulta "cnpj". |
| `cpf` | string | Não | Parâmetro de consulta "cpf". |
| `ie` | string | Não | Parâmetro de consulta "ie". |
| `cep` | string | Não | Parâmetro de consulta "cep". |
| `cpf_emissao` | string | Não | Parâmetro de consulta "cpf_emissao". |
| `uf` | string | Sim | Parâmetro de consulta "uf". |
| `preferencia_emissao` | string | Não | Parâmetro de consulta "preferencia_emissao". |
| `login_cpf` | string | Não | Parâmetro de consulta "login_cpf". |
| `login_senha` | string | Não | Parâmetro de consulta "login_senha". |
| `pkcs12_cert` | string | Não | Parâmetro de consulta "pkcs12_cert". |
| `pkcs12_pass` | string | Não | Parâmetro de consulta "pkcs12_pass". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_sefaz_certidao_debitos` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
