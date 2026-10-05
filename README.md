# Aula ao vivo — Workflows mais seguros e robustos

Material de apoio da aula ao vivo do TIPS (complemento dos dias 5, 6 e 7).

| Workflow | Tema |
|---|---|
| `01-injection-vulneravel.yml` | Script injection: título de issue executado como código |
| `02-injection-corrigido.yml` | A correção: passar o dado por `env:` |
| `03-supply-chain.yml` | Actions fixadas por SHA e `permissions` mínimas |
| `04-funcoes-de-status.yml` | `success()`, `failure()`, `always()`, `cancelled()` e o skip em cascata do `needs` |
| `05-concurrency-matrix.yml` | `concurrency` com `cancel-in-progress` e matrix com `fail-fast: false` |
| `06-job-summary.yml` | Resumo do run com `$GITHUB_STEP_SUMMARY` e anotações |

Também há um `.github/dependabot.yml` que mantém os SHAs das actions atualizados.

> ⚠️ O workflow `01` é **vulnerável de propósito**. Para testar, copie para um repositório **privado** e desative ou apague o arquivo depois.

## Payload da demo 1

Abra uma issue com este título:

```
bug"; echo "INJETADO: $(whoami)@$(hostname)"; echo "
```

## Descobrir o SHA de uma tag

```bash
git ls-remote https://github.com/actions/checkout refs/tags/v4.2.2
```
