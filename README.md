# Agregação, tratamento e visualização de dados e metodologias

Repositório de organização e desenvolvimento do Challenge sobre desinformação do Grupo 6. A primeira etapa reúne catálogo, inspeção, leitura manual, EDA e visualização; os requisitos permanecem provisórios e serão refinados pelo grupo.

- [Challenge e frentes de trabalho (#1)](https://github.com/Residencia-em-IA-Grupo-6/agregacao-tratamento-e-visualizacao-de-dados-de-noticias-e-metodologias/issues/1)
- [Coordenação, marcos e decisões (#17)](https://github.com/Residencia-em-IA-Grupo-6/agregacao-tratamento-e-visualizacao-de-dados-de-noticias-e-metodologias/issues/17)
- [EDA comparativa (#18)](https://github.com/Residencia-em-IA-Grupo-6/agregacao-tratamento-e-visualizacao-de-dados-de-noticias-e-metodologias/issues/18)
- [Project Fake News](https://github.com/orgs/Residencia-em-IA-Grupo-6/projects/1)

## Organização provisória

EDA e visualização ficam juntas neste repositório inicialmente. Quando houver código e artefatos, usar `analysis/` para análises, `reports/` para entregáveis revisados e `visualization/` para a interface; criar pastas conforme surgirem conteúdos concretos. Essas são convenções de destino, não aplicações já implementadas.

O clone `datasets/` na workspace serve como fonte intermediária. Migrar apenas material conferido, preservando proveniência e registrando origem e destino. O clone independente `FACTCK.BR-extended` já está no lugar definido na workspace. Os experimentos Laya têm seu próprio repositório e suas issues ainda são propostas locais nesta sessão.

## Dados locais

A raiz provisória recomendada é `~/Dados/fake-news`, externa aos repositórios Git. A convenção é separar `raw/<fonte>/<versao>/`, `derived/<fonte>/<versao>/` e `cache/`, preservando originais e identificando as transformações. Cada fonte terá um registro de obtenção, versão/hash, formato e condições de uso; nenhum desses dados foi migrado por este bootstrap.

Scripts futuros devem ler `FAKE_NEWS_DATA_DIR` e explicar como configurá-la. O [.env.example](.env.example) registra o contrato; não há loader nem carregamento automático de `.env` implementado. CSV e Parquet podem coexistir conforme a necessidade. Versionar código, metadados e resultados compactos cuja divulgação tenha sido conferida; não adicionar corpus bruto, caches e outputs individuais ao Git.

A normalização e consolidação em banco local por desenvolvedor ou remoto ficam para uma decisão de arquitetura posterior. Submodules também serão avaliados nesse momento; não são necessários para começar a exploração.

## Contribuição

O fluxo inicial usa `main` e branches curtas com PRs. As convenções de issues, labels, fechamento e branches estão em [CONTRIBUTING.md](CONTRIBUTING.md). O único conteúdo inicial é a documentação de organização; dependências e comandos de análise serão definidos com a implementação.
