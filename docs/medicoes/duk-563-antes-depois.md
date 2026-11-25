# DUK-563 — o cartão aparece quando algo vai mudar

Medição de 24/11/2026, na branch `feat/duk-563-leitura-sem-cartao`.

![antes e depois](antes-depois.png)

## O que foi medido

A decisão de um comando no degrau **`Pergunta tudo`** — o degrau em que o
Cauteloso e o Planejador são projetados (`EixosDoModo`, `eixos.go`). Os mesmos
quinze comandos rodaram nos dois lados:

- **antes** — `domain.DecidirComandoLocal` de `origin/homolog` (`91e16c97`);
- **depois** — `domain.DecidirComandoNaPasta` da branch, que é a porta que o
  adaptador usa (`execcomando.go`), com uma raiz de teste de verdade.

As saídas estão cruas em `antes.tsv` e `depois.tsv`, no formato
`comando → decisão → motivo`. O print é a renderização desses dois arquivos;
não há número escrito à mão nele.

## O que mudou

| | antes | depois |
|---|---|---|
| `git status`, `ls`, `cat`, `go test` | cartão | livre |
| `Get-Content`, `Get-ChildItem` (PowerShell) | cartão | livre |
| `ls && git status` (composto só de leitura) | cartão | livre |
| `cd app; ls` (dentro da pasta) | cartão | livre |
| `ls \| wc -l` | cartão ("composto") | cartão ("composto") — `\|` fica de fora |
| `git status && npm run build` | cartão ("composto") | cartão, **dizendo qual parte barrou** |
| `grep -rn x . > saida.txt` | cartão | cartão — redirecionar grava |
| `rm -rf build`, `git push --force` | cartão (trava) | cartão (trava) |
| `cd ..; ls` | cartão | cartão — sai da pasta |

## Como reproduzir

Cada lado é um `main.go` de 30 linhas que importa `dukk-poc/internal/domain`.
Ele fica fora do repositório de propósito: é prova, não produto.

```bash
# antes
git worktree add ../base origin/homolog
cd ../base && go run ./caminho/do/programa-de-antes

# depois
cd <branch> && go run ./caminho/do/programa-de-depois
```

No lado de depois, a raiz é `os.MkdirTemp` com uma pasta `app` dentro, para
que `cd app` seja um caminho que existe sem depender da máquina de quem roda.

## O que NÃO foi provado aqui

- O print é a decisão do **motor**, não a tela do app com o cartão desenhado.
  A tela usa o mesmo `PreviaComando` de sempre; o aviso novo aparece nela, mas
  capturar isso exige abrir o app com login, e isso não foi feito nesta sessão.
- O volume real de cartões economizados. O número de novembro (1.681 cliques,
  4 em 10 de leitura) vem da task; o que esta medição mostra é o comportamento
  por comando, não a contagem em produção.
