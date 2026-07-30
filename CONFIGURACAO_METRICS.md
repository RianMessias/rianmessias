# Configuração do GitHub Metrics

O workflow já está configurado para usar o secret `METRICS_TOKEN`. Falta apenas criar o token no GitHub, cadastrá-lo no repositório e executar o workflow pela primeira vez.

## Passo a passo

1. Abra as configurações da sua conta no GitHub.
2. Acesse **Developer settings → Personal access tokens → Tokens (classic)** e crie um Personal Access Token.
3. Conceda somente as permissões mínimas necessárias. Para as métricas públicas configuradas neste repositório, a documentação do `lowlighter/metrics` informa que o token clássico pode ser criado **sem escopos adicionais**. Não habilite `repo` se não quiser incluir dados de repositórios privados.
4. Abra o repositório de perfil [`RianMessias/rianmessias`](https://github.com/RianMessias/rianmessias).
5. Acesse **Settings → Secrets and variables → Actions**.
6. Clique em **New repository secret**.
7. Informe exatamente `METRICS_TOKEN` no campo de nome e cole o token no campo de valor.
8. Abra a aba **Actions** do repositório.
9. Selecione o workflow **GitHub Metrics**.
10. Clique em **Run workflow** e confirme a execução na branch `main`.

Após a primeira execução bem-sucedida, a Action criará o arquivo `github-metrics.svg` na raiz do repositório. As execuções seguintes atualizarão esse arquivo automaticamente uma vez por dia.

> **Segurança:** nunca cole o token no `README.md`, no workflow, neste arquivo ou em commits. Mantenha-o somente no secret `METRICS_TOKEN`.
