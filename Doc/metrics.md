## Métricas de Saúde, Fluxo e Qualidade
* Dora (Enxergar, Comparar, Priorizar, DF/LT/CFR/MTTR)

### Deploy Frequency (DF)
* Definição: Frequência com que o código é entregue em produção.
* Coleta: Contagem de disparos do pipeline de deploy na branch main (via GitHub Actions/GitLab CI).
* Meta: Mínimo de 1 deploy por semana.

### Lead Time (LT)
* Definição: Tempo médio entre o primeiro commit de uma tarefa e sua chegada em produção.
* Coleta: Timestamp do merge commit menos o timestamp do primeiro commit da branch. Extraído via API do Git.
* Meta: < 72 horas.

### Change Failure Rate (CFR)
* Definição: Percentual de deploys que resultam em falhas (bugs críticos, rollback ou hotfix).
* Coleta: (Número de Hotfixes / Total de Deploys) * 100. Identificado por PRs com a label hotfix.
* Meta: < 45%.

### Mean Time To Recovery (MTTR)
* Definição: Tempo médio para restaurar o serviço após uma falha em produção.
* Coleta: Tempo entre a abertura de um incidente (ou alerta no monitoramento) e o deploy da correção.
* Meta: < 1 dia.