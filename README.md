**GIT 101**
---

**_TERMINAL_**

É o Prompt de comando do Windows, chamado de Terminal no Linux e no iOS. É comum utilizar terminais de terceiros, ou seja, programas de terminal com funcionalidades avançadas. O Cmder, por exemplo, já vem com o Git instalado.


**- Comandos básicos de terminal**

__cd:__ Usado para acessar pastas/diretórios.
_Ex:_
~~~
<!-- cd c: -->
~~~
> Este comando leva para o diretório da unidade de armazenamento principal (C:).
Podemos ter também:
~~~
/c/users/convidado
cd d:/cursos
~~~
> partindo da pasta de usuário "convidado", entramos direto na pasta "Curso" na unidade de armazenamento (D:).

Para voltar um diretório "acima" usamos ~cd..~.
_Ex:_
~~~
d:/cursos
cd ..
d:
~~~

__dir:__ para visualizar o conteúdo de um diretório, no Windows.
> Pode ser usado, também, o comando ```tree /f``` para Windows ou o comando ```ls``` para iOs e Linux.

__mkdir:__ para criar um novo diretório.
_Ex:_
~~~
mkdir <nome do diretório>
~~~
>Para entrar no novo diretório, basca usar o comando ```cd```

__ls:__ ppara listar os arquivos e pastas do diretório.

---


**_GIT 01 - Hello Friend!_**

O Git é um sistema de vercionamento de código. Com versionamento é possível encurtar e simplificar os processos de produção de código, solo ou em equipe. Para realizar o versionamento, os principais servidores são o [Git Hub](https://github.com), [GitLab](https://gitlab.com) e o [BitBucket](https://bitbucket.org). Para utilizar o Git, é necessário instalá-lo, pode-se fazer isso baixando o Git diretamente do [site do Git](https://git-scm.com). Você pode também instalar algum terminal que já venha com o Git em conjunto, como por exemplo o [Cmder](https://cmder.net).


__Repositório:__ é o nome dado para o projeto. É literalmente um repositório de códigos.

__Branch:__ as Branchs são versões, as ramificações, do nosso projeto, sendo a "Branch Master" o projeto principal.

__Commit:__ alterações do sistema. Envio de arquivos, edições e etc. Armazena apenas as edições feitas. 

__Comandos:__ todos os comandos do Git se iniciam com o comando git.

---

**- Configurando o Git**

O primeiro passo para configurar o Git é associar um nome de usuário e um email. 

**- Comandos básicos do Git**

__git config:__ usado para configurar o Git.
__Ex:__
~~~
git config --global user.name "Nome-de-Usuário"
~~~

para configurar o nome do usuário.

~~~
git config --global user.email "email@email.com"
~~~

para configurar o email. É comum a configuração, também do editor, que é feito apartir do código

~~~
git config --global core.editor nome-do-editor
~~~
>É comum vermos comandos com apenas um traço, que é a forma abreviada de um comando enquanto com dois traços é o comando "por extenso".
>Uma outra razão é permitir distinguir uma opção, constituída por vários caracteres, de uma sequência de opções. Se 'merged' fosse escrita com um traço seria interpretada como ```-m-e-r-g-e-d```. Um exemplo disso é o comando ```git commit -am "blabla"``` que executa o ```add (a)``` e atribui uma ```mensage (m)``` ao commit.

__help:__ - ao adicionar o comando "help" depois de um comando, abre-se a lista de opções desse comando.
_Ex:_
~~~
git comando --help
~~~
ou
~~~
git comando -h
~~~

__git --version:__ mostra se o Git está instalado e sua versão

__git init:__ - para iniciar um repositório, levando em consideração TODOS os arquivos e pastas dentro do diretório. É criada uma pasta _.git_, geralmente oculta.

__git status:__ - mostra a situação do projeto.

__git add:__ - adiciona os arquivos para trabalho, fazendo que sejam localizados pelo Git quando utilizamos o comando _git status_.
_Ex:_
~~~
git add "nome-do-arquivo.extenção"
~~~

Para adicionar todos os arquivos do diretório utiliza-se a seguinte sintaxe:
~~~
git add -A
~~~
A letra "A" deve ser maiúscula. Para ver todas as opções do comando _git add_. 

__git rm:__ - para excluir arquivos da branch.
_Ex:_
~~~
git rm "nome-do-arquivo.extenção"
~~~

Para forçar a deleção, também do diretório acrescentamos ```--comando```
~~~
git rm --comando <file>
~~~
> Ao usar ```git rm --cached "nome-do-arquivo.extenção"```, removemos do histórico de edições. para mais funcionalidades ```git rm help```.

__git commit:__ - é oque, de fato, realiza as alterações do projeto. É de boas práticas realizar um commit junto de um comentário pertinente aos trabalhos realizados no projeto.
_Ex:_
~~~
git commit -m "Comentário relevante"
~~~
> A função ```-m``` é utilizada para inserir um comentário ao commit. Se for usado apenas ```git commit``` é necessário escrever um comentário e outros comandos, que honestamente, não consegui executar, nem fazer funcionar. Talvez pela versão do Git, ou do Cmder, serem diferentes dos usados nas vídeo-aulas. Para mais funções do 'git commit help'.
>Utilizando o comando 'git commit -am "Comentário relevante"' adicionamos diretamente os arquivos não commitados, como se usássemos o comando 'git add -A' junto do 'git commit -m'

__git log:__ - retorna os commits feitos, com um código hash, a branch onde o commit foi realizado, dados como autor, data, etc e a mensagem do commit. 
_Ex:_
~~~
git log
~~~

__git branch:__ mostra com um asterisco na branch que estamos.
> Para criação de uma nova branch usamos o comando 'git branch <nomedabranch>'. Este comando irá copiar toda a branch a partir da qual está sendo criada.

Usando o comando ```-D``` podemos eliminar uma branch criada localmente.
_Ex:_
~~~
git branch -D "nome-da-branch"
~~~

---

**_GIT 02 - Título a ser decidido_**

__git reset:__ utilizado para reverter alterações em uma branch.
>Utiliza-se todo o código hash do commit, ou seus sete primeiros dígitos. 

Existem 3 tipos de 'reset', são eles: soft, mixed e hard.

**-** _Soft reset:_ é tulizado para retornar as edições para o commit desejado, mantendo os arquivos, e as edições feitas posteriormente, sem comitá-los. 
~~~
git reset --soft <hash do commit>
~~~
>Ao fazer um novo commit, os arquivos e edições posteriores ao commit que retornamos à ele, deixaram de existir, sendo substituídos pelo novo commit.

**-** _Mixed reset:_ é semelhante ao Soft Reset, a única diferença é que os arquivos não estarão prontos para comitar, será necessário executar a adição dos arquivos e alterações.
~~~
git reset --mixed <hash do commit>
~~~
**-** _Hard Reset:_ elimina TUDO que foi feito após o commit que desejamos retornar para ele.
~~~
git reset --hard <hash do commit>
~~~
>Não recomendado no uso em trabalhos de equipe.

__git checkout:__ usado para mudar para a nova branch.
>__ATENÇÃO!__ Aparentemente, se realizar o checkout sem commitar as alterações pendentes de commit, elas são sobrescritas e você as perde. lembre-se de conferir isso, geralmente o terminal nos lembra de fazer isso.
_Ex:_
~~~
git checkout <branch de destino>
~~~
>Podemos usar o _git checkout_ para retornar as alterações de um arquivo.
_Ex:_
~~~
git checkout HEAD -- <file>
~~~
>O comando _HEAD_ substitui o nome da branch atual, enquanto o duplo hífen, seguido de espaço, indica que o que vier depois será o nome de um arquivo.

__git diff:__ - para verificar quais alterações foram feitas.
_Ex:_
~~~
git diff
~~~
> Ele irá mostrar todos as linhas que foram alteradas.
>P.s1: Ele não mostra onde foi feita a alteração, é necessário analisar e comparar para identificar as alterações.
> O _git diff_ irá mostrar TODOS os arquivos modificados.

Para mostrar apenas os títulos dos arquivos basta usar o comando '--name-only'.
_Ex:_
~~~
git diff --name-only
~~~

Para mostrar as alterações de um único arquivo da branch, entre os que foram alterados, basta acrescentar o nome do arquivo.
_Ex:_
~~~
git diff <file>
~~~


---

**_GIT 03 - Git quem?_**

Vamos ver agora como criar um repositório remoto. Repositórios remotos são os repositórios em um servidor Git como o [GitHub](https://github.com), [GitLab](gitlab.com), [BitBucket](https://bitbucket.org), [SourceForge](https://sourceforge.net), [Launchpad](https://launchpad.net), [Apache Allura](https://allura.apache.org) e etc.

Não tem necessidade de explicar que é preciso ter uma conta em um serviço de repositório Git, como os citados a cima. Caso não tenha, basta se cadastrar em um serviço de repositório de sua preferência. 


1. Para criar um repositório no Git Hub é preciso:
	- Ir no canto superior direito, ao lado da foto do usuário, clicar no botão de mais e em seguida em _New repository_. Ou procurar isso em algum canto da tela.
	- Adicionar um nome para o repositório, sem letras maiúsculas e caracteres especiais, uma descrição e definir se ele será público ou privado.
	- Escolhe-se criar um arquivo README ou não. É possível acrescentar um arquivos README manualmente e enviar para o repositório.
	- Escolhe-se, também, acrescentar ou não a licença do seu projeto, casa ela exista.
	- .gitignore Lorem ipsum dolor sit amet.
	- Tendo feito estes passos, basta clicar em _Create repository_
	- Será criado uma url para o repositório.
	_Ex:_
~~~ 
 https://github.com/usuario/nome-do-repositorio.git
~~~

2. Para criar uma conexão entre um repositório local é necessário:
	- Clicar na foto de perfil > settings > SSH and GPG keys > New SSH key
	- Em seguida criasse um título para o repositório e colamos a chave pública gerada no _Git Bach_.

3. Para criar as chaves públicas e privadas é necessário ter o _Git Bach_ "instalado", que nada mais é do que um terminal próprio do Git.

Ao instalar o Cmder, o _Git Bach_ é instalado automaticamente. É possível entrar no site oficial do _Git_ e baixá-lo para o computador ou procurar por "Git Bach" no Google e fazer o download do arquivo. 

Será necessário procurar um tutorial de como instalar pq eu honestamente não faço a puta.

4. Depois de instalar o _bach_, vá até o terminal e digite o código:
~~~
ssh-keygen -t rsa -b 4096 -C "seu@email.com"
~~~
>É necessário que seja o mesmo email usado no cadastro do Git Hub
>Insira, ou não, uma senha. Confirme a senha, caso tenha colocado uma, e em seguida dê enter.

5. No diretório, indicado pelo terminal, procure as chaves e abra a chave pública no seu editor de códigos. Copie o código da chave pública e cole na área indicada pelo seu servidor Git.
	6. Na opção 'Settings' do servidor, procure pela opção 'SSH and GPG keys' e clique em 'New SSH key'.
	7. Na área indicada cole a chave SSH pública e e confirme a ação. Ao fazer isto, você estará pronto pra enviar seus projetos do seu repositório Git local, para seu repositório Git remoto.

---


**-Mais comandos Git**

__git remote:__ - é o repositório remoto, ou seja, o repositório criado no _Git Hub_.
_Ex:_
~~~
git remote add origin https://github.com/usuario/repositorio.git
~~~
>Comumente usasse o nome **origin** para o repositório.
>Para adicionar um repositório local em um repositório remoto usamos o comando ```add origin "url-do-diretorio.git"```.
>O comando ```remote -v``` mostra as opções do repositório. Normalmente os comandos possíveis são _fetch_ e _push_.

- O comando _fetch_ traz as alterações de uma branch no repositório remoto para o repositório local. Por exemplo, se um dev está no Japão, usamos o comando _fetch_ para trazer suas alterações no projeto para nossa máquina local.
_Ex:_
~~~
git fetch
~~~
- Já o comando _push_ envia às alterações para o repositório remoto.
_Ex:_
~~~
git push -u origin master
~~~

Para remover um branch remoto, também utilizamos o comando _push_, colocando o sinal de dois pontos antes do nome da branch que desejamos eliminar.
_EX:_
~~~
git push origin :"nome-da-branch"
~~~
>Desta forma, é possível eliminar também, arquivos, diretórios, tags e etc.

__git ignore:__ usado para ignorar algum arquivo ou pasta. Para isso, basta criar um arquivo chamado .gitignore e nele colocar o nome dos aruiqvos, com extenção, para que ele seja ignorado quando executar adiçõs e commits.
__Ex:__ 
~~~
título.html
*.sql
diretório/
~~~
>O GitHub possuí um repositório com gitignores mais populares, [neste link aqui](https://github.com/github/gitignore).

__git revert:__ é utilizado no lugar do ~git reset~ para não perder as funcionalidades commitadas. ao usar o 'revert' ainda temos acesso ao commit feito errado. 
>O salvador das sextas-feiras. Sem ele, não sextarás!

Para voltar o commit sem perder o código, usamos o comando 'git log' e copiamos o hash do commit que desejamos desfazer
__Ex:__
~~~
git revert --no-edit "hash do commit"
~~~
>Caso não seja usado o comando ```--no.edit```, o programa registrado na configuração do Git irá abrir com o código a ser editado.

__git pull:__ para trazer os arquivos e commits remotos, que foram adicionados por outros usuários, para o git local.
_Ex:_
~~~
git pull origin "nome-da-branch"
~~~
>Sempre faça um ```pull``` antes do ```push```. 

---

**_GIT_ 04 - Soyuz nerushimy respublik svobodnykh
Splotila naveki velikaya Rus'!**

É aqui que o comunismo se torna ferramenta das grandes empresas ~~capitalsitas~~ de tecnologia!

Uma das principais funções do Git, se não a principal, na minha opinião fecal, é colaborar projetos de outros devs e permitir que outros devs colaborem com os nossos projetos. obviamente um projeto em sigilo de uma empresa nunca estará aberto para colaboração, ou replicação. Porém, os projetos estando abertos para colaboração, ou não, os processos colaborativos e práticos são os mesmos. 

Vejamos agora como realizar as duas principais funções para colaboração e trabalho em equipe.

__git clone:__ simplesmente, clona um projeto de um repositório remoto para o repositório local. Basta copiar a url do repositório que deseja clonar, entrar no diretório destino, através do terminal, e utilizar o comando.
_Ex:_
~~~
git clone "url-do-repositório-remoto.com"
~~~
>Esse processo permite ter acesso à commits feitos no projeto, pulls e etc. É possível comitar e fazer edições no projeto, localmente. para realização de pushes e contribuições é ecessário realizar um ```fork```.

__fork e merge:__ o _fork_ é usado para podermos colaborar com um projeto. Os passos para realização do fork são:

1. Na página de um repositório, procure o botão **_"Fork"_** e clique nele.
>Ao fazer isso, um novo repositório será criado na sua própria conta, com uma indicação mostrando apartir de qual projeto o repositório foi forkado;

2. Em seguida realize o processo de clonagem com o comando ```git clone```, utilizando a url do repositório remoto criado na sua prórpia conta;

3. Realize as alterações desejadas. Corrija bugs, crie novas funcionalidades, melhore as linhas de código... go nuts;

4. Realize todos os processos já aprendidos de adição, commit, etc e então realize o push para o seu repositório remoto com o projeto. 
>Não se esqueça de conferir em qual branch e em qual servidor está o projeto utizando o comando ```git remote -v```;

5. Confira se tudo está dentro do que foi demandado e em seguida clique em **_"New pull request"_**;

6. Verifique o destinatário, em **_"base fork"_** e se o projeto enviado está correto em **_"head fork"_** e em seguida clique em **_"Create pull request"_**;

7. Na página que se abrirá, _"Open a pull request"_, e redija sua argumentação, defendendo o pq de suas alterações devem ser aceitas. Ao confirmar, basta esperar a resposta dos responsáveis pelo projeto. Se aceito, suas alterações serão agregadas ao projeto original, o que chamamos de _merge_;

---

**GIT EXTRA**
---

**_GIT Extra 01_**

**- Comandos básicos do Git**

__git-credentials:__ para detalhes [clique aqui](https://www.udemy.com/course/curso-completo-de-git/learn/lecture/6886902#overview).

---

__git tag:__ Coloca marcas no "código", marcando o ```commit```.

No GuitHub vá até sua _branch maste_ e clique em um _releases_, escolha seu seu release, ou crie um novo clicando em **create new release**, e bastar colocar um nome e uma descrição e clique em **Publishe Target**. Geralmente usado para marcar o último commit.

Quando um ```git fetch```for realizado, as tagas serão exibidas.

~~~
git tag 1.1

git push --tags
~~~

>```git tag 1.1``` cria a tag e o ```git push --tags``` realiza o push da tag.

---

__git clear:__ limpa a tela.

---

