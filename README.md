<header>

# Olá GitHub Actions

_Criar e executar um fluxo de trabalho do GitHub Actions._

</header>

## Passo 5: Acionar o fluxo de trabalho

_Agora você adicionou um fluxo de trabalho totalmente funcional ao seu repositório! :smile:_

O script shell no fluxo de trabalho será executado sempre que um novo pull request for aberto.

**Vendo sua _action_ em ação**: O status de cada execução de fluxo de trabalho que é acionada é mostrado no pull request antes de ser mesclado: procure por **All checks have passed** quando você experimentar os passos abaixo. Você também pode ver uma lista de todos os fluxos de trabalho que estão executando, ou que terminaram de executar, na aba **Actions** do seu repositório. De lá, você pode clicar em cada execução de fluxo de trabalho para ver mais detalhes e acessar arquivos de log.

![Uma captura de tela da aba Actions mostrando uma lista de execuções de fluxo de trabalho.](https://user-images.githubusercontent.com/16547949/62388049-4e64e600-b52a-11e9-8bf5-db0c5452360f.png)

### :keyboard: Atividade: Acionar o fluxo de trabalho

1. Crie uma nova branch chamada `test-workflow`.
1. Faça uma alteração, como adicionar um emoji ao seu arquivo README.md, e confirme a alteração diretamente em sua nova branch.
1. Na aba **Pull requests**, crie um pull request que fará merge de `test-workflow` em `main`.
1. Observe o fluxo de trabalho sendo executado na seção de verificações do pull request.
1. Note o comentário que o fluxo de trabalho adiciona ao pull request.
1. Aguarde cerca de 20 segundos e atualize esta página (a que você está seguindo as instruções). Outro fluxo de trabalho será executado e substituirá o conteúdo deste arquivo README pelas instruções para o próximo passo.

<footer>

---

Obtenha ajuda: [Poste em nosso fórum de discussão](https://github.com/orgs/skills/discussions/categories/hello-github-actions) &bull; [Consulte a página de status do GitHub](https://www.githubstatus.com/)

&copy; 2023 GitHub &bull; [Código de Conduta](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [Licença MIT](https://gh.io/mit)

</footer>
