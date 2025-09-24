#  AWS Step Functions - Workflow

Nesta etapa do meu aprendizado, foi muito interessante conhecer e aplicar na prática um **fluxo de orquestração de microserviços** usando a AWS Step Functions.  


---

## Hands-on: 

Para este desafio, utilizei o **AWS Step Functions Workflow Studio** para construir visualmente o fluxo abaixo.  
Cada etapa foi criada arrastando e configurando componentes como **Tasks, Choice e Integrations**, conectando-os para simular um sistema de compra e venda de ações.

###  Experiência
- Entendi melhor o **papel de cada estado** (Task, Choice, Pass, Succeed, Fail).
- Aprendi a **definir transições** de um estado para outro.
- Testei o fluxo para garantir que as decisões (buy/sell) estivessem funcionando corretamente.


<img src=".img/WorkFlow.jpeg" alt="Workflow do Desafio" width="350"/>

---

##  Explicação do Workflow

1. **Start** → O fluxo inicia automaticamente.
2. **Check Stock Price (Lambda)** → Função Lambda que consulta o preço da ação.
3. **Generate Buy/Sell Recommendation (Lambda)** → Gera recomendação de compra ou venda.
4. **Request Human Approval (SQS)** → Envia a recomendação para aprovação humana.
5. **Buy or Sell? (Choice State)** → Verifica/escolhe a recomendação:
   - Se `$.recommended_type == "buy"` → chama **Buy Stock**.
   - Se `$.recommended_type == "sell"` → chama **Sell Stock**.
6. **Buy Stock / Sell Stock (Lambda)** → Executa a compra ou venda da ação.
7. **Report Result (SNS)** → Notifica o resultado final.
8. **End** → Finaliza.

---

##  Conceitos Aprendidos e Explicados

Durante esta etapa, explorei conceitos fundamentais para arquiteturas modernas:

###  Arquitetura de Microserviços
- **Desacoplamento de componentes** → cada Lambda faz uma tarefa isolada.
- **Escalabilidade** → serviços podem crescer independentemente.
- **Resiliência** → falhas não derrubam o sistema inteiro.

###  AWS Step Functions
- Serviço de **orquestração de workflows**.
- Permite coordenar múltiplos serviços AWS em um fluxo visual.
- Suporte a **estados** como:
  - **Task** → executa uma função ou integração (ex.: Lambda).
  - **Choice** → implementa decisões condicionais.
  - **Pass** → passa dados adiante sem executar código.
  - **Wait** → adiciona atrasos no fluxo.
  - **Succeed / Fail** → finalizam o workflow com sucesso ou erro.

### Amazon SNS e SQS
- **Amazon SNS (Simple Notification Service):**
  - Publica mensagens para múltiplos assinantes.
  - Ideal para enviar notificações de eventos.
- **Amazon SQS (Simple Queue Service):**
  - Fila de mensagens para desacoplar sistemas.
  - Garantia de entrega e processamento assíncrono.

### Amazon ECS e EKS
- **ECS (Elastic Container Service):**
  - Orquestração de containers nativa da AWS.
  - Pode usar Fargate (serverless) ou EC2 para rodar containers.
- **EKS (Elastic Kubernetes Service):**
  - Kubernetes gerenciado pela AWS.
  - Ideal para quem já usa Kubernetes e quer escalar na nuvem.




