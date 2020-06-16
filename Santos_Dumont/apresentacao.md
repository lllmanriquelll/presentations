<h1 align="center"> Webinar - Cluster Santos Dumont </h1>
<h2 align="center"> Acesso e submissão de jobs </h2>
   
| ![Santos Dumont](images/sd.jpg) | 
|:--:| 
| Fonte da imagem: https://itforum365.com.br/lncc-e-coppe-abrem-chamada-para-uso-de-supercomputadores/ |

## Sumário
1. [Introdução ao cluster Santos Dumont](#introducao)
    * [Hardware](#hardware)
    * [Filas](#filas)
    
1. [Projeto CADASE](#cadase)
    * [Tempo de computação](#tempo)
    * [Prazo para o uso](#prazo)
    * [Cotas](#cotas)
    
1. [Requisitos de acesso](#requisitos)
    * [Ativação da conta](#ativacao)
    * [Acesso VPN](#acesso)
    1. [Recomendações de ferramentas](#recomendacoes)
        * [Screen](#screen)
        * [Vim](#editor)

1. [Entendendo as partições dos discos](#particoes)
    * [/home](#home)
    * [/prj](#prj)
    * [/scratch](#scracth)

1. [Transferência de dados](#transferencia)
    * [Enviando arquivos](#envio)
    * [Recebendo arquivos](#recebimento)

1. [Module](#module)
    * [module avail](#)
    * [module load](#)
    * [module unload](#)
    * [module purge](#)

1. [Compilando código C/C++](#)
    * [Carregando os módulos necessários](#)
    * [Encontrando módulos necessários a partir de erros na compilação](#)

1. [Compilando código C/C++ com openMP e openMPI](#)
    * [Carregando os módulos necessários](#)

1. [SLURM](#)
    * [Comandos básicos](#)
        * [sinfo](#)
        * [squeue](#)
        * [scancel](#)
    * [Alocando recursos](#)
        * [srun](#)
        * [sbatch](#)
    * [Filas do SLURM](#)
    
1. [srun - Shell em modo interativo e jupyter notebook](#)
    * [Rodando um script em python](#)
    * [Acessado o jupyter notebook remotamente](#)
  
1. [Submissão de jobs](#)
    *[Rodando um código C com openMP](#)
    *[Rodando um código C com MPI](#)
