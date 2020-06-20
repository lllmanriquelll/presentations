<h1 align="center"> Webinar - Cluster Santos Dumont </h1>
<h2 align="center"> Acesso e submissão de jobs </h2>
   
| ![Santos Dumont](images/sd.jpg) | 
|:--:| 
| Fonte da imagem: https://itforum365.com.br/lncc-e-coppe-abrem-chamada-para-uso-de-supercomputadores/ |

## Sumário

1. [Introdução ao cluster Santos Dumont](#introducao)

   - [Hardware](#hardware)
   - [Filas](#filas)

1. [Projeto CADASE](#cadase)

   - [Prazo para o uso](#prazo)
   - [Tempo de computação](#tempo)
   - [Cotas de disco](#cotas)
   - [Softwares do projeto](#software)
   - [Canais de Suporte](#suporte)

1. [Requisitos de acesso](#requisitos)

   - [Ativação da conta](#ativacao)
   - [Acesso VPN](#acesso_vpn)
   - [SSH Client](#client)

1. [Acessando o Santos Dumont](#acesso)

1. [Recomendação de ferramentas](#recomendacoes)

   - [Screen](#screen)
   - [Vim](#editor)
   - [SSHFS](#sshfs)

1. [Entendendo as partições dos discos](#particoes)

   - [/home](#home)
   - [/prj](#prj)
   - [/scratch](#scracth)

1. [Transferência de dados](#transferencia)

   - [Enviando arquivos](#envio)
   - [Recebendo arquivos](#recebimento)

1. [Module](#module)

   - [module avail](#)
   - [module load](#)
   - [module unload](#)
   - [module purge](#)

1. [Compilando código C/C++](#compilacao1)

   - [Carregando os módulos necessários](#)
   - [Encontrando módulos necessários a partir de erros na compilação](#)

1. [Compilando código C/C++ com openMP e openMPI](#compilacao2)

   - [Carregando os módulos necessários](#)

1. [SLURM](#slurm)

   - [Comandos básicos](#)
     - [sinfo](#)
     - [squeue](#)
     - [scancel](#)
   - [Alocando recursos](#)
     - [srun](#)
     - [sbatch](#)
   - [Filas do SLURM](#)

1. [srun - Shell em modo interativo e jupyter notebook](#srun)

   - [Rodando um script em python](#)
   - [Acessado o jupyter notebook remotamente](#jupyter)

1. [sbatch - Submissão de jobs](#sbatch)
   - [Rodando um código C com openMP](#)
   - [Rodando um código C com MPI](#)

## Introdução <a name="introducao"></a>

**Breve Histórico**

O supercomputador Santos Dumont (SDumont), adquirido junto a empresa francesa ATOS/BULL, está localizado na sede do Laboratório Nacional de Computação Científica (LNCC), em Petrópolis-RJ, atuando como nó central (Tier-0) do Sistema Nacional de Processamento de Alto Desempenho - SINAPAD.

A primeira versão do SDumont (2015), chamada de "SDumont Base", possuía um total de 18.424 núcleos de CPU, distribuídos em 758 nós computacionais utilizando a tecnologia BullX B700. <br> No quarto trimestre de 2019 o SDumont recebeu uma expansão computacional, composta da tecnologia BullSequana X, que aumentou o poder computacional de 1,1 Petaflops para 5,1 Petaflops. Após essa expansão o SDumont passou a contar com um total de 34.688 núcleos de CPU, distribuídos em 1132 nós computacionais.

### Hardware <a name="hardware"></a>

<div align="center">
<table class="tg">
<thead>
  <tr>
    <th class="tg-7btt">Qtd. de nós</th>
    <th class="tg-7btt">Processador</th>
    <th class="tg-7btt">Número de cores por nó</th>
    <th class="tg-7btt">Memória</th>
    <th class="tg-7btt">Acelerador</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-c3ow">504</td>
    <td class="tg-c3ow">2 x Intel Xeon E5-2695v2</td>
    <td class="tg-c3ow">24</td>
    <td class="tg-c3ow">64GB</td>
    <td class="tg-c3ow"></td>
  </tr>
  <tr>
    <td class="tg-c3ow">198</td>
    <td class="tg-c3ow">2 x Intel Xeon E5-2695v2</td>
    <td class="tg-c3ow">24</td>
    <td class="tg-c3ow">64GB</td>
    <td class="tg-c3ow">1 x NVIDIA K40</td>
  </tr>
  <tr>
    <td class="tg-c3ow">54</td>
    <td class="tg-c3ow">2 x Intel Xeon E5-2695v2</td>
    <td class="tg-c3ow">24</td>
    <td class="tg-c3ow">64GB</td>
    <td class="tg-7btt">1 x Xeon Phi 7120</td>
  </tr>
  <tr>
    <td class="tg-c3ow">1</td>
    <td class="tg-c3ow">16 x Intel Xeon Ivy Bridge</td>
    <td class="tg-c3ow">240</td>
    <td class="tg-c3ow">6TB</td>
    <td class="tg-c3ow"></td>
  </tr>
  <tr>
    <td class="tg-c3ow">246</td>
    <td class="tg-c3ow">2 x Intel Xeon Skylake 6152</td>
    <td class="tg-c3ow">48</td>
    <td class="tg-c3ow">384GB</td>
    <td class="tg-c3ow"></td>
  </tr>
  <tr>
    <td class="tg-c3ow">36</td>
    <td class="tg-c3ow">2 x Intel Xeon Skylake 6152</td>
    <td class="tg-c3ow">48</td>
    <td class="tg-c3ow">768GB</td>
    <td class="tg-c3ow"></td>
  </tr>
  <tr>
    <td class="tg-c3ow">94</td>
    <td class="tg-c3ow">2 x Intel Xeon Skylake 6152</td>
    <td class="tg-c3ow">48</td>
    <td class="tg-c3ow">384GB</td>
    <td class="tg-c3ow">4 x NVIDIA V100</td>
  </tr>
  <tr>
    <td class="tg-c3ow">1</td>
    <td class="tg-c3ow">2 x Intel Xeon Skylake 6148</td>
    <td class="tg-c3ow">40</td>
    <td class="tg-c3ow">384GB</td>
    <td class="tg-c3ow">8 x NVIDIA V100</td>
  </tr>
</tbody>
</table>
</div>

### Filas <a name="filas"></a>

Os equipamentos do cluster Santos Dumont listados acima representam um valioso recurso computacional, que é compartilhado por diversos grupos de pequisas que possuem vínculo com o Laboratório Nacional de Computação Científica. Para manter os recursos disponíveis para todos os pesquisadores de forma consistente e justa, foi implementado um sistema de filas.

Em um computador não compartilhado, o usuário que define as prioridades de execução e pode rodar os programas diretamente em seu terminal ou gerenciador de janelas, no caso do SDumont, o usuário precisa criar um script e submetê-lo para uma fila (SLURM), que vai determinar em que momento o código entrará em execução, essa etapa extra será detalhada mais a frente.

---

---

## Projeto CADASE <a name="cadase"></a>

### Prazo para o uso <a name="prazo"></a>

Prazo de 6 meses a contar a partir de junho de 2020.

### Tempo de computação <a name="tempo"></a>

Unidades de Alocação (UAs) ~5.000.000

- 1,0 UA é igual a 1 (uma) hora de processamento em 1 (um) núcleo de
  processamento do nó com CPU

- Uma hora de processamento em 1 (um) núcleo dos nós com CPU+GPU
  corresponde à 1,5 UA

- Uma hora de processamento em 1 (um) núcleo de MESCA2 ou GDL-IA
  corresponde à 2,0 UAs

Com essa cota de processamento, nós poderíamos utilizar 45 nós CPU com ocupação de todos os cores, 24 horas por dia, e não chegaríamos ao limite antes do prazo de seis meses, portanto, utilizem o recurso sempre que possível.

### Cotas de disco <a name="cotas"></a>

O espaço em disco é limitado, temos acesso a duas partições com cotas:

- /prj 25TB (a confirmar)
- /scracth 25TB

### Softwares do projeto <a name="software"></a>

Os softwares do projeto estão localizados no diretório **_/scratch/cadase/app_**

Segue abaixo a lista de sotwares instalados até o momento:

      anaconda3
      devito
      firedrake
      htop
      openfoam
      scripts (exemplos do slurm e carregamento dos softwares do projeto)
      singularity (ainda não está funcional)

### Canais de Suporte <a name="suporte"></a>

Lista de e-mail do google groups

- cadase-members@googlegroups.com

Canal Slack

- http://cadasemembers.slack.com

Help Desk do LNCC

- helpdesk-sdumont@lncc.br

---

---

## Requisitos de acesso <a name="requisitos"></a>

### Ativação da conta <a name="ativacao"></a>

Entrar em contato com a equipe do Helpdesk do LNCC através do telefone (24) 2233-6050 e informar o número do seu atendimento, localizado no campo "assunto" da mensagem de e-mail confirmando a criação da sua conta.

### Acesso VPN <a name="acesso_vpn"></a>

Configurar um cliente VPN, abaixo segue um exemplo no ambiente Ubuntu:

<ol>

<br><li>Abra o menu de configuração no canto superior direito.</li><br>

<center>
<img src="images/vpn/1_vpn.png" width="460" height="450" />
</center>

<br><li>Clique no símbolo <b>+</b> para adicionar uma nova conexão.</li><br>

<center>
<img src="images/vpn/2_vpn.png" width="650" height="450" />
</center>

<br><li>Selecione o <b>Cisco Compatible VPN</b>.</li><br>

<center>
<img src="images/vpn/3_vpn.png" width="650" height="450" />
</center>

<br><li>Adicione as credenciais enviadas pelo helpdesk do LNCC.
Para adicionar a senha do grupo, selecione <b>Store password ...</b>.</li><br>

<center>
<img src="images/vpn/4_vpn.png" width="650" height="450" />
</center>

<br><li>Selecione connect para estabelecer a conexão VPN.</li><br>

<center>
<img src="images/vpn/5_vpn.png" width="460" height="450" />
</center>

</ol>

### SSH Client <a name="client"></a>

---

---

## Acessando o Santos Dumont <a name="acesso"></a>

<ol>

<br><li>Se conecte à rede VPN.</li><br>

<center>
<img src="images/acesso/1_vpn.png" width="890" height="450" />
</center>

<br><li>Estabeleça a conexão via ssh com: <b><i>ssh user@login.sdumont.lncc.br</i></b></li><br>

<center>
<img src="images/acesso/2_ssh.png" width="890" height="550" />
</center>

</ol>

---

---

## Recomendação de ferramentas <a name="recomendacoes"></a>

### Screen <a name="screen"></a>

Quando estamos trabalhando em tarefas de longa duração em máquinas remotas, alguns problemas podem ocorrer: queda na conexão de internet; desconexão da sessão ssh; travamentos, entre outros. Quando algum desses problemas ocorre, o nosso trabalho é perdido.

Para evitar esse tipo de situação, podemos usar a ferramenta Screen ou GNU Screen, que é um multiplexador de terminais, ele serve para que possamos iniciar uma sessão do screen dentro do terminal convencional, e nele criamos terminais virtuais, que podem continuar rodando mesmo quando estamos deconectados. Podemos deixar algo rodando no terminal do cluster, desconectar e voltar algum tempo depois para retomar do mesmo ponto em que paramos.

    screen #Comandos básicos

    #Lista as sessões
    screen -ls

    #Cria uma nova sessão com o nome "minha-sessao"
    screen -S "minha-sessao"

    #Se vincula a uma sessão existente de nome "minha-sessao"
    screen -x minha-sessao

    Comandos dentro do screen

    Ctrl+A -> c      #Cria um novo terminal

    Ctrl+A -> "      #Lista todos os terminais da sessão

    Ctrl+A -> 0      #Alterna para o terminal 0

    Ctrl+A -> A      #Renomeia o terminal

    Ctrl+A -> S      #Divide a tela horizontalmente em duas regiões

    Ctrl+A -> |      #Divide a tela verticalmente em duas regiões

    Ctrl+A -> tab    #Alterna o foco nas regiões

    Ctrl+A -> X      #Fecha a região em foco

    Ctrl+A -> Q      #Fecha todas as regiões menos a que tem o foco

    Ctrl+A -> Ctrl+a #Alterna o terminal

    Ctrl+A -> d      #Desvincula o seu terminal da sessão

### Vim <a name="editor"></a>

Trabalhando no ambiente de linha de comando do cluster, muitas vezes será necessário abrir arquivos para leitura e eventualmente para edições, dessa forma, se faz necessário ter o conhecimento de algum editor de textos no terminal. Abaixo eu apresento alguns comandos básicos do Vim, um dos editores mais populares do Linux.

      Vim #Comandos básicos

      vim arquivo.txt    #Abre o arquivo.txt, caso não ele não exista, um novo será criado


      Abrir e salvar arquivo

      Esc
      :w     #Salva o arquivo
      :q     #Sai do editor
      :wq!   #Salva e sai do editor


      Busca

      Esc
      /word     #Procura a palavra word de cima para baixo
      ?word     #Procura a palavra word de baixo para cima
      /jo[ha]n  #Procura por john ou joan
      /\< the   #Procura por the, theatre ou then


      Substituição

      Esc
      :%s/old/new/g      #Substitui todas as ocorrência de old por new
      :%s/old/new/gw     #Substitui todas as ocorrência de old por new com confirmação
      :2,35s/old/new/g   #Substitui todas as ocorrência de old por new entre as linhas entre 2 e 35
      :5,$s/old/new/g    #Substitui todas as ocorrência de old por new da linhas 5 até o final do arquivo
      :%s/^/hello/g      #Insere hello no início de cada linha


      Outros

      Esc
      :syntax on         #Ativa o modo de exibição de cores de sintaxe
      :set number        #Exibe o número da linha
      :set autoindent    #Ativo o modo de identação automática
      :set shiftwidth=4  #Configura o tamanho da identação

### SSHFS <a name="sshfs"></a>

O SSHFS (Secure Shell FileSystem), é uma ferramenta que permite os usuários acessarem de forma segura um sistema de arquivos remoto, no exemplo a seguir iremos acessar os diretórios da sua conta no SDumont. Esse método é considerado seguro pois a comunicação se dá através do protocolo SSH.

Uma vez estabelecida a conexão, é possível utilizar ferramentas da sua interface gráfica para manipular os arquivos.

<ol>

<br><li>Instalando o SSHFS no seu computador:</li><br>

      sudo apt-get install sshfs

<br><li>Criando o diretório que servirá para acessar os dados do SDumont:</li><br>

      sudo mkdir ~/sdumont-fs

<br><li>Estabelecendo a conexão:</li><br>

      sudo sshfs luis.manrique@login.sdumont.lncc.br: ~/sdumont-fs

<br><li>O diretório remoto deve aparecer no Natilus conforme a imagem abaixo:</li><br>

<center>
<img src="images/sshfs/1_sshfs.png" width="400" height="550" />
</center>

<br><li>Desconectando do cluster:</li><br>

      sudo umount ~/sdumont-fs

</ol>

---

---

## Entendendo as partições dos discos <a name="particoes"></a>

---

---

## Transferência de dados <a name="transferencia"></a>

---

---

## Module <a name="module"></a>

---

---

## Compilando código C/C++ <a name="compilacao1"></a>

---

---

## Compilando código C/C++ com openMP e openMPI <a name="compilacao2"></a>

---

---

## SLURM <a name="slurm"></a>

---

---

## srun - Shell em modo interativo e jupyter notebook <a name="srun"></a>

---

---

### Rodando um script em python

---

---

### Acessado o jupyter notebook remotamente <a name="jupyter"></a>

<ol>

<br><li>Utilize o comando <b><i>srun</i></b> para alocar o node que será utilizado em modo interativo. <br> O parâmetro <b><i>-p</i></b> serve para identifcar a fila utilizada, o <b><i>--pty bash -i</i></b> identifca o tipo de shell da sessão que será retornada. <br> Outros parâmetros não utilizados aqui podem servir para requisitar uma quantidade específica memória, uso exclusivo do node, número de tasks (processos mpi), etc. Confira outros parâmetros e os tipos de máquinas de cada fila no manual do usuário.<br> Aproveite para guardar o hostname do node que foi alocado.</li><br>

<center>
<img src="images/srun/1_srun_hostname.png" width="890" height="550"  />
</center>

<br><li>Carregue o anaconda com <b><i>eval "\$(/scratch/cadase/app/anaconda3/bin/conda shell.bash hook)"</i></b>. Neste exemplo iremos utilizar o Devito como exemplo, para tanto carregaremos o ambiente com: <b><i>conda activate devito</i></b></li><br>

<center>
<img src="images/jupyter/1_anaconda_devito.png" width="890" height="550" />
</center>

<br><li>Inicialize o notebook com: <b><i>jupyter-lab --no-browser --ip=0.0.0.0</i></b></li><br>

<center>
<img src="images/jupyter/2_jupyter.png" width="890" height="550" />
</center>

<br><li>Abra um novo terminal e crie um túnel para acessar o notebook, utilize o hostname do node alocado anteriormente:<b><i> ssh -L 8888:hostname:8888 user@login.sdumont.lncc.br</i></b></li><br>

<center>
<img src="images/tunel/1_tunel.png" width="890" height="550" />
</center>

<br><li>Utilize o terminal com a sessão do jupyter notebook aberta para copiar a url e cole no browser como no exemplo abaixo:</li><br>

<center>
<img src="images/jupyter/3_jupyter_browser.png"/>
</center>
</ol>

---

---

## sbatch - Submissão de jobs <a name="sbatch"></a>

---

---
