# git-collaboration-lab

Laboratório prático de Git simulando fluxos de trabalho em equipe, resolução de problemas de histórico e estratégias de integração via GitHub.

## Estrutura

```text
├── .github/
│   └── pull_request_template.md   # Template com checklist de PR
├── docs/
│   └── code-review-guide.md       # Regras adotadas para revisão
└── README.md                      # Log de execução dos cenários
```

## Cenários Executados

### 1. Conflito de Merge
- **Problema:** Divergência nas mesmas linhas do `README.md` entre `main` e `feature/conflict-guide`.
- **Ação:** Identificação manual dos delimitadores (`<<<<<<<`, `=======`, `>>>>>>>`), unificação do conteúdo e commit de merge (`02caea4`).
- **Comandos:**
```bash
git checkout main
git merge feature/conflict-guide
# Edição manual do arquivo
git add README.md
git commit -m "Merge branch 'feature/conflict-guide'"
```

### 2. Correção de Linhagem (`git rebase --onto`)
- **Problema:** A branch `feature/pr-review-amend` foi ramificada por engano a partir de `feature/conflict-guide` em vez da `main`.
- **Ação:** Transplante cirúrgico da cadeia de commits diretamente para o topo da `main`, ignorando a base errada.
- **Comandos:**
```bash
git rebase --onto main <commit-base> feature/pr-review-amend
git rebase --continue
```

### 3. Higiene de Histórico (`git commit --amend`)
- **Problema:** Necessidade de alterar arquivos após feedback de revisão sem criar commits de ruído ("fix", "ajuste").
- **Ação:** Absorção do staging no último commit mantendo a árvore limpa.
- **Comandos:**
```bash
git add README.md
git commit --amend --no-edit
```

### 4. Estratégias de Merge e Ciclo Remoto
- **Execução:** Abertura do PR #1 usando template padronizado, revisão e integração na `main` via merge commit (`6213da5`).
- **Pós-merge:** Remoção da branch remota e limpeza dos ponteiros locais obsoletos.
- **Comandos:**
```bash
git checkout main
git pull
git branch -d feature/pr-merge-strategies
git fetch --prune
```

## Como Auditar

Verifique o histórico completo e a árvore de merges pelo terminal:

```bash
git log --graph --oneline --all
```
