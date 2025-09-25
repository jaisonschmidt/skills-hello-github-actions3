<header>

# Olá GitHub Actions

_Criar e executar um fluxo de trabalho do GitHub Actions._

</header>

## Passo 2: Adicionar um job ao seu arquivo de fluxo de trabalho

_Bom trabalho! :tada: Você adicionou um arquivo de fluxo de trabalho!_

Aqui está o que significam as entradas no arquivo `welcome.yml`, na branch `welcome-workflow`:

- `name: Post welcome comment` dá um nome ao seu fluxo de trabalho. Este nome aparecerá na aba Actions do seu repositório.
- `on: pull_request: types: [opened]` indica que seu fluxo de trabalho será executado sempre que alguém abrir um pull request em seu repositório.
- `permissions` atribui ao fluxo de trabalho permissões para operar no repositório
- `pull-requests: write` dá ao fluxo de trabalho permissão para escrever em pull requests. Isso é necessário para criar o comentário de boas-vindas.

Em seguida, precisamos especificar jobs para executar.

**O que é um _job_?**: Um job é um conjunto de etapas em um fluxo de trabalho que são executadas no mesmo runner (um runner é um servidor que executa seus fluxos de trabalho quando acionado). Os fluxos de trabalho têm jobs, e os jobs têm etapas. As etapas são executadas em ordem e são dependentes umas das outras. Você adicionará etapas ao seu fluxo de trabalho mais tarde no curso. Para ler mais sobre jobs, veja "[Jobs](https://docs.github.com/pt/actions/learn-github-actions/understanding-github-actions#jobs)".

Na atividade a seguir, você adicionará um job "build" ao seu fluxo de trabalho. Você especificará `ubuntu-latest` como o runner de job mais rápido e barato disponível. Se você quiser ler mais sobre por que usaremos esse runner, veja a explicação do código para a linha `runs-on: ubuntu-latest` no artigo "[Entendendo o arquivo de fluxo de trabalho](https://docs.github.com/pt/actions/learn-github-actions/understanding-github-actions#understanding-the-workflow-file)".

### :keyboard: Atividade: Adicionar um job ao seu arquivo de fluxo de trabalho

1. Em uma aba separada do navegador, certifique-se de estar na branch `welcome-workflow` e abra seu arquivo `.github/workflows/welcome.yml`.
1. Edite o arquivo e atualize seu conteúdo para:

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
   ```

1. Clique em **Commit changes** no canto superior direito do editor de fluxo de trabalho.
1. Digite uma mensagem de commit e confirme suas alterações diretamente na branch `welcome-workflow`.
1. Aguarde cerca de 20 segundos e atualize esta página (a que você está seguindo as instruções). Outro fluxo de trabalho será executado e substituirá o conteúdo deste arquivo README pelas instruções para o próximo passo.

<footer>

---

Obtenha ajuda: [Poste em nosso fórum de discussão](https://github.com/orgs/skills/discussions/categories/hello-github-actions) &bull; [Consulte a página de status do GitHub](https://www.githubstatus.com/)

&copy; 2023 GitHub &bull; [Código de Conduta](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [Licença MIT](https://gh.io/mit)

</footer>
