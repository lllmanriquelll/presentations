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

   - [Tempo de computação](#tempo)
   - [Prazo para o uso](#prazo)
   - [Cotas](#cotas)

1. [Requisitos de acesso](#requisitos)

   - [Ativação da conta](#ativacao)
   - [Acesso VPN](#acesso)

   1. [Recomendações de ferramentas](#recomendacoes)
      - [Screen](#screen)
      - [Vim](#editor)

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
   - [Acessado o jupyter notebook remotamente](#)

1. [sbatch - Submissão de jobs](#sbatch)
   - [Rodando um código C com openMP](#)
   - [Rodando um código C com MPI](#)

## Introdução <a name="introduction"></a>

## Projeto CADASE <a name="cadase"></a>

## Requisitos de acesso <a name="requisitos"></a>

## Entendendo as partições dos discos <a name="particoes"></a>

## Transferência de dados <a name="transferencia"></a>

## Module <a name="module"></a>

## Compilando código C/C++ <a name="compilacao1"></a>

## Compilando código C/C++ com openMP e openMPI <a name="compilacao2"></a>

## SLURM <a name="slurm"></a>

## srun - Shell em modo interativo e jupyter notebook <a name="srun"></a>

### Rodando um script em python

### Acessado o jupyter notebook remotamente

<ol>
<li>Se conecte à rede VPN utilizando o manual do Santos Dumont enviado por e-mail pelo helpdesk.</li><br>

<center>
<img src="images/acesso/1_vpn.png" width="890" height="450" />
</center>

<br><li>Estabeleça a conexão via ssh com: <b><i>ssh user@login.sdumont.lncc.br</i></b></li><br>

<center>
<img src="images/acesso/2_ssh.png" width="890" height="550" />
</center>

<br><li>Utilize o comando <b><i>srun</i></b> para alocar o node que será utilizado em modo interativo. <br> O parâmetro <b><i>-p</i></b> serve para identifcar a fila que será utilizada, o <b><i>--pty bash -i</i></b> identifca o tipo de shell da sessão que sera retornada. <br> Outros parâmetros não utilizados aqui podem servir para requisitar uma quantidade específica memória, uso exclusivo do node, número de tasks (processos mpi), etc. Confira outros parâmetros e os tipos de máquinas de cada fila no manual do usuário.<br> Aproveite para guardar o hostname do node que foi alocado.</li><br>

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

<br><li>Abra um novo terminal e crie um túnel para acessar o notebook, utilize o hostname do node alocado anteriormente:<b><i>ssh -L 8888:hostname:8888 user@login.sdumont.lncc.br</i></b></li><br>

<center>
<img src="images/tunel/1_tunel.png" width="890" height="550" />
</center>

<br><li>Utilize o terminal com a sessão do jupyter notebook aberta para copiar a url e cole no browser como no exemplo abaixo:</li><br>

<center>
<img src="images/jupyter/3_jupyter_browser.png"/>
</center>
</ol>

## sbatch - Submissão de jobs <a name="sbatch"></a>
