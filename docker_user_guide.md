Guia do usuário do Docker
É assim que se usa o Docker escrito para quem usa o Docker.

Guia de instalação do Docker
Introdução e guia do Docker - Sang-Jun Oh

Instruções após a instalação do Docker
Executando o Docker pela primeira vez
Após executar o Docker Terminal, memorize o IP da imagem abaixo!

Usaremos esse IP para nos comunicarmos com o contêiner do Docker no futuro.

imagem

Baixar imagem do docker
Obtenha a imagem do docker em hub.docker e prepare o contêiner para uso. (Pode ser necessário fazer login. Inscreva-se em https://hub.docker.com !)

$ docker pull deeplearningzerotoall/pytorch
Se você quiser especificar uma versão diferente, conecte-se ao nosso hub docker e verifique a versão desejada.

Após receber a imagem, execute o comando para verificar a existência da imagem do Docker docker images.

$ docker images
REPOSITORY				TAG	...
hello-world				latest	... 
deeplearningzerotoall/pytorch		latest	...
Executando contêineres de imagens do docker e desligá-los
Crie e execute um contêiner de uma imagem do docker. Neste ponto --name, você pode definir qualquer nome que desejar. Neste guia, ptvamos

$ docker run -i -t --name pt -p 8888:8888 -p 8097:8097 deeplearningzerotoall/pytorch /bin/bash
Estamos quase lá. Você criou um contêiner docker e se conectou ao shell interno do contêiner com a conta root.

root@[고유번호]:~#
Se você quiser desligar completamente o container, exitbasta digitar o comando!

root@[고유번호]:~# exit
docker ps -aVocê pode usar o comando para verificar se o contêiner do Docker está em execução no momento. Verificar ESTADO

$ docker ps -a
O contêiner do Docker se move livremente
Nota : docker runVocê só precisa executar o comando uma vez. Para executar o contêiner encerrado novamente, execute da seguinte maneira.

$ docker start pt
Essa etapa só fez o container crescer. Execute o seguinte para se conectar ao terminal de contêiner. Isso o levará a um terminal dentro do contêiner.

$ docker attach pt
root@[고유번호]:~#
Se você quiser deixar o container ligado e sair um pouco , use Ctrl+P+ Ctrl+Q. Da mesma forma, você pode usar o comando para reconectar docker attach.

Fork e Git Clone para estudar
Agora, para começar a estudar de verdade, acesse o Deep Learning Github para todos .

ForkFaça login na sua conta do Github e clique no botão no canto superior direito, conforme mostrado na imagem abaixo .

imagem

ForkDepois de concluído, vá para seus repositórios (depois de clicar na imagem do perfil no canto superior direito, Seus repositórios), um repositório bifurcado é criado a partir deste github.

imagem

Clique no repositório relevante para acessá-lo Clone or downloade pressione o botão verde para copiar ou memorizar o link abaixo.

imagem

Volte para dentro do contêiner do Docker novamente git clonee cole ou digite o link copiado junto com o comando.

root@[고유번호]:~# git clone https://github.com/[github계정이름]/PyTorch.git
Quando terminar, agora vá para o diretório PyTorch.

root@[고유번호]:~# cd PyTorch
root@[고유번호]:~/PyTorch# 
Instale os pacotes necessários.

root@[고유번호]:~/PyTorch# pip install --upgrade pip
root@[고유번호]:~/PyTorch# pip install -r requirements.txt
Estamos quase lá. jupyter notebookBasta executá-lo agora .

root@[고유번호]:~/PyTorch# jupyter notebook --ip 0.0.0.0 --allow-root
Para aqueles que se incomodam em digitar o comando acima todas as vezes, eu o transformei em um script de shell.

root@[고유번호]:~/PyTorch# sh run_jupyter_docker.sh
jupyter notebookDepois de executar pela primeira vez, um token longo é criado no terminal docker, conforme mostrado na imagem abaixo. Copie o token.

imagem

Agora, na janela da Internet, digite ' usando o endereço IP fornecido ao executar o Docker pela primeira vez [IP주소]:8888. Em seguida aparecerá a tela abaixo.

imagem

Insira o token que você copiou anteriormente. Se esta é a primeira vez que você o executa, você também pode definir uma senha. É recomendável configurá-lo, pois você só precisa digitar a senha na próxima vez que se conectar.

jupyter notebookPara sair, retorne Ctrl+cao terminal do Docker e pressione duas vezes para sair.

Todos os guias estão agora completos. Espero que estude bastante! :)
