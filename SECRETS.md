# Gerenciamento de Segredos

Este repositório usa `dbutils.secrets` para recuperar segredos em tempo de execução no Databricks.

## Regras básicas

- Não versionar credenciais, tokens, connection strings ou chaves em arquivos do repositório.
- Guardar dados sensíveis em Secret Scopes do Databricks.
- Usar o arquivo [conf.json](conf.json) apenas para informações não sensíveis, como nomes de conta, containers e identificadores de escopo.

## Exemplo de uso no notebook

```python
access_key = dbutils.secrets.get(
    scope="olist-scope",
    key="access-key"
)
```

## Recomendação

Se a organização já utiliza Azure Key Vault, prefira conectar o Secret Scope do Databricks ao Key Vault para centralizar e controlar o ciclo de vida das credenciais.
