Policies:
documentos JSON que definem permissões (Allow/Deny), podem ser _managed_ (reutilizáveis) ou _inline_ (específicas). 

Tipos: 
identity-based vs resource-based; suportam conditions (ex.: `aws:SourceIp`).

Roles: 
entidade que pode ser assumida por usuários, serviços ou contas (ex.: role para EC2 acessar S3). Roles têm **trust policy** (quem pode assumir) e **permission policy** (o que pode fazer).  

Dica rápida:
use policies gerenciadas e boundaries de permissão para limitar alcance de permissões.

<br>

[Voltar para o Oráculo](../../Oracle/Oráculo.md)
<p align="left">
  <img src="https://media0.giphy.com/media/v1.Y2lkPTc5MGI3NjExNHl6NXVoZ2hjZnkxYTNndHdjczdzYm5laW1tc3phMTc4ZjNwZXpkciZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/MgkBTmxt18lGg/giphy.gif" width="157"/>
</p>
