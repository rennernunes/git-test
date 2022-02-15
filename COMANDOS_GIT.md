# Git

## Resumo

> Git é um sistema de controle de versões (VCS - Version Control System):
</br> – Mantém um histórico de alterações;
</br> – Permite ter controle sobre alterações do código;

# Principais comandos

### Criar um repositório Git local:


```
git init
```

### Criar um repositório Git remoto:


```
git remote add nome-repositorio <caminho/do/repositorio>
```

### Fix git erro: Authentication failed (Windows Git Bash):

```
1. GitHub > Settings > Developer settings > Personal access tokens > generate new token > Copiar o token

2. No Git Bash > rodar o git push > Entrar com usuário do GitHub > Na senha colocar o token > rodar o git push
```

### Atribuir um responsável pelo repositório:

```
git config --local user.name <Nome do usuário>
```

### Visualizar o repositório:

```
git remote -v
```

### Analisar o estado do nosso repositório:

```
git status
```

</br>

### Ao executar o comando git status, recebemos algumas informações como:
 |  |  |
| --- | --- |
| HEAD | Classificação do Git sobre o estado atual do nosso código |
| Working tree | Local onde os arquivos são armazenados e editados |
| index | Local onde o Git armazena o que será commitado |

</br>

###  Visualizar o histórico de alterações em nosso projeto

```
git log
git log --oneline
git log -n 2
```

### Ver alterações no código no console:
```
git log -p
```

## Commitando as alterações

### Primeira alteração
1) No terminal Git Bash navegue até a pasta do projeto;
2) Execute o comando `git add <nome_arquivo>` para marcar o arquivo para ser commitado;
3) Execute `git status` para conferir o estado do arquivo e se está pronto para ser commitado;
4) Execute o comando para adicionar uma mensagem `git commit -m "<Mensagem de Commit>"`;

### Demais alterações
5) Para treinar mais, altere novamente o arquivo;
6) Adicione o arquivo para ser salvo, com `git add .`;
7) Execute o comando para adicionar uma mensagem `git commit -m "<Nova Mensagem de Commit>"`;
8) Execute o comando `git log` e analise a saída;

### Ignorando alterações
9) Crie um novo arquivo;
10) Crie o arquivo `.gitignore` e adicione uma linha com o nome do arquivo recém-criado;
11) Execute `git status` e verifique que o arquivo não está na lista para ser commitado;
12) Realize o commit do  arquivo `.gitignore` com `git add .gitignore`;

</br>

## Mergeando branches

</br>

> Branches ("ramos"):
</br> - São utilizados para desenvolver funcionalidades isoladas umas das outras
</br> –  A branch master é a branch "padrão"
</br> – É interessante separar o desenvolvimento de funcionalidades em branches diferentes

### Checkout:
Atualiza os arquivos na _working tree_ para ficarem na versão especificada.
```
git checkout <branch>
```

### Criando uma branch local:

```
git checkout -b <nova_branch>
```

### Navegar em um commit pelo hash
Exibe mensagem indica que estamos em um estado de cabeça (HEAD) desanexado (detached) do controle de versões. </br>
Não estamos mais em nenhuma branch, e sim em um commit específico

```
git log --oneline
git checkout <hash>
```
Se quisermos manter os commits feitos a partir deste ponto, será necessário criar uma nova branch
```
git checkout -b <nova_branch>
```

### Fazendo o merge da branch na branch master

```
git checkout master
git merge <branch>
```

### Fazendo o rebase da branch na branch master

```
git checkout master
git rebase <branch>
```

### Rebase vs Merge
 |  |  |
| --- | --- |
| Merge | Agrupa os commits da branch e gera um merge commit |
| Rebase | Atualiza a branch atual (mantendo o trabalho dela como sendo o último) </br> e aplica os commits da outra branch nela |
| Discussão | https://medium.datadriveninvestor.com/git-rebase-vs-merge-cc5199edd77c |


###  Exibindo diferença entre as alterações
```
git diff
```

Ver alterações de vários commits:
```
git diff <id1>...<id2>
```
Ver os comits que não estão na branch:
```
gitk origin/master..origin/dev
```

### Salvando temporariamente

Quando precisamos pausar o desenvolvimento antes de finalizar, talvez não seja interessante realizar um commit.
</br> Nesse caso é interessante salvar o trabalho para podermos voltar a ele depois.

```
git stash
git stash list
git stash apply 0
```
Remover as modificações: 
```
git stash drop
```
Aplicar e remover as modificações ao emsmo tempo:

```
git stash pop
```

## Ctrl + Z no Git
#
### Remover alterações que não foram commitadas
```
git checkout -- <arquivo>
```

### Remover alterações que foram adicionadas para serem commitadas (git add)
```
git reset HEAD <arquivo>

Para remover o arquivo:

git checkout -- <arquivo>
```

### Remover alterações que foram commitadas
#### O commit informado será desfeito, criando outro commit
```
git log
git revert <commit_id>
```

## Tags e releases
#
Definindo uma versão para o projeto
```
git tag -a <v0.1.0> -m <"Lançando a primeira versão da ..."
git push origin master
git push origin v0.1.0
```