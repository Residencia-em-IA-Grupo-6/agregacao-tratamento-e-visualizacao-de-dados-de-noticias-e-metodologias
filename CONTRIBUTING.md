# Convenções provisórias de trabalho

Revisar estas convenções após algumas issues/PRs reais. Elas organizam o trabalho inicial sem fixar stack, perguntas de pesquisa ou arquitetura final.

## Issues e relações

Usar o template geral de quatro partes: objetivo/contexto, escopo/entrega, critérios de aceite e relações/evidências. Um título descreve uma ação e um resultado; prefixos como `[EDA]` ou `[Dados]` ajudam a leitura, mas não são obrigatórios.

Uma issue corresponde a uma entrega revisável. Criar filhos quando houver resultados executáveis e verificáveis separadamente; manter checklists para passos pequenos da mesma entrega. Um pai coordena as partes que compõem seu resultado. Trabalho relacionado recebe links, sem ser colocado como filho apenas porque compartilha o assunto. Não criar uma issue por gráfico, coluna, commit ou discussão curta.

Usar relações nativas de pai/filho para composição e dependências para impedimentos reais. Distinguir “usa resultados de” de “só pode começar depois de”: catálogo, inspeção, leitura e análise podem avançar por recortes em paralelo. Não inserir bloqueios por conveniência visual do board.

Ao concluir, registrar artefato/commit/PR, como foi conferido e limitações. Trabalho já feito pode receber uma issue retrospectiva, cujo aceite exige evidência revisada. Uma tarefa descartada fecha como não planejada; duplicata só fecha depois de preservar conteúdo e indicar a issue canônica. Fechar um filho não significa que seu pai foi concluído.

## Tipos, labels e Project

| Campo | Uso |
| --- | --- |
| Tipo nativo `Task`, `Feature`, `Bug` | Natureza do trabalho: tarefa, capacidade de produto ou defeito concreto |
| `tipo:planejamento`, `tipo:pesquisa`, `tipo:dados`, `tipo:documentacao` | Categoria do trabalho; combinar apenas quando ambas forem úteis |
| `tema:eda`, `tema:visualizacao`, `tema:guiding-questions` | Tema que precisa ser filtrado entre frentes diferentes |
| `dominio:*` | Contexto do conteúdo, como jornalismo e fact-checking |
| `escopo:manual`, `escopo:baixo-computacional` | Restrição ou método de execução quando realmente caracterizar a entrega |
| Milestone | Fase/entrega compartilhada; prazo somente quando acordado |
| Assignees e campos do Project | Responsável, status, prioridade e datas; não duplicar em labels |

Por compatibilidade, os nomes `tipo:*` existentes são preservados, embora representem categorias e não substituam o tipo nativo. As fases usam milestones; a label antiga `fase:engage` deixa de ser aplicada. Labels padrão como `documentation` e `enhancement` sobrepõem convenções atuais: ficam preservadas no catálogo, sem uso preferencial. `bug`, `help wanted` e `accessibility` continuam úteis quando existir a necessidade correspondente. Não criar label de prioridade, bloqueio, responsável ou “épico” para duplicar campos/relações.

Novas issues entram no Project como trabalho a organizar. Responsáveis, prazos e status de execução refletem acordo e evidência; não presumir que todas as issues abertas estejam em andamento.

## Branches e revisão

`main` contém o estado compartilhado. Criar uma branch por unidade de trabalho, a partir de `main` atualizada, e propor sua integração por PR:

```text
analysis/<issue>-<assunto>   EDA e análises
data/<issue>-<assunto>       ingestão, metadados e migração
feat/<issue>-<assunto>       capacidade de visualização
docs/<issue>-<assunto>       documentação e organização
fix/<issue>-<assunto>        correção de defeito
chore/<issue>-<assunto>      manutenção do ambiente
```

Uma issue de coordenação pode não exigir branch. Um PR pode atender passos de mais de uma issue se a revisão permanecer coesa; registrar cada relação. Usar `Closes #N` apenas quando o aceite da issue estiver atendido; em contribuição parcial, usar `Ref #N`. Fazer revisão e verificações proporcionais à mudança, registrando reprodução de análises quando pertinente. Após merge, apagar branches concluídas.

O primeiro commit de documentação inicializa diretamente a branch padrão, necessária para oferecer os templates num repositório vazio. As próximas mudanças seguem branch e PR. Não foi configurada proteção de branch nesta sessão.

Gitflow com `develop`, `release/*` e `hotfix/*` passa a ser uma opção se houver versões de produto mantidas em paralelo e calendário de releases. Na fase de investigação, `main` e branches curtas dão histórico revisável com menos coordenação. Tags podem marcar entregáveis depois de sua revisão; não criar versões apenas para espelhar cada issue.

## Alternativas de template

| Opção | Vantagens | Limitações | Quando considerar |
| --- | --- | --- | --- |
| Um template Markdown geral (adotado) | Curto, adaptável a pesquisa, dados, decisões e retrospectivas; funciona bem pela CLI | Preenchimento inconsistente precisa de revisão; não impõe campos obrigatórios | Enquanto aprendemos quais informações são realmente necessárias |
| Um formulário YAML com poucos campos obrigatórios | Padroniza contexto e aceite e facilita preenchimento guiado | Menos flexível; exige manter o formulário e seu vocabulário | Se as primeiras issues repetirem omissões importantes |
| Templates específicos para pesquisa, dados e bugs | Perguntas adequadas a cada tipo de trabalho | Mais manutenção e dúvida sobre qual escolher; pode duplicar conteúdo | Quando surgirem padrões recorrentes distintos |

Por ora há um template de issue e um de PR. Issues em branco continuam permitidas para casos que não se encaixem. Antes de ampliar, observar se objetivo, entrega, aceite e evidências estão ajudando o grupo a executar e revisar o trabalho.
