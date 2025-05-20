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
