# AWS CloudFormation - Infraestrutura como Código

Nesta etapa do meu aprendizado, mergulhei no uso do **AWS CloudFormation**, uma ferramenta poderosa que permite criar, configurar e gerenciar toda a infraestrutura da AWS por meio de código. Essa abordagem garante **padronização, automação e controle total** sobre os recursos na nuvem.

---

## O que é AWS CloudFormation

O AWS CloudFormation é um serviço que **automatiza o provisionamento de recursos AWS** usando templates em **YAML** ou **JSON**.  
Em vez de criar manualmente cada serviço pelo console, é possível definir tudo em um arquivo — desde VPCs, instâncias EC2, buckets S3 até regras de segurança.

Com isso, a infraestrutura se torna **reprodutível, rastreável e versionável**, seguindo o conceito de **Infraestrutura como Código (IaC)**.

---

## Criando uma Stack — passo a passo (o que aprendi)

Neste desafio, aprendi a criar uma **Stack** no AWS CloudFormation passo a passo, documentando e validando cada etapa sem executar a criação efetiva no ambiente.  
O processo foi organizado e me ajudou a entender o fluxo completo de provisionamento.

### Passos que segui (resumo)

#### 1. Planejamento
- Definir quais recursos são necessários (ex.: VPC, sub-redes, EC2, RDS, S3, Security Groups) e as dependências entre eles.

#### 2. Escrita do template (YAML/JSON)
- Estruturar **Parameters**, **Mappings**, **Resources**, **Outputs** e **Conditions** para deixar o template **reutilizável e parametrizável**.

#### 3. Validação do template
- Validar a sintaxe e lógica (usando o **CloudFormation Designer** ou validação local/console) para garantir que o template não tenha erros antes de qualquer deploy.

#### 4. Preparação para criação da Stack
- Revisar parâmetros, definir tags e selecionar uma **role de execução** (se necessário).  
- Aprendi como seria o fluxo no console ou via CLI para criar a stack:  
  `upload do template → preenchimento de parâmetros → revisar → criar`.

#### 5. Acompanhamento (monitoramento)
- Entender como acompanhar os **eventos de criação** no console do CloudFormation e verificar **logs em CloudWatch** para identificar problemas ou confirmar sucesso.

#### 6. Atualização controlada (Change Sets)
- Aprendi a gerar **Change Sets** para revisar mudanças antes de aplicá-las na stack, minimizando riscos em produção.

#### 7. Rollback e exclusão
- Conheci o comportamento de **rollback automático** em caso de falhas e como excluir uma stack de forma segura quando necessário.

---

## Para que serve uma Stack?

- Agrupar **recursos relacionados** (todos criados e gerenciados juntos).  
- Gerenciar o **ciclo de vida da infraestrutura** (criar, atualizar, deletar de forma controlada).  
- Reproduzir **ambientes idênticos** (dev/test/prod) facilmente a partir do mesmo template.  
- Versionar infraestrutura no **Git**, permitindo auditoria e revisão de mudanças.  
- Automatizar deploys e integrar com **pipelines de CI/CD**.  
- Aplicar **controle e governança** (parâmetros, roles e políticas centralizadas).  
- Minimizar **erros manuais** e garantir **consistência entre ambientes**.
