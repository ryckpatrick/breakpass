# Quebrar senha do Windows 10 com Prompt de Comando.

É necessário ter uma mídia de instalação seja ela pendrive ou CD.

Você vai acessar o ela como se fosse formatar a máquina, mas ao iniciar você clica em avançar e depois em reparar o computador.

Após isso soluções de problemas -> Opções avançadas -> Prompt de Comando

Abrindo o CMD você vai acessar o diskpart, pelo comando diskpart mesmo, em seguinda utiliza o comando list volume para descobrir aonde está a pasta do system32,
após pode sair utilizando o comando exit para sair apenas do diskpart.

~~~bash
diskpart
list volume
exit
~~~

Agora referenciar a letra do onde está instalado o Windows para acessar os diretorios. 

~~~bash
C:
cd windows
cd system32
~~~

Utilizaremos o comando ren e copy para fazer as altereções na facilidade de acesso da tela de bloqueio.

Acessando a pasta system32 pelos comandos informados vamos substituir o utilman com o comando 

~~~bash
ren utilman.exe utilmanoriginal.exe. 
~~~

Agora vamos copiar o cmd e renomear utilizando o seguinte comando

~~~~bash
copy cmd.exe utilman.exe.
~~~~

Para chegar se o passo deu certo vamos usar o comando dir util*, ele deverá mostrar que tem 3 arquivos.

~~~bash
dir util*
~~~

Aqui já pode sair do CMD e reniciar a máquina.

Quando a máquina iniciar pode apertar no atalho de facilidade de acesso que ja vai abrir o CMD na raiz do system32.

Uma vez aberto utilzar o comando

~~~bash
control userpasswords2.
~~~

Vai abrir a tela de usuários locais e você terá acesso para alterar a senha.

Para desfazer o atalho acesso o prompt novamente utilzando o a midia de instalação e chegar na pasta do system32, uma vez lá vamos deletar a cópia criada do cmd com o comando: del.

~~~bash
del utilman.exe
~~~

Agora vamos renomear o atalho da facilidade de acesso orginal de volta.

~~~bash
ren utilmanoriginal.exe utilman.exe
~~~
