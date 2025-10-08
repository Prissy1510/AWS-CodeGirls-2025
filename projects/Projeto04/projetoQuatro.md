# Implementando Infraestrutura Automatizada com AWS CloudFormation

##  O que é o AWS CloudFormation

O **AWS CloudFormation** é um serviço da Amazon Web Services que permite **criar, configurar e gerenciar recursos de infraestrutura na nuvem por meio de código**.  
Com ele, é possível definir toda a infraestrutura (como instâncias EC2, bancos de dados, VPCs e funções Lambda) em **templates YAML ou JSON**, garantindo **padronização, reprodutibilidade e automação** do ambiente.

---

##  Automação da Infraestrutura

A automação com o CloudFormation elimina a necessidade de configurar recursos manualmente no console da AWS.  
Isso é feito através de **templates declarativos**, onde você descreve o que deseja criar, e o CloudFormation se encarrega de provisionar tudo automaticamente.  

###  Benefícios da automação:
- **Consistência**: ambientes de desenvolvimento, teste e produção podem ser replicados com precisão.  
- **Velocidade**: criação de recursos em minutos, sem etapas manuais.  
- **Controle de versão**: templates podem ser versionados no Git.  
- **Escalabilidade**: fácil criação e atualização de infraestruturas complexas.  

---

##  Criação de uma Stack

No CloudFormation, uma **Stack** é o **conjunto de recursos que são criados e gerenciados como uma única unidade**.  
Quando um template é enviado ao CloudFormation, ele gera uma stack com todos os recursos definidos — como servidores, redes, e bancos de dados.  

### 🔍 Exemplo de fluxo:
1. Criar um arquivo `template.yaml` descrevendo os recursos (ex: uma instância EC2 e um Security Group).  
2. Fazer o upload do template no CloudFormation.  
3. O serviço cria automaticamente todos os recursos, formando uma **Stack**.  
4. Caso seja necessário atualizar ou excluir, o CloudFormation gerencia tudo de forma segura e automatizada.  

---

##  Diferença entre AWS CloudFormation e Terraform

| Característica | **AWS CloudFormation** | **Terraform** |
|----------------|------------------------|----------------|
| **Provedor** | Exclusivo da AWS | Multicloud (AWS, Azure, GCP etc.) |
| **Linguagem** | YAML ou JSON | HCL (HashiCorp Configuration Language) |
| **Gerenciamento de estado** | Controlado automaticamente pela AWS | Estado armazenado localmente ou em repositório remoto |
| **Integração com AWS** | Nativa e mais profunda | Boa, mas via APIs externas |
| **Custos** | Gratuito (paga-se apenas pelos recursos criados) | Gratuito (open-source) |
| **Curva de aprendizado** | Mais simples para quem usa só AWS | Mais flexível, mas exige mais configuração |


 
