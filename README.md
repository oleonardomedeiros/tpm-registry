# tpm-registry

Registry de pacotes para o **TPM — TOTVS Package Manager**.

## Estrutura

```
index.json              ← índice de todos os pacotes disponíveis
packages/
  {nome}/
    {versão}/
      {nome}.tlpp       ← arquivo fonte
```

## Como publicar um pacote

1. Crie a pasta `packages/{nome}/{versão}/`
2. Adicione o arquivo `{nome}.tlpp`
3. Atualize o `index.json` com a nova versão
4. Faça o commit e push

## Formato do index.json

```json
{
  "packages": {
    "api-financeiro": {
      "description": "API financeira",
      "versions": ["1.0.0", "1.1.0"],
      "latest": "1.1.0"
    }
  }
}
```

## Uso no projeto

No arquivo `packages` do seu projeto:

```
source 'https://cdn.jsdelivr.net/gh/oleonardomedeiros/tpm-registry@main'

package 'api-financeiro', '1.0.0'
```
