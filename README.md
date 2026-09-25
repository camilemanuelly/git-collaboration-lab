# Git Collaboration Lab

Espaço prático criado para registrar exercícios, testes de fluxo de trabalho e comandos avançados de Git e GitHub durante os meus estudos.

A ideia aqui não é só anotar teoria, mas usar o próprio repositório para testar branches, resolução de conflitos, rebase e simulações de Pull Requests.

## Conteúdo Praticado

### 1. Fundamentos e Git Local
* Instalação, configuração e comandos básicos (`status`, `add`, `commit`, `log`).
* Como o Git rastreia arquivos (áreas de trabalho, staging e commits).
* Desfazendo coisas: `checkout`, `revert` e correções com `commit --amend`.

### 2. Branches e Conflitos
* Criação e troca de branches (`switch`/`checkout`).
* Tipos de merge (fast-forward e commits de merge).
* Identificação e resolução manual de conflitos de merge.

### 3. Trabalho Remoto (GitHub)
* Conexão via SSH e configuração de repositórios remotos (`origin`).
* Sincronização de alterações: diferenças entre `fetch`, `pull` e `push`.
* Organização do fluxo pull-merge-push.

### 4. Colaboração em Equipe
* Fluxo com forks e abertura de Pull Requests.
* Limpeza de commits usando rebase interativo (`squash` e `fixup`).
* Boas práticas de Code Review e atendimento a feedbacks.
* Diferenças práticas entre Merge Commit, Squash and Merge e Rebase and Merge no GitHub.

## Cenário 1: Resolução de Conflitos.
Estratégia adotada: Integração manual realizada após divergência entre a branch de desenvolvimento e a main. Ambas as propostas foram avaliadas e consolidadas para manter o histórico de auditoria e a estabilidade da release.

## Cenário 2: Limpeza de Histórico com Rebase Interativo.
O rebase interativo (`git rebase -i`) permite reescrever o histórico local antes de integrá-lo à branch principal. A técnica combina múltiplos commits intermediários em uma única entrega atômica via `squash` ou `fixup`, eliminando ruídos de desenvolvimento e garantindo um histórico linear e auditável.

### Caso Real Durante o Cenário 2: Correção de Linhagem com Rebase Onto
- **Problema:** Criei a branch de feature inadvertidamente a partir de `feature/conflict-guide` em vez de `main`, herdando histórico desatualizado.
- **Solução Técnica:** Usei o comando `git rebase --onto main <commit-base> <branch>` para transplantar a cadeia de commits diretamente para o topo da `main`, resolvendo os conflitos de patch passo a passo via `--continue`.
