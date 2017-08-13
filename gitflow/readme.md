![](http://i.imgur.com/C6iN5jr.png?1)

> O git-flow é um conjunto de extensões para o git que provê operações de alto-nível para repositórios usando o modelo de branches do Vincent Driessen. [mais](http://nvie.com/posts/a-successful-git-branching-model/)

É recomendado o uso do [git-flow](https://danielkummer.github.io/git-flow-cheatsheet/index.html) para controle de versões de projetos no CITi. Ele garante que o código mantenha-se organizado e consistente, dando alternativas simples para releases de features, sprints e correção de bugs.

## Instalação
1. Baixe o arquivo [gitflow-installer.sh](https://raw.githubusercontent.com/citiufpe/citi-coding-style/master/gitflow/gitflow-installer.sh) (no Cloud9, digite `wget https://raw.githubusercontent.com/vanessa/citi-coding-style/master/gitflow/gitflow-installer.sh`) e coloque-o no diretório principal do seu projeto.
2. Digite `chmod +x gitflow-installer.sh`
3. Digite `sudo ./gitflow-installer.sh`
4. Pronto! O git-flow está instalado e pronto para uso.

## Como e por quê?
To-do.
- [ ] Explicar gerenciamento de projetos, sprint
- [ ] .gitignore

## Utilizando em um projeto
1. Digite `git flow init` e responda algumas perguntas simples para configuração. É recomendado que você utilize as opções padrão (para isso, só apertar Enter até o final da instalação)
2. Para cada feature (em nossos projetos, são as **Epics**) dentro de um sprint, inicie uma branch de feature seguindo o nome *feature/nome-do-epic*. Para isso, digite `git flow feature start nome-do-epic`, você notará que automaticamente a branch será trocada, e a partir daí pode commitar normalmente até a feature ser finalizada
3. Quando você acreditar que terminou a feature e está pronto pra iniciar outra, digite `git flow feature finish nome-do-epic`, isso fará o seguinte:
    * Mesclará *nome-do-epic* na branch *develop*
    * Remove a branch da feature
    * Volta automaticamente para a branch *develop*
4. Quando todas as features do sprint terminarem e você estiver pronto para começar outro sprint, crie um release usando o comando `git flow release start versao`, por exemplo: `git flow release start 1.0`, e você notará que a branch será trocada para a do release
5. Na branch do release, você pode rodar testes e corrigir bugs e, quando estiver pronto para colocar seu código para produção, digite `git flow release finish versao`. Isso irá:
    * Integrar a branch do release com develop e master
    * Criará uma tag na branch com a versão do release
    * Remove a branch do release
    * Não esqueça de dar push nas tags utilizando o comando `git push --tags`
----
### Hotfixes
Correspondem a reparos emergenciais de um release.

1. Caso necessite fazer um reparo emergencial, utilize o comando `git flow hotfix start versao-incrementada` (versao-incrementada significa a utilização de semanticidade de versionamento. No ponto 4, por exemplo, utilizamos a versão `1.0`, e como iremos realizar um reparo emergencial, a versão passará a ser `1.1`, porque é a correção de um problema encontrado na versão `1.0`)
1. Ao terminar, digite `git flow hotfix finish versao-incrementada`, no nosso caso, `git flow hotfix finish 1.1`


Após iniciar o git-flow no seu projeto, você já pode seguir [este modelo](https://danielkummer.github.io/git-flow-cheatsheet/index.html#features).

#### To-do
- [ ] Como funciona?
- [ ] Sugestão de branches na configuração inicial (feature -> epic, release -> sprint)
