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

|    Acessar um jupyter notebook rodando no Santos Dumont    |
| :--------------------------------------------------------: |
|           ![Acesso VPN](images/acesso/1_vpn.png)           |
|                            :--:                            |
|           ![Acesso SSH](images/acesso/2_ssh.png)           |
|                            :--:                            |
|          ![srun](images/srun/1_srun_hostname.png)          |
|                            :--:                            |
| ![Anaconda + Devito](images/jupyter/1_anaconda_devito.png) |
|                            :--:                            |
|        ![jupyter-lab](images/jupyter/2_jupyter.png)        |
|                            :--:                            |
|             ![Túnel](images/tunel/1_tunel.png)             |
|                            :--:                            |
|      ![Browser](images/jupyter/3_jupyter_browser.png)      |
|                            :--:                            |

## sbatch - Submissão de jobs <a name="sbatch"></a>
