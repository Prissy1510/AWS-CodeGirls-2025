Policies:
documentos JSON que definem permissões (Allow/Deny), podem ser _managed_ (reutilizáveis) ou _inline_ (específicas). 

Tipos: 
identity-based vs resource-based; suportam conditions (ex.: `aws:SourceIp`).

Roles: 
entidade que pode ser assumida por usuários, serviços ou contas (ex.: role para EC2 acessar S3). Roles têm **trust policy** (quem pode assumir) e **permission policy** (o que pode fazer).  

Dica rápida:
use policies gerenciadas e boundaries de permissão para limitar alcance de permissões.