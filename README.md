# GIT - Documentação: https://git-scm.com/doc
## LIVRO: https://git-scm.com/book/en/v2


git push #enviar para o servidor

git pull #atualiza versão do repositório

#############################################

#github: opção "fork" no projeto, copia todo o projeto para o seu perfil, se clonar não é possível dar push porque você não é dono do projeto; com "fork" você consegue atualizar no seu próprio repositório

#github: pull request, manda suas alterações para o dono do projeto que você fez o fork, se não houver conflito, pode ser o dono do projeto pode fazer o merge pull request

#github: "issues" relatar erro no projeto
=> o dono do projeto pode aplicar uma "label" na issue: bug, wontfix, duplicate, invalid, etc. (mostrar como analisou a issue)

#github: criar "milestones" (ex. versao 1, versão 2) e mover cada issue para uma milestone (exemplo: tal issue será corrigida na versão 2)

#github: após mandar a issue, pode fazer uma modificação e mandar um pull request para resolvê-la. Indicar qual issue no comentário com: Close #2 (vai abrir nomes de issues e você escolhe, nesse exemplo é a 2). Se fizer a merge a issue é resolvida.

#github: criar arquivo README.md para explicar o projeto. Mais fácil editar texto pelo site dillinger.io

####################################################

#Bitbucket: igual o github
- Habilitar verificação de duas etapas e então aparece a opção SSH Keys (Seguir os passos para configurar a chave no computador)

###################################################

BRANCHES: Permitem a paralelização do trabalho, sendo possível juntar depois com outra branch e/ou merge com a master

git branch //listar as branches no repositório local

git branch nomeDaNovaBranch //criar branch

git checkout nomeDaBranch //muda para a branch

git checkout -b nomeDaNovaBranch //já cria a branch e muda para ela

git push --set-upstream origin nomeDaNovaBranch //envia nova branch para o servidor (cria a branch no servidor, estava somente no repositório local)

git push -u origin nomeDaNovaBranch //mesmo comando anterior

git branch -d nomeDaBranch //deleta a branch LOCAL
git branch -D nomeDaBranch //deleta a branch LOCAL

git branch --delete origin nomeDaBranch ///deleta a branch no SERVIDOR, se alguém estiver usando pode atrapalhar, deve ser confirmado com o grupo de trabalho

git branch -m novoNome //estando na branch, esse comando altera o seu nome LOCAL

git branch -m nomeAntigo novoNome //altera nome da branch estando em outra branch LOCAL

//não tem como deletar branch do SERVIDOR, o jeito indicado é criar uma nova e dar push, depois excluir a antiga

git merge nomeDaBranch //merge a branch indicada na branch atual
 (se não tiver conflitos), já faz o commit

//não dá pra fazer push se o trabalho remoto tem alterações comitadas que não estão no repositório local; forçando sempre manter o seu repositório local atualizado com git pull

######################################################

#kdiff3 para poder resolver conflitos

git config --global --list //mostra o usuario

git config --global --add merge.tool kdiff3 //fazer de kdiff3 a ferramenta de merge

#Agora se tiver algum conflito no merge é só digitar:
git mergetool

//abre uma janela mostrando as opçõesm para o merge; verificar e salvar

######################################################


git commit -a -m "Mais traduções" //faz o add e o commit direto

#github: PULL REQUEST solicita análise do merge antes de aceitá-lo

####################################################

git log --oneline #dentro do projeto, mostra as modificações/ commits

TAGS: servem para ajudar a mostrar em que commit tem-se uma fase estável

git tag -a nomedatag -m "Mensagem sobre a tag" //cria tag na última commit disponível

git tag //ver as tags

git push origin NomeDaTag //enviar tag para o servidor, no github ele marca como RELEASE

git checkout NomeDaTag //mover para a tag

//pode-se criar branchs de uma tag antiga, mas ela não está no projeto principal

git tag -d NomeDaTag //remove tag no LOCAL

git push --delete origin NomeDa Tag //deleta RELEASE (tag) no servidor 

git tag -a nomedatag nomeDaCommit -m "Mensagem sobre a tag" //criar tag em commit anterior

################################################

#STASH

//quando fez uma alteração no arquivo mas não quer fazer add nem commit, nem deletar a alteração

git stash //salva a alteração separadamente

git stash save "Testando stash" //outra forma de salvar, com mensagem

git status //não aparece mais a alteração

git stash list //lista as stashes salvas

git stash drop stash@{1} //obs: codigo da stash obtido na stash list, apaga a stash com o codigo indicado

git stash apply //retorna a stash mais recente ao projeto, sem apagar a stash

git stash pop //retorna a mais recente ao projeto e apaga a stash

git stash pop stash@{0} //retorna a stash com o codigo e a apaga

####################################

DELETAR COMMITS

git reset --hard HEAD~1 //volta uma commit e deleta a mais recente, pode voltar mais atrás mudando o número do HEAD, exemplo: voltar três commits: HEAD~3

####################################

MODIFICAR UM COMMIT JÁ FEITO SEM PERDER AS ALTERAÇÔES:
Ex: Alterou um arquivo e quer inserir essa alteração na commit mais recente

git commit --amend

//vai abrir uma página, no topo você pode modificar a mensagem do commit. Para sair aperte esc depois digite ":wb" e enter 

##################################

GIT FETCH: Trás as alterações do servidor e não aplica, ao contrário do git pull ( que equivale a git fetch e git merge)

##################################

REBASE: 
faz o mesmo que o git merge (a diferença é que na rebase é como eles mergeam na master: o merge pega as branchs e merge com uma nova commit, rebase não cria novo commmit).

###################################

ALIAS (fazendo atalhos)

git config --global alias.s status #configurou git s como git status

git config --global --unset alias.s #desconfigura o atalho

###################################

VER A URL ASSOCIADA AO URL

git remote -v

###################################

GRAP: ajuda na listagem de branches e tags com nomes padronizados (aplica um filtro)

git branch | grep R1 //mostra uma lista de branches que começam com "R1"

git tag | grep 1 //mostra uma lista de tags que começam com "1"

####################################

SOURCETREE: Software que mostra visualmente a árvore do projeto

Apps: sourcetree, gitkraken

https://www.sourcetreeapp.com/
https://www.gitkraken.com/			_#gostei do layout_

GIT FLOW: https://www.youtube.com/watch?v=wzxBR4pOTTs
