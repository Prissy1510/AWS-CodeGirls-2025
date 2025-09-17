# Resumindo Modulo de Banco de Dados:

- **RDS** → Bancos relacionais (Aurora, Oracle, MySQL, PostgreSQL, MariaDB, SQL Server).  

- **DynamoDB** → Banco NoSQL, super rápido e escalável.  

- **Backup** → Cópia de segurança dos dados para evitar perdas.  

- **RPO e RTO** → Ajudam a definir a frequência de backup e o tempo máximo de recuperação.  

- **S3 e AWS Backup** → Armazenam e automatizam o processo de backup.  

- **CloudWatch** → Monitora recursos e envia alertas sobre falhas.

# 📘 Glossário AWS

1. **Nuvem Pública** - Servidores e serviços compartilhados por um provedor externo (ex: AWS, Google Drive).  
2. **Nuvem Privada** - Servidores exclusivos de uma empresa, internos ou dedicados.  
3. **Nuvem Híbrida** - Combinação de nuvem pública e privada para flexibilidade e segurança.  
4. **Serverless** - Modelo em que você roda código sem se preocupar com servidores; paga apenas pelo que usar.  
5. **Lambda** - Serviço serverless da AWS que executa funções automaticamente quando acionadas.  
6. **Regions** - Áreas geográficas com múltiplas zonas de disponibilidade.  
7. **Availability Zones (AZ)** - Data centers independentes dentro de uma região, conectados logicamente.  
8. **IaaS** - Infrastructure as a Service: Aluga infraestrutura (máquinas virtuais, rede, armazenamento).  
9. **PaaS** - Platform as a Service: Plataforma pronta para desenvolver e rodar aplicações sem gerenciar servidores.  
10. **SaaS** - Software as a Service: Aplicativos prontos acessados pela internet, sem manutenção pelo usuário.  
11. **EC2** - Elastic Compute Cloud: Máquina virtual para rodar aplicações, paga pelo tempo de uso.  
12. **Tipos de Instâncias EC2** - Diferentes configurações de CPU, memória e armazenamento, agrupadas por famílias.  
13. **VPC (Virtual Private Cloud)** - Rede virtual isolada na AWS onde você pode criar sub-redes, definir rotas e gerenciar recursos de forma segura.  
14. **Subnet (Sub-rede)** - Segmento da VPC que organiza recursos dentro de uma área específica da rede, podendo ser pública ou privada.  
15. **Route 53** - Serviço de DNS da AWS que traduz nomes de domínio em endereços IP, roteando o tráfego de forma confiável.  
16. **Elastic Load Balancer (ELB)** - Distribui automaticamente o tráfego entre múltiplas instâncias EC2, melhorando desempenho e disponibilidade.  
17. **CloudFront** - Content Delivery Network (CDN) da AWS que entrega conteúdo globalmente com baixa latência e alta velocidade.  
18. **RDS** - Bancos relacionais (Aurora, Oracle, MySQL, PostgreSQL, MariaDB, SQL Server).  
19. **DynamoDB** - Banco NoSQL, super rápido e escalável.  
20. **Backup** - Cópia de segurança dos dados para evitar perdas.  
21. **RPO e RTO** - Ajudam a definir a frequência de backup e o tempo máximo de recuperação.  
22. **S3 e AWS Backup** - Armazenam e automatizam o processo de backup.  
23. **CloudWatch** - Monitora recursos e envia alertas sobre falhas.

---

# 🌐 Diagrama de Arquitetura AWS

```mermaid
flowchart TD
    CF[CloudFront CDN] --> ELB[Elastic Load Balancer]
    ELB --> EC2[EC2 Instances]
    EC2 --> VPC[VPC]
    VPC --> Subnet1[Subnet Pública]
    VPC --> Subnet2[Subnet Privada]
    Subnet2 --> RDS[RDS (Aurora, MySQL, etc.)]
    Subnet2 --> DynamoDB[DynamoDB NoSQL]
    S3[S3 + AWS Backup] --> RDS
    S3 --> DynamoDB
    CloudWatch[CloudWatch] --> EC2
    CloudWatch --> RDS
    CloudWatch --> DynamoDB
