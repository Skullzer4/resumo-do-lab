# resumo-do-lab
Este repositório contém o resumo das lições aprendidas durante o desenvolvimento do lab na DIO
Aprendemos as diferenças de nuvens (privada, hibrida, puplica e multi-cloud). 
Sobre versionamento na platafortma git e github e suas diferenças 
Overwiew sobre os menus da plataforma azure e criação de conta na plataforma.

# resumo-do-lab 2

Configurando Recursos e Dimensionamentos em Máquinas Virtuais no Azure
Ao criar uma Máquina Virtual (VM) no Azure, é possível configurar os recursos e o dimensionamento de acordo com as necessidades do seu ambiente. Veja os principais pontos:

1. Escolha do Tamanho (SKU da VM)
O tamanho da VM define a quantidade de:

vCPUs

Memória RAM

Capacidade de disco

Placa de rede

Azure oferece várias séries de VMs (ex: B, D, E, F, etc.), otimizadas para diferentes cargas de trabalho (uso geral, memória intensiva, computação, etc.).

2. Dimensionamento Vertical
Alterar o tamanho da VM (mais CPU/RAM) sem mudar o tipo de máquina.

Ex: mudar de uma D2s_v3 para D4s_v3.

3. Dimensionamento Horizontal (Escalabilidade)
Adicionar mais instâncias da VM com Azure Scale Set para distribuir carga automaticamente.

Ideal para aplicações web, APIs ou serviços que precisam lidar com picos de acesso.

4. Configuração de Disco
Escolha entre discos:

Standard HDD, Standard SSD, Premium SSD (desempenho e custo variam).

Pode adicionar discos de dados além do disco do sistema operacional.

5. Rede e Segurança
Configuração de:

Rede virtual (VNet)

Grupo de segurança de rede (NSG)

IP público ou privado

6. Monitoramento e Autoescala
Configurar Azure Monitor e alertas.

Definir regras de autoescala para ligar/desligar ou aumentar/diminuir recursos automaticamente.
