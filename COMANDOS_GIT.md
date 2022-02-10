# Git

## Resumo

> Git é um sistema de controle de versões (VCS - Version Control System):
– Mantém um histórico de alterações;
– Permite ter controle sobre alterações do código;

## Principais comandos

##### Criar um repositório Git:
#
```
git init
```

##### Analisar o estado do nosso repositório:
#
```
git status
```
 Ao executar o comando git status, recebemos algumas informações como:
 |  |  |
| --- | --- |
| HEAD | Classificação do Git sobre o estado atual do nosso código |
| Working tree | Local onde os arquivos são armazenados e editados |
| index | Local onde o Git armazena o que será commitado |

#####  Visualizar o histórico de alterações em nosso projeto

#
```
git log
git log --oneline
git log -p
```

## Commitando as alterações

##### Primeira alteração
1) No terminal Git Bash navegue até a pasta do projeto;
2) Execute o comando `git add <nome_arquivo>` para marcar o arquivo para ser commitado;
3) Execute `git status` para conferir o estado do arquivo e se está pronto para ser commitado;
4) Execute o comando para adicionar uma mensagem `git commit -m "<Mensagem de Commit>"`;

##### Demais alterações
5) Para treinar mais, altere novamente o arquivo;
6) Adicione o arquivo para ser salvo, com `git add .`;
7) Execute o comando para adicionar uma mensagem `git commit -m "<Nova Mensagem de Commit>"`;
8) Execute o comando `git log` e analise a saída;

##### Ignorando alterações
9) Crie um novo arquivo;
10) Crie o arquivo `.gitignore` e adicione uma linha com o nome do arquivo recém-criado;
11) Execute `git status` e verifique que o arquivo não está na lista para ser commitado;
12) Realize o commit do  arquivo `.gitignore` com `git add .gitignore`;




