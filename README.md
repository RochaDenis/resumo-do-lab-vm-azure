# README - Criação de Máquina Virtual na Azure

## Introdução
Este documento descreve o processo de criação de uma Máquina Virtual (VM) na plataforma Microsoft Azure. Ele aborda os principais passos para a configuração e provisionamento, além de discutir os níveis de SLA (Acordo de Nível de Serviço) e os fatores que definem essas métricas.

---

## 1. **Pré-requisitos**
Antes de criar uma VM, verifique se você possui:
- Uma conta ativa no Microsoft Azure.
- Um grupo de recursos disponível ou a criação de um durante o processo.
- Permissões de usuário para criar e gerenciar VMs.

---

## 2. **Passos para a Criação de uma Máquina Virtual**

### 2.1. **Acessar o Portal do Azure**
- Acesse o [Portal do Azure](https://portal.azure.com) e faça login com sua conta.

### 2.2. **Criar um Grupo de Recursos (se necessário)**
- No painel esquerdo, clique em **"Grupos de Recursos"** e depois em **"Criar"**.
- Insira um nome e selecione a região para este grupo.
- Clique em **"Revisar e Criar"**.

### 2.3. **Iniciar o Processo de Criação de Máquina Virtual**
1. No painel esquerdo, clique em **"Máquinas Virtuais"** e depois em **"Criar"**.
2. Escolha a opção **"Azure Virtual Machine"**.

### 2.4. **Configurar as Propriedades da Máquina Virtual**
Na aba **"Informações básicas"**:
- **Assinatura**: Selecione a assinatura do Azure a ser utilizada.
- **Grupo de Recursos**: Escolha um grupo de recursos existente ou crie um novo.
- **Nome da VM**: Defina um nome único para a VM.
- **Região**: Selecione a região onde a VM será hospedada. (Ex: "East US")
- **Opções de Disponibilidade**: Configure opções de alta disponibilidade, como Conjuntos de Disponibilidade (Availability Sets) ou Zonas de Disponibilidade (Availability Zones).
  
Na aba **"Tamanho"**:
- Escolha o tamanho da VM, baseado no número de CPUs virtuais (vCPUs) e memória RAM.
  
Na aba **"Administração"**:
- Defina as credenciais de administrador (nome de usuário e senha ou chave SSH).

### 2.5. **Configurações de Rede**
Na aba **"Rede"**:
- Escolha ou crie uma rede virtual (VNet).
- Configure as sub-redes e o endereço IP público, se necessário.
- Defina regras de segurança, como portas a serem abertas (Ex: Porta 22 para SSH ou Porta 3389 para RDP).

### 2.6. **Revisar e Criar**
- Revise todas as configurações na aba **"Revisão e Criação"**.
- Clique em **"Criar"** para provisionar a VM. O processo levará alguns minutos para ser concluído.

---

## 3. **Níveis de SLA (Service Level Agreement)**

### 3.1. **O que é SLA?**
O Acordo de Nível de Serviço (SLA) define o compromisso da Microsoft Azure em garantir a disponibilidade e o desempenho das VMs. O SLA é expresso como uma porcentagem de disponibilidade mensal.

### 3.2. **Níveis de SLA para Máquinas Virtuais**
A Azure oferece diferentes níveis de SLA, dependendo da configuração de alta disponibilidade escolhida:

- **Máquinas Virtuais Isoladas**: 
  - **99,9% de SLA** para uma única VM usando **Discos Gerenciados** em uma **Zona de Disponibilidade**.
  
- **Conjuntos de Disponibilidade (Availability Sets)**: 
  - **99,95% de SLA** quando duas ou mais VMs são implantadas em um **Conjunto de Disponibilidade**, o que reduz o impacto de falhas de hardware ou software.

- **Zonas de Disponibilidade (Availability Zones)**:
  - **99,99% de SLA** quando as VMs estão distribuídas em diferentes Zonas de Disponibilidade dentro da mesma região.

### 3.3. **Fatores que Definem as Métricas de SLA**
Os principais fatores que influenciam o SLA de uma VM incluem:
- **Redundância**: O uso de conjuntos de disponibilidade ou zonas de disponibilidade pode aumentar o SLA.
- **Discos Gerenciados**: VMs que utilizam discos gerenciados possuem SLAs mais altos em comparação com aquelas que usam discos não gerenciados.
- **Resiliência da Região**: A escolha de regiões com suporte a múltiplas zonas de disponibilidade pode aumentar a resiliência e, consequentemente, o SLA.
- **Mecanismos de Backup**: Implementar estratégias de backup e failover pode minimizar o tempo de inatividade durante manutenções ou falhas.

---

## 4. **Monitoramento e Gerenciamento**
Depois de provisionada a VM, utilize ferramentas como **Azure Monitor** para monitorar a saúde e o desempenho da máquina. As métricas incluem CPU, memória, uso de disco e latência de rede, permitindo a detecção de problemas de disponibilidade.

---

## 5. **Conclusão**
A criação de uma máquina virtual no Azure é um processo simples, mas exige atenção às opções de alta disponibilidade para garantir um SLA adequado. Implementar boas práticas de resiliência, como o uso de conjuntos ou zonas de disponibilidade, é essencial para garantir altos níveis de disponibilidade e minimizar o impacto de falhas.

