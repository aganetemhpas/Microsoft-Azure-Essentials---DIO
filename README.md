# Microsoft-Azure-Essentials-DIO
Repositório com anotações, laboratórios e práticas desenvolvidas durante o curso Microsoft Azure Essentials (DIO). Exploração de conceitos fundamentais de computação em nuvem, serviços do Azure, governança, segurança e arquitetura básica.


## 📘 Laboratório: Microsoft Azure - Localizando Serviços por Categoria

No laboratório **Microsoft Azure - Localizando Serviços por Categoria**, aprendi como personalizar o ambiente do portal Azure para torná-lo mais agradável e produtivo, ajustando:

- 🌎 Idioma  
- 🎨 Layout e disposição dos itens  
- 📌 Preferências de navegação  

O foco principal foi compreender a organização dos serviços do Azure por categorias, facilitando a localização e entendimento das soluções disponíveis na plataforma.

Também foi dada atenção especial aos serviços que estão em **prévia (Preview)**. Esses serviços ainda estão em fase de testes, podendo sofrer alterações, limitações ou até mesmo serem descontinuados. Por isso, **não é recomendado utilizá-los em ambientes de produção**, especialmente em cenários corporativos críticos.

Esse laboratório reforçou a importância de avaliar o nível de maturidade dos serviços antes de sua adoção em projetos reais.



## 📘 Laboratório: Microsoft Azure - Criando Máquinas Virtuais na Azure

Este laboratório tem como objetivo consolidar os conhecimentos em máquinas virtuais da Azure, cobrindo desde a criação pelo Portal até a conexão remota e boas práticas de gerenciamento de recursos.

---

### 🎯 Objetivos de Aprendizagem

Ao concluir este desafio, você será capaz de:

- Aplicar os conceitos aprendidos em um ambiente prático;
- Documentar processos técnicos de forma clara e estruturada;
- Utilizar o GitHub como ferramenta para compartilhamento de documentação técnica;
- Compreender os principais parâmetros de configuração de uma VM no Azure.

---

### 🧠 Conceitos Aprendidos

### O que é uma Máquina Virtual (VM)?

Uma VM é uma instância de computação em nuvem (IaaS) que oferece controle total sobre sistema operacional, memória, disco e rede — sem a necessidade de hardware físico.

### Componentes principais envolvidos:

- **Grupo de Recursos** — contêiner lógico para organizar todos os recursos relacionados;
- **Imagem do SO** — Windows Server, Ubuntu, etc.;
- **Tamanho da VM** — define CPU e memória (ex: `Standard_B1s`);
- **Rede Virtual (VNet)** — isolamento de rede e definição de sub-redes;
- **NSG (Network Security Group)** — regras de entrada/saída de tráfego;
- **Disco gerenciado** — Standard HDD, Standard SSD ou Premium SSD.

---

### 🔧 Passo a Passo

#### 1. Acessar o Portal Azure
Acesse [portal.azure.com](https://portal.azure.com) e faça login com sua conta Microsoft.

#### 2. Criar um Grupo de Recursos
- Navegue até **Grupos de recursos** → **Criar**
- Defina nome, assinatura e região (ex: `Brazil South`)

#### 3. Criar a Máquina Virtual
- Navegue até **Máquinas Virtuais** → **Criar**
- Selecione a imagem (ex: Windows Server 2022 ou Ubuntu 22.04)
- Escolha o tamanho da VM
- Defina usuário e senha de acesso

#### 4. Configurar Rede e Portas
- Defina a VNet e sub-rede
- No NSG, habilite as portas necessárias:
  - `3389` para RDP (Windows)
  - `22` para SSH (Linux)

#### 5. Revisar e Criar
- Acesse a aba **Examinar + criar**
- Valide as configurações e confirme o deployment

#### 6. Conectar-se à VM
- Utilize **RDP** (Windows) ou **SSH** (Linux) com o IP público gerado
- Valide o acesso e o funcionamento da máquina

#### 7. Limpar os Recursos
- Após os testes, exclua o Grupo de Recursos para evitar cobranças desnecessárias

---

### ⚠️ Dicas Importantes

- Sempre defina uma **região próxima** ao seu público para reduzir latência.
- Use o tamanho mínimo necessário durante os estudos para **evitar custos**.
- **Delete os recursos** ao finalizar o laboratório — VMs geram cobrança mesmo paradas.
- Nunca exponha a porta `3389` ou `22` sem restrição de IP em ambientes reais.

---

### 📚 Recursos Úteis

- [Início Rápido: Criar uma VM Windows no Portal Azure](https://learn.microsoft.com/pt-br/azure/virtual-machines/windows/quick-create-portal)
- [Início Rápido: Criar uma VM Linux no Portal Azure](https://learn.microsoft.com/pt-br/azure/virtual-machines/linux/quick-create-portal)
- [Documentação oficial Azure Virtual Machines](https://learn.microsoft.com/pt-br/azure/virtual-machines/)
- [Calculadora de preços Azure](https://azure.microsoft.com/pt-br/pricing/calculator/)


## 📘 Laboratório: Microsoft Azure - Configurando uma Instância de Banco de Dados

### Descrição do Desafio

Este laboratório tem como objetivo praticar o processo de configuração de uma instância de Banco de Dados na plataforma Microsoft Azure, documentando o aprendizado como material de apoio para estudos e futuras implementações.

---

### 🎯 Objetivos de Aprendizagem

Ao concluir este desafio, você será capaz de:

- Aplicar os conceitos aprendidos em um ambiente prático;
- Documentar processos técnicos de forma clara e estruturada;
- Utilizar o GitHub como ferramenta para compartilhamento de documentação técnica.

---

### 🧠 Conceitos Aprendidos

#### O que é o Azure SQL Managed Instance?

É um serviço de banco de dados relacional totalmente gerenciado na nuvem, compatível com o SQL Server, que oferece alta disponibilidade, backups automáticos e escalabilidade — sem necessidade de gerenciar a infraestrutura subjacente.

### Modelos de implantação disponíveis no Azure:

- **Azure SQL Database** — banco de dados como serviço (DBaaS), ideal para novas aplicações;
- **Azure SQL Managed Instance** — maior compatibilidade com SQL Server on-premises, ideal para migrações;
- **SQL Server em VM** — controle total, indicado quando se precisa de acesso ao SO.

#### Principais componentes envolvidos:

- **Grupo de Recursos** — contêiner lógico para organizar todos os recursos;
- **Servidor lógico** — ponto de gerenciamento de autenticação e firewall;
- **Instância Gerenciada** — o mecanismo de banco de dados em si;
- **VNet / Sub-rede dedicada** — obrigatória para o Managed Instance;
- **Camada de serviço** — General Purpose ou Business Critical;
- **Redundância de backup** — local, zonal ou geográfica.

---

### 🔧 Passo a Passo

#### 1. Acessar o Portal Azure
Acesse [portal.azure.com](https://portal.azure.com) e faça login com sua conta Microsoft.

#### 2. Criar um Grupo de Recursos
- Navegue até **Grupos de recursos** → **Criar**
- Defina nome, assinatura e região (ex: `Brazil South`)

#### 3. Criar a Instância Gerenciada de SQL
- Pesquise por **Instâncias Gerenciadas de SQL** na barra de busca
- Clique em **Criar**
- Preencha os campos:
  - **Nome da instância** — identificador único
  - **Região** — mesma do grupo de recursos
  - **Camada de computação** — General Purpose (estudos) ou Business Critical (produção)
  - **vCores e armazenamento** — defina conforme a necessidade
  - **Autenticação** — SQL ou Azure Active Directory

#### 4. Configurar a Rede Virtual
- O Managed Instance exige uma **VNet com sub-rede dedicada**
- Crie uma nova VNet ou selecione uma existente
- A sub-rede não pode ser compartilhada com outros recursos

#### 5. Configurar Backup e Redundância
- Selecione o tipo de redundância de armazenamento de backup:
  - **Localmente redundante (LRS)** — para estudos/dev
  - **Geograficamente redundante (GRS)** — para produção

#### 6. Revisar e Criar
- Acesse a aba **Examinar + criar**
- Valide todas as configurações
- Confirme o deployment — *a criação pode levar até 6 horas*

#### 7. Conectar-se à Instância
- Após o deployment, obtenha o **host de conexão** na visão geral da instância
- Utilize o **SQL Server Management Studio (SSMS)** ou **Azure Data Studio** para conectar
- Informe o host, usuário e senha definidos na criação

### 8. Limpar os Recursos
- Exclua o Grupo de Recursos ao finalizar para **evitar cobranças**


---

### ⚠️ Dicas Importantes

- O **Managed Instance é significativamente mais caro** que o SQL Database comum — use apenas pelo tempo necessário durante os estudos.
- A criação da instância pode levar bastante tempo; planeje com antece

