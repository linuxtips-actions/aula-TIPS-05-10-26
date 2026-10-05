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
| `07-injection-pr-vulneravel.yml` | Injection pelo nome da branch de um PR (demo com fork) |
| `08-injection-pr-corrigido.yml` | A correção do 07: `head_ref` passado por `env:` |

Também há um `.github/dependabot.yml` que mantém os SHAs das actions atualizados.

> ⚠️ Os workflows `01` e `07` são **vulneráveis de propósito**. Mantenha este
> repositório **privado**, ou desative/apague esses workflows depois da aula.
> O passo a passo da demo com fork está em `INSTRUCOES-DEMO-FORK.md`.

## Payload da demo 1

Abra uma issue com este título:

```
bug"; echo "INJETADO: $(whoami)@$(hostname)"; echo "
```

## Descobrir o SHA de uma tag

```bash
git ls-remote https://github.com/actions/checkout refs/tags/v4.2.2
```
