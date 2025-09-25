## Passo 3: Adicionar uma etapa ao seu arquivo de fluxo de trabalho

_Bom trabalho adicionando um job ao seu fluxo de trabalho! :dancer:_

Os fluxos de trabalho têm jobs, e os jobs têm etapas. Então agora vamos adicionar uma etapa ao seu fluxo de trabalho.

**O que são _etapas_?**: As etapas do Actions são executadas - na ordem em que são especificadas, de cima para baixo - quando um job do fluxo de trabalho é processado. Cada etapa deve passar para que a próxima etapa seja executada.

Cada etapa consiste em um script shell que é executado, ou uma referência a uma action que é executada. Quando falamos sobre uma action (com "a" minúsculo) neste contexto, queremos dizer uma unidade reutilizável de código. Você pode descobrir sobre actions em "[Encontrando e personalizando actions](https://docs.github.com/pt/actions/learn-github-actions/finding-and-customizing-actions)", mas por enquanto usaremos um script shell em nossa etapa do fluxo de trabalho.

Atualize seu fluxo de trabalho para fazê-lo postar um comentário em novos pull requests. Ele fará isso usando um script [bash](https://en.wikipedia.org/wiki/Bash_%28Unix_shell%29) e [GitHub CLI](https://cli.github.com/).

### :keyboard: Atividade: Adicionar uma etapa ao seu arquivo de fluxo de trabalho

1. Ainda trabalhando na branch `welcome-workflow`, abra seu arquivo `welcome.yml`.
1. Atualize o conteúdo do arquivo para:

   ```yaml copy
   name: Post welcome comment
   on:
     pull_request:
       types: [opened]
   permissions:
     pull-requests: write
   jobs:
     build:
       name: Post welcome comment
       runs-on: ubuntu-latest
       steps:
         - run: gh pr comment $PR_URL --body "Welcome to the repository!"
           env:
             GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
             PR_URL: ${{ github.event.pull_request.html_url }}
   ```

   **Nota:** A etapa que você adicionou usa o GitHub CLI (`gh`) para adicionar um comentário quando um pull request é aberto. Para permitir que o GitHub CLI poste um comentário, definimos a variável de ambiente `GITHUB_TOKEN` com o valor do secret `GITHUB_TOKEN`, que é um token de acesso de instalação, criado quando o fluxo de trabalho é executado. Para mais informações, veja "[Autenticação automática de token](https://docs.github.com/pt/actions/security-guides/automatic-token-authentication)". Definimos a variável de ambiente `PR_URL` como a URL do pull request recém-criado, e a usamos no comando `gh`.
   
1. Clique em **Commit changes** no canto superior direito do editor de fluxo de trabalho.
1. Digite sua mensagem de commit e confirme suas alterações diretamente em sua branch.
1. Aguarde cerca de 20 segundos e atualize esta página (a que você está seguindo as instruções). Outro fluxo de trabalho será executado e substituirá o conteúdo deste arquivo README pelas instruções para o próximo passo.
