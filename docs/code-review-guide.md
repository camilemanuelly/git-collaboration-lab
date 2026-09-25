# Diretrizes de Code Review

Guia de boas práticas e estratégias de revisão de código para o time.

## Estratégias de Revisão
- **Pair Programming:** Desenvolvimento síncrono em dupla. Alta troca de contexto e mentoria direta.
- **Over the Shoulder:** Revisão informal presencial ou compartilhamento de tela pontual.
- **Email Thread:** Envio de patches assíncronos via lista de discussão (comum em projetos como Linux e Git).
- **Tool-Assisted:** Fluxo moderno via interface de Pull Request (GitHub/GitLab) com comentários inline e aprovações.

## Regras de Ouro para PRs
1. **Seletividade:** Atribuir apenas os revisores necessários (1 a 2 pessoas).
2. **Tempo de Resposta:** Priorizar revisões em até 2 horas úteis para evitar bloqueios de fluxo.
3. **Comentários Construtivos:** Focar no código, não no autor; justificar o *porquê* da mudança solicitada.
4. **Descrição Clara:** Explicar o contexto da alteração, testes executados e decisões tomadas.
5. **Histórico Limpo:** Utilizar rebase interativo (`squash`/`fixup`) para condensar commits redundantes antes do merge.
