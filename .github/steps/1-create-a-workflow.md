## Passo 1: Criar um arquivo de fluxo de trabalho

_Bem-vindos ao "Olá GitHub Actions"! :wave:_

**O que é o _GitHub Actions_?**: O GitHub Actions é uma maneira flexível de automatizar quase todos os aspectos do fluxo de trabalho de software da sua equipe. Você pode automatizar testes, fazer deploy contínuo, revisar código, gerenciar issues e pull requests, e muito mais. A melhor parte é que esses fluxos de trabalho são armazenados como código em seu repositório e facilmente compartilhados e reutilizados entre equipes. Para saber mais, confira estes recursos:

- A página de recursos do GitHub Actions, veja [GitHub Actions](https://github.com/features/actions).
- A documentação do usuário "GitHub Actions", veja [GitHub Actions](https://docs.github.com/pt/actions).

**O que é um _fluxo de trabalho_?**: Um fluxo de trabalho é um processo automatizado configurável que executará um ou mais jobs. Os fluxos de trabalho são definidos em arquivos especiais no diretório `.github/workflows` e são executados com base no evento escolhido. Para este exercício, usaremos um evento `pull_request`.

- Para ler mais sobre fluxos de trabalho, jobs e eventos, veja "[Entendendo o GitHub Actions](https://docs.github.com/pt/actions/learn-github-actions/understanding-github-actions)".
- Se você quiser saber mais sobre o evento `pull_request` antes de usá-lo, veja "[pull_request](https://docs.github.com/pt/developers/webhooks-and-events/webhooks/webhook-events-and-payloads#pull_request)".

Para começar, executamos um fluxo de trabalho do Actions em seu novo repositório que, entre outras coisas, criou uma branch para você trabalhar, chamada `welcome-workflow`.

### :keyboard: Atividade: Criar um arquivo de fluxo de trabalho

1. Abra uma nova aba do navegador e navegue para este mesmo repositório. Em seguida, trabalhe nas etapas em sua segunda aba enquanto lê as instruções nesta aba.
1. Crie um pull request. Isso conterá todas as alterações que você fará ao longo desta parte do curso.

   Clique na aba **Pull Requests**, clique em **New pull request**, defina `base: main` e `compare:welcome-workflow`, clique em **Create pull request** e depois clique em **Create pull request** novamente.

1. Navegue para a aba **Code**.
1. No dropdown da branch **main**, clique na branch **welcome-workflow**.
1. Navegue para a pasta `.github/workflows/`, então selecione **Add file** e clique em **Create new file**.
1. No campo **Name your file**, digite `welcome.yml`.
1. Adicione o seguinte conteúdo ao arquivo `welcome.yml`:

   ```yaml copy
   name: Post welcome comment
   on:
     pull_request:
       types: [opened]
   permissions:
     pull-requests: write
   ```

1. Para confirmar suas alterações, clique em **Commit changes**.
1. Digite uma mensagem de commit, selecione **Commit directly to the welcome-workflow branch** e clique em **Commit changes**.
1. Aguarde cerca de 20 segundos e atualize esta página (a que você está seguindo as instruções). Um fluxo de trabalho separado do Actions no repositório (não o fluxo de trabalho que você criou) será executado e automaticamente substituirá o conteúdo deste arquivo README pelas instruções para o próximo passo.
