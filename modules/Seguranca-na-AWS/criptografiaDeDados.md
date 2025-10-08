## Criptografia de Dados na AWS

A **criptografia** é uma técnica essencial para proteger dados sensíveis, garantindo que somente usuários ou sistemas autorizados possam acessá-los. Na **AWS (Amazon Web Services)**, a criptografia é amplamente utilizada para proteger dados **em trânsito** (quando são enviados pela rede) e **em repouso** (quando estão armazenados).

### 1. **Criptografia em Trânsito**

- Protege os dados enquanto eles se movem entre serviços, aplicações e clientes.
    
- Normalmente, é feita usando **TLS (Transport Layer Security)** ou **HTTPS**, garantindo que os dados não sejam interceptados ou alterados durante a transmissão.
    

### 2. **Criptografia em Repouso**

- Protege os dados armazenados em serviços da AWS, como **S3, RDS, DynamoDB, EBS**, entre outros.
    
- Pode ser automática ou configurada pelo usuário, usando chaves gerenciadas pela AWS ou pelo próprio cliente.
    

### 3. **AWS Key Management Service (KMS)**

- Serviço central da AWS para gerenciar chaves de criptografia.
    
- Permite criar, controlar e auditar chaves de criptografia de forma segura.
    
- Suporta criptografia **simétrica** (uma única chave para criptografar e descriptografar) e **assimétrica** (chave pública e privada).
    

### 4. **Tipos de Criptografia na AWS**

- **Criptografia do lado do servidor (SSE – Server-Side Encryption)**: Dados são criptografados automaticamente antes de serem armazenados. Exemplos:
    
    - **SSE-S3**: AWS gerencia a chave.
        
    - **SSE-KMS**: AWS KMS gerencia a chave, permitindo auditoria e controle de acesso.
        
    - **SSE-C**: O cliente fornece e gerencia a chave.
        
- **Criptografia do lado do cliente (CSE – Client-Side Encryption)**: Dados são criptografados antes de serem enviados para a AWS, garantindo que nem mesmo a AWS tenha acesso direto ao conteúdo.
    

### 5. **Auditoria e Segurança**

- AWS integra criptografia com serviços como **CloudTrail** e **CloudWatch** para monitoramento e auditoria.
    
- Permite definir **políticas de acesso** detalhadas e rastrear quem acessou ou usou chaves de criptografia.
    

### 6. **Vantagens**

- Protege dados sensíveis contra acessos não autorizados.
    
- Facilita conformidade com normas de segurança e regulamentações, como **LGPD** e **GDPR**.
    
- Combina facilidade de gerenciamento com alta segurança, usando serviços integrados da AWS.

<br>

[Voltar para o Oráculo](../../Oracle/Oráculo.md)
<p align="left">
  <img src="https://media0.giphy.com/media/v1.Y2lkPTc5MGI3NjExNHl6NXVoZ2hjZnkxYTNndHdjczdzYm5laW1tc3phMTc4ZjNwZXpkciZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/MgkBTmxt18lGg/giphy.gif" width="157"/>
</p>