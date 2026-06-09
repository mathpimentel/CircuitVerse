# AGENTS.md — CircuitVerse (fork de manutenção)

> Arquivo de orientação para agentes de IA (Codex etc.) trabalhando neste fork do CircuitVerse.
> Coloque-o na raiz do repositório. O agente deve segui-lo ao executar qualquer tarefa.

## Sobre o projeto
- Aplicação **Ruby on Rails**.
- UI migrando para a gem **ViewComponent**. Os componentes são **namespaceados** e vivem em
  `app/components/<Namespace>/...` (ex.: `Home::BadgeComponent`, `Home::StatCardComponent`).
- **Paginação** via gem **`will_paginate` (~4.0.1)** + **`will_paginate-bootstrap`** (Bootstrap 5).
- Testes em **RSpec**. Lint com **RuboCop**. Frontend usa **Bootstrap 5**.

## Comandos de validação
- Testes: `bundle exec rspec` (ou apenas os specs relacionados aos arquivos alterados)
- Lint: `bundle exec rubocop` (apenas nos arquivos alterados)
- Instalação de dependências Ruby: `bundle install`

> Observação: subir o app completo (Postgres/Redis/Yarn) pode não funcionar no sandbox. Se a suíte
> completa não rodar, é aceitável: declare a limitação e valide por (a) teste do componente isolado,
> (b) inspeção de código e (c) checklist de teste manual para o humano.

## Regras de contribuição (FAÇA)
- Leia o `CONTRIBUTING.md`, o `README.md` e o template de PR antes de codar.
- Faça o **menor diff possível**, sempre vinculado claramente a uma issue.
- Siga as convenções de branch, commit e estilo já usadas no projeto.
- Mantenha **nomes de classe/arquivo, identificadores e mensagens de commit/PR em inglês**.
- Reutilize helpers, i18n e padrões já existentes no projeto.
- Ao migrar para ViewComponent, **copie o padrão de PRs já mergeados** (ex.: #5811, #5815, #5830):
  classe Ruby do component + template `.html.erb` + teste do component + namespace correto.

## Restrições (NÃO FAÇA)
- ❌ Não altere comportamento ou aparência em tarefas de migração (é refactor, não redesign).
- ❌ Não faça refatoração ampla, reformatação de arquivos não relacionados ou mudanças cosméticas.
- ❌ Não troque dependências/gems nem mexa em configuração de build sem necessidade.
- ❌ Não toque em código de segurança, autenticação, pagamento ou dados sensíveis.
- ❌ Não deixe `// TODO`, código morto, ou chamadas órfãs após uma migração.
- ❌ Não invente nem simule evidências de teste. Se não executou, diga que não executou.
- ❌ Não abra Pull Request duplicado de uma issue que já tenha PR aberto em andamento.

## Pull Request
- Abra a PR **contra `CircuitVerse/CircuitVerse:master`**, a partir da branch deste fork.
- Vincule a issue no corpo (`Fixes #<numero>` ou `Closes #<numero>`).
- Siga o template de PR do projeto: descrição do problema, resumo da solução, tipo de manutenção,
  testes/validações realizados e limitações conhecidas.
- Não marque mantenedores nem peça revisão com urgência. Tom respeitoso e profissional.

## Contexto
Este fork é usado em uma **atividade acadêmica** de manutenção de software. A prioridade é um processo
correto, respeitoso e bem documentado — não o tamanho da alteração.
