-> Identity and Access Management

O que é:
serviço que controla identidade (quem) e autorização (o que pode fazer) na AWS.  

Componentes: 
**users**, **groups**, **roles**, **policies**, **MFA**, federation (login via IdP).  

Boas práticas: 
princípio do _least privilege_ (permissões mínimas), evitar uso do root, preferir roles para serviços e ativar MFA.  

Dica rápida: 
crie roles para aplicações (EC2/Lambda) em vez de distribuir credenciais.