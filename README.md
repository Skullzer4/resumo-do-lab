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

# resumo-do-lab 3

Armazenamento no Microsoft Azure
O Armazenamento no Azure é um conjunto de serviços escaláveis, duráveis e seguros usados para armazenar dados de forma eficiente na nuvem. Ele suporta diversos tipos de dados — estruturados, semiestruturados e não estruturados — e é amplamente utilizado em aplicações empresariais, backup, recuperação, arquivos, bancos de dados e análise de big data.

Principais Tipos de Armazenamento no Azure
1. Blob Storage (Armazenamento de Objetos)
Ideal para armazenar arquivos não estruturados como imagens, vídeos, backups, logs e documentos.
Blobs são armazenados em contêineres dentro de contas de armazenamento.
Suporta acesso via HTTP/HTTPS, Azure SDKs e AzCopy.
Classes de acesso:
Hot: acesso frequente.
Cool: acesso esporádico.
Archive: raramente acessado, custo muito baixo.

2. Azure Files (Compartilhamento de Arquivos)
Compartilhamento de arquivos via protocolo SMB (compatível com Windows e Linux).
Pode ser mapeado como unidade de rede em estações de trabalho ou VMs.
Útil para migração de servidores de arquivos locais para a nuvem.

3. Fila de Armazenamento (Azure Queue Storage)
Serviço de mensageria assíncrona.
Permite que diferentes componentes de uma aplicação troquem mensagens de forma desacoplada.
Cada mensagem pode ter até 64 KB.

4. Tabela de Armazenamento (Azure Table Storage)
Armazenamento de dados semiestruturados (NoSQL).
Ideal para grandes volumes de dados com esquema flexível e consulta rápida.
Substituído por Cosmos DB para aplicações mais modernas.

5. Discos do Azure (Azure Disks)
Usado como armazenamento persistente para máquinas virtuais (VMs).
Tipos:
Standard HDD (custo mais baixo)
Standard SSD
Premium SSD (alto desempenho)
Ultra Disk (baixa latência, IOPS elevado)

Modelos de Redundância de Dados
Para garantir alta durabilidade e disponibilidade, o Azure oferece diferentes modelos de replicação:

Tipo de Redundância	Localização das Cópias	Durabilidade
LRS (Locally Redundant Storage)	3 cópias no mesmo datacenter	11 noves (99,999999999%)
ZRS (Zone-Redundant Storage)	Cópias em zonas diferentes da mesma região	Alta
GRS (Geo-Redundant Storage)	Cópias em outra região	Muito alta
RA-GRS (Read-Access GRS)	Como o GRS, mas com leitura permitida da região secundária	Muito alta

Segurança e Gerenciamento de Acesso
Suporte a criptografia em repouso (Storage Service Encryption).
Controle de acesso via Azure AD, chaves SAS (Shared Access Signatures) e tokens OAuth.
Integração com Azure Monitor, Log Analytics e Azure Policy para governança e auditoria.

🛠️ Ferramentas de Acesso e Gerenciamento
Azure Portal: interface gráfica.
Azure CLI / PowerShell: automação via linha de comando.
AzCopy: utilitário para copiar dados entre locais e contas de armazenamento.
Storage Explorer: aplicativo de desktop para gerenciar recursos de armazenamento visualmente.

Cobrança e Preços
Os custos dependem de:
Tipo de armazenamento (Blob, Arquivo, Disco etc.)
Classe de acesso (Hot, Cool, Archive)
Capacidade utilizada
Tipo de redundância
Taxa de transações e saídas de dados

Casos de Uso Comuns
Backup e recuperação de desastres
Armazenamento de mídia
Aplicações empresariais baseadas em nuvem
Sistemas de arquivos compartilhados
Arquivamento de dados e compliance

# resumo-do-lab 4

Segurança e Identidade no Microsoft Azure
A segurança e identidade são pilares fundamentais da computação em nuvem. No Microsoft Azure, esses aspectos são tratados de forma integrada, com soluções avançadas para proteger dados, usuários, dispositivos, redes e aplicações, garantindo conformidade e mitigando riscos.

1. Princípios Fundamentais
Defesa em profundidade: estratégia que utiliza múltiplas camadas de segurança (identidade, rede, dados, etc.) para dificultar ataques.
Modelo de responsabilidade compartilhada: a Microsoft protege a infraestrutura da nuvem, e o cliente é responsável pela segurança dos recursos que implanta.
Zero Trust (Confiança Zero): nunca confiar por padrão; sempre verificar. Acesso é concedido com base em identidade, localização, dispositivo e risco.

2. Gerenciamento de Identidade – Microsoft Entra ID
Anteriormente conhecido como Azure Active Directory (Azure AD), o Microsoft Entra ID é a solução central de gerenciamento de identidade e acesso da Azure.
Funções principais:
Autenticação e login único (SSO)
Controle de acesso baseado em função (RBAC)
Suporte a autenticação multifator (MFA)
Acesso condicional baseado em local, dispositivo, risco de login
Integração com mais de 5.000 apps SaaS

3. Recursos de Segurança na Azure
Autenticação Multifator (MFA)
Adiciona uma camada extra de segurança exigindo uma segunda forma de autenticação (token, SMS, app).

Acesso Condicional
Controla o acesso com base em políticas como localização geográfica, grupo de usuários ou nível de risco.

Azure Key Vault
Armazena de forma segura segredos, chaves de criptografia e certificados usados por aplicações.

Microsoft Defender for Cloud
Oferece visibilidade, recomendações e proteção contra ameaças para recursos no Azure e em ambientes híbridos.

Azure Firewall e NSGs (Network Security Groups)
Permitem controlar o tráfego de rede para dentro e fora de sub-redes e máquinas virtuais.

Microsoft Sentinel
Uma solução SIEM/SOAR nativa em nuvem, para monitoramento, correlação e resposta a incidentes de segurança.

4. Proteção de Dados
Criptografia em repouso e em trânsito com padrões como AES-256.
Armazenamento seguro com segurança de blob, discos gerenciados criptografados e controle de acesso baseado em identidade.
Backup e recuperação com Azure Backup e Azure Site Recovery.

5. Conformidade e Governança
A Azure oferece mais de 100 certificações de conformidade (ISO, GDPR, LGPD, HIPAA, etc.).
Uso de Azure Policy e Blueprints para garantir conformidade automática com regras e padrões.
Microsoft Purview (governança de dados) e Azure Monitor para auditoria e rastreabilidade.

Boas Práticas
Habilitar MFA para todos os usuários
Aplicar RBAC de forma granular e usar o princípio do menor privilégio
Monitorar continuamente com ferramentas como Defender for Cloud e Sentinel
Manter logs e auditorias ativos
Aplicar acesso condicional e revisar periodicamente as permissões

# resumo-do-lab 5

1. Princípios de Otimização de Custos
Visibilidade dos Gastos: Ter clareza sobre onde, como e por que os recursos estão sendo usados.
Eliminação de Desperdícios: Identificar e desligar recursos não utilizados ou subutilizados.
Ajuste de Recursos: Alocar o tamanho certo de máquinas virtuais, bancos de dados e outros serviços.
Uso de Preços e Modelos Flexíveis: Adotar modelos de cobrança como instâncias reservadas ou preços spot para reduzir gastos.

Ferramentas do Azure para Otimização
Azure Cost Management + Billing
Monitora e analisa o consumo de recursos.
Gera relatórios, alertas e orçamentos.
Ajuda na previsão de custos futuros com base no uso atual.

Azure Pricing Calculator
Permite estimar custos antes de provisionar recursos.
Útil para simular diferentes configurações e prever gastos mensais.

TCO Calculator (Calculadora de Custo Total de Propriedade)
Compara os custos da infraestrutura local com os custos esperados no Azure.
Avalia a viabilidade econômica de migração para a nuvem.

Azure Advisor
Oferece recomendações práticas para:
Reduzir custos,
Melhorar desempenho,
Aumentar segurança e confiabilidade.
Sinaliza recursos subutilizados ou superprovisionados.

Boas Práticas de Otimização
Dimensionamento Correto
Reduzir ou redimensionar recursos de acordo com a necessidade real.
Usar autoescalabilidade para lidar com variações de carga.

Desligamento de Recursos em Horários de Baixa
Automatizar o desligamento de VMs ou bancos de dados fora do horário comercial.

Instâncias Reservadas
Contratos de 1 ou 3 anos com desconto, ideais para cargas de trabalho constantes.

Utilização de Tags (Marcas)
Ajudam a organizar e rastrear custos por projeto, departamento ou cliente.

Uso de Contêineres e Serviços Serverless
Soluções como Azure Functions e Azure Container Instances cobram apenas pelo uso efetivo, reduzindo custos ociosos.

Escolha Estratégica da Região
Custos variam entre regiões do Azure. Algumas regiões são mais baratas para determinados serviços.

4. Exemplos Práticos
Desligar VMs não utilizadas à noite economiza em ambientes de desenvolvimento e teste.
Reservar instâncias de SQL Database com uso constante pode gerar até 40% de economia.
Redimensionar discos e armazenamento evita pagar por capacidade não utilizada.

Monitoramento e Governança
Criação de políticas de governança para limitar uso excessivo.
Definir orçamentos e alertas de gastos por grupo de recursos.
Utilizar Azure Policy para controlar padrões de uso e aplicar regras de otimização automaticamente.

# resumo-do-lab 6

Tipos de Bloqueios
Existem dois tipos de bloqueios no Azure:
ReadOnly (Somente leitura)
Impede qualquer modificação no recurso.
Ainda é possível visualizar os dados, mas não é permitido fazer alterações nem realizar operações de gerenciamento.
Nenhuma alteração via portal, PowerShell, CLI ou ARM é permitida.
Delete (Exclusão)
Permite a modificação do recurso, mas impede que ele seja excluído.
Ideal para recursos que ainda estão em desenvolvimento ou uso, mas não devem ser removidos por engano.

Onde e Como Aplicar um Bloqueio
Os bloqueios podem ser aplicados em diferentes níveis:
Nível de Recurso: Protege um recurso individual.
Nível de Grupo de Recursos: Todos os recursos dentro do grupo herdariam o bloqueio.
Nível de Assinatura: Afeta todos os recursos e grupos de recursos da assinatura.
Você pode aplicar bloqueios pelo:
Portal do Azure
Azure PowerShell
Azure CLI
Templates ARM


Prioridade sobre permissões: Mesmo que um usuário tenha permissões para excluir ou editar um recurso, o bloqueio impede a ação.
Administração: Apenas usuários com permissões apropriadas (como proprietário ou administrador) podem adicionar ou remover bloqueios.
Não substitui RBAC: Bloqueios não são um substituto para o RBAC, mas sim um complemento de segurança.

# resumo-do-lab 7

1. Azure Resource Manager (ARM)
O ARM é a plataforma nativa de gerenciamento de recursos no Azure. Ele permite que os usuários implantem, atualizem e excluam recursos de forma organizada. Todos os recursos implantados via ARM fazem parte de um grupo de recursos, e a plataforma permite controle de acesso, auditoria e aplicação de políticas.
Suporte à infraestrutura como código (IaC) por meio de arquivos JSON ARM templates.
Permite o versionamento, reutilização e a automação de configurações.

2. ARM Templates
Arquivos JSON declarativos que descrevem os recursos a serem implantados no Azure. Eles são usados com o Azure Resource Manager para automatizar e padronizar implantações.
Ideal para automação repetível.
Suporta parâmetros, variáveis, condições e funções.
Pode ser usado via Azure CLI, PowerShell ou diretamente no portal.

3. Bicep
Bicep é uma linguagem de domínio específico (DSL) que simplifica a criação de templates ARM.
Mais legível que JSON.
Compila para templates ARM padrão.
Permite uso de módulos reutilizáveis.
Ferramenta oficial da Microsoft e integrada ao Visual Studio Code.

4. Azure CLI
A Azure Command-Line Interface (CLI) é uma ferramenta de linha de comando multiplataforma para criar e gerenciar recursos do Azure.
Permite execução rápida de comandos para criar recursos.
Suporta scripts automatizados.
Pode ser usada localmente ou no Azure Cloud Shell.

5. Azure PowerShell
Parecida com a Azure CLI, mas voltada para administradores que preferem o PowerShell como linguagem de script.
Integração com o Azure Resource Manager.
Suporte a scripts automatizados com lógica condicional complexa.

6. Terraform
Ferramenta de IaC de código aberto desenvolvida pela HashiCorp, amplamente usada no mercado.
Suporte a múltiplas nuvens (Azure, AWS, GCP).
Utiliza linguagem HCL (HashiCorp Configuration Language).
Permite versionamento e reuso de código com estados mantidos localmente ou remotamente.

7. Ansible
Ferramenta de automação de configuração e provisionamento, baseada em YAML.
Usa playbooks para descrever infraestrutura.
Muito usada para configuração pós-implantação de recursos.
Requer um controlador local para executar os scripts.

8. Azure DevOps
Plataforma que permite a criação de pipelines de CI/CD (Integração e Entrega Contínua).
Integra-se com ARM Templates, Bicep, Terraform, entre outras ferramentas.
Suporte nativo para controle de versão (Git) e testes automatizados.

9. GitHub Actions for Azure
Permite automatizar implantações usando workflows GitHub.
Ideal para projetos hospedados no GitHub.
Integra-se diretamente com Azure CLI, Bicep, Terraform, etc.

# resumo-do-lab 8

Principais Funcionalidades do Azure Monitor
Coleta de dados
Métricas: Valores numéricos sobre o desempenho de recursos ao longo do tempo (ex.: uso de CPU, memória, tempo de resposta).
Logs: Dados detalhados sobre eventos e atividades (ex.: registros de auditoria, erros, transações).
Análise de dados
Kusto Query Language (KQL): Linguagem usada para consultar dados nos logs.
Dashboards personalizados: Visualizações em tempo real para métricas e logs.
Notificações e respostas
Alertas: Disparados com base em regras personalizadas para métricas ou logs.
Automação: Pode iniciar ações automáticas via Logic Apps, Runbooks do Azure Automation, ou funções do Azure.

Benefícios do Azure Advisor
Proatividade: Identifica problemas antes que causem impacto.
Economia: Reduz custos com recomendações práticas.
Segurança reforçada: Ajuda a manter conformidade e proteção.
Facilidade: Não exige instalação; disponível direto no portal Azure.
Personalização: As recomendações são específicas para o seu ambiente.


