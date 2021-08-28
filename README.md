## GIT

-   **Configurações**:
    -   Usuário:  **git config --global user.name "Claudio Marcos de Campos"**          
    -   Email:  **git config --global user.email "cmcampos86@gmail.com"**          
    -   Editor (Visual Studio Code):  **git config --global core.editor "code --wait"**        
    -   Lista de configurações:  **git config --list**
    -   Cria atalho para comandos: **git config --global alias.*ALIAS* *COMANDO***
   
-   **Repositório**
    -   Inicia um repositório:  **git init**
    -   Status do repositório:  **git status**

-   **Add e commit**  
    -   Adiciona um arquivo (usado para incluir ou quando há modificação):  **git add *NOME_ARQUIVO***
	-   Adiciona todos os arquivos (usado para incluir ou quando há modificação):  **git add** *
    -   Efetua um commit: **git commit -m "*MENSAGEM_COMMIT*"**
    -   Efetua o commit de um arquivo que já existe (-am): **git commit -am "***MENSAGEM_COMMIT***"**
    -   Diferença na alteração do arquivo:  **git diff**
    -   Só os arquivos modificados: **git diff --name-only**

-   **Reset**
    -   Reset do arquivo antes de ter adicionado para o commit: **git checkout *NOME_ARQUIVO***
    -   Reset para quando o arquivo já estiver adicionado para o commit: **git reset HEAD  *NOME_ARQUIVO***
    -   Tipo de reset (escolher sempre o commit anterior):
        -   Exclui o commit e coloca o arquivo para staged: **git reset --soft *HASH***
        -   Exclui o commit e coloca o arquivo para antes do staged (padrão git reset): **git reset --mixed *HASH***
        -   Exclui o commit: **git reset --hard *HASH***

-   **Histórico**
    -   Simples:  **git log**          
    -   Com informações da branche: **git log --decorate**
    -   Buscando pelo autor do commit: **git log --author="*NOME_AUTOR*"**
    -   Enxuto:  **git shortlog**          
    -   Com a quantidade de commits feitos:  **git shortlog -sn**          
    -   Mostrando as linhas de evolução do arquivo: **git shortlog --graph**
    -   Específico pela hash:  **git show *HASH***
	-   Compara repositório local com o remoto:  **git log --oneline --decorate --all --graph**
    -   Tecla **q** finaliza o log

-   **Configurar Repositório no GitHub**  
    -   Apontar  repositório local no remoto: **git remote add origin *ENDEREÇO_REPOSITÓRIO***
    -   Envia os arquivo para o repositório remoto: **git push -u *NOME_REMOTE* master**
    -   Remove um remote: **git remote rm *NOME_REMOTE***
    -   Enviar as alterações para o servidor remoto: **git push *NOME_REMOTE* *BRANCH***
    -   Clonar um repositório: **git clone *ENDEREÇO_REPOSITÓRIO NOME_REPOSITORIO***
	-	Listar arquivos de configuração GIT: **git config --list --show-origin**
	
-   **Branches**
    -   Cria um branche e já deixa esta marcada: **git checkout -b *NOME_BRANCH***
    -   Listar branches:  **git branch**
    -   Aponta para um branch: **git branch *NOME_BRANCH***
    -   Apaga um branch: **git branch -D *NOME_BRANCH***
    -   Apaga branch no servidor remoto(depois de ter executado o comando acima): **git push origin :*BRANCH***

-   **Merge/Rebase**
    -   Faz o merge (uni arquivo mas cria commit extra)**: git merge *NOME_BRANCH***
    -   Faz o rebase (uni arquivos, mas deixa o histórico linear, apagando commits desnecessários): **git rebase *NOME_BRANCH***
	-   O conflito pode acontecer quando for feita alteração no mesmo arquivoe na mesma linha
	-   Após dar o conflito pela linha de comando, é necessário abrir o arquivo e escolher entre o que estava no local (HEAD) ou o que vem no repositório do merge

-   **.gitignore**
    -   Gravar o arquivo como .gitignore e colocar ***.EXTENSAO** ou o **nome do arquivo** que você quer ignorar no commit
    -   Link aonde tem alguns .gitignores por projetos: **[https://github.com/github/gitignore](https://github.com/github/gitignore)**
	
-   **Stash**
    -   Guarda alterações não commitadas em uma pasta/arquivo a parte
    -   Guarda o que foi feito:  **git stash save**
    -   Aplica o que foi guardado:  **git stash apply *AREA_STASH(dar um git stash list e pegar o area stash)***
    -   Lista os stashs feitos:  **git stash list**
    -   Limpa os stashs:  **git stash clear**
	-   Apagar o stashs:  **git stash drop *AREA_STASH(dar um git stash list e pegar o area stash)***
	-   Aplica o stash e apagar:  **git stash pop *AREA_STASH(dar um git stash list e pegar o area stash)***

-   **Tags**
    -   Identificada como Release no github, tags servem para marcar a versão de um conjunto de commits
    -   Cria a tag: **git tag -a <*VERSAO*> -m "*MENSAGEM*"**
    -   Envia para o repositório remoto: **git push *NOME_REMOTE* *BRANCH* --tags**
    -   Lista as tags: **git tag**
    -   Apaga tags: **git tag -d *TAG***
    -   Apaga tags no servidor remoto(depois de ter executado o comando acima): **git push origin :*TAG***
	
-   **Revert**
    -   O revert não perder no histórico as coisas que foram feitas, diferente do reset que faz isso: **git revert *HASH***  
        
-   **Configurar o proxy**
	-	Reset do proxy
        -   **git config --global --unset-all remote.origin.proxy**
        -   **git config --global --unset http.proxy**
        -   **git config --global --unset https.proxy**
	-	Configuração do proxy
        -   **git config --global http.sslVerify false**
        -   **git config --global https.sslVerify false**
        -   **git config --global http.proxy http://username:password@enderecoproxy:porta**
        -   **git config --global https.proxy http://username:password@enderecoproxy:porta**
	-	Notas
        -   Não utilizar http:// no endereço do proxy
		-	Se a senha conter caracteres especiais, o unicode dela deve ser usado (https://pt.stackoverflow.com/questions/14421/fazer-o-git-passar-pelo-proxy)

## **GITHub**

-   Para repositórios privados, o github é cobrado, diferente do bitbucket que não é.
-   **SSH** é um protocolo que serve para autenticar um usuário remoto ao servidor
-   Site para ter as chaves para autenticar e fazer os commits no github: [https://help.github.com/articles/connecting-to-github-with-ssh/](https://help.github.com/articles/connecting-to-github-with-ssh/). Os links para configurar é o  **Generating a new SSH key**  e o **Adding your SSH key to the ssh-agent**
-   Quando for usar o git no console, pode efetuar o procedimento acima, mas quando for usar com o git extension, deve-se gerar uma key pelo generate key do putty que tem no git extensions e ai adicionar a key no git hub. Logo... teremos duas key: uma para o git e outra para git extensions.
-   **Origin** é o nome da origem do remoto (pode ser qualquer nome)
-   **Fork**: pega um projeto que não é seu e faz uma cópia dele pra você. É diferente do clone que você faz uma cópia, mas o projeto é seu.
-   Editor de arquivo README.md: **https://stackedit.io/**
