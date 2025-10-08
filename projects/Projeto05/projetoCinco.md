# Projeto: Tarefas Automatizadas com AWS Lambda e Amazon S3

Neste projeto, explorei a criação de **tarefas automatizadas** utilizando a combinação de **AWS Lambda** e **Amazon S3**. O objetivo foi aprender a automatizar processos na nuvem, aproveitando a escalabilidade e a flexibilidade da AWS.

---

## O que é Amazon S3

O **Amazon S3 (Simple Storage Service)** é um serviço de armazenamento de objetos na nuvem da AWS. Ele permite armazenar arquivos de qualquer tipo e tamanho, como imagens, documentos, backups ou dados de logs. Alguns pontos importantes:

- **Alta durabilidade e disponibilidade**: Seus dados são replicados automaticamente em múltiplas regiões.
- **Controle de acesso**: Possui políticas e permissões para garantir segurança.
- **Integração com outros serviços AWS**: Pode disparar eventos em serviços como Lambda quando um arquivo é criado ou modificado.

> **Exemplo real**: Imagine que você queira armazenar relatórios gerados diariamente por uma aplicação. Cada arquivo pode ser enviado para um bucket S3, onde ficará seguro e disponível para análise posterior.

---

## O que é AWS Lambda

O **AWS Lambda** é um serviço de **computação serverless**, que executa código em resposta a eventos sem precisar provisionar servidores. Principais características:

- **Execução baseada em eventos**: Pode ser disparado por uploads em S3, mensagens no SNS, requisições HTTP via API Gateway, entre outros.
- **Escalabilidade automática**: A AWS ajusta a quantidade de instâncias conforme a demanda.
- **Pagamento por uso**: Você paga apenas pelo tempo de execução do código.

> **Exemplo real**: Quando um arquivo CSV é enviado para o S3, a função Lambda pode automaticamente ler o arquivo, processar os dados e enviar um resumo por e-mail.


## Exemplo de Código Lambda (Node.js)

```javascript
const AWS = require('aws-sdk');
const s3 = new AWS.S3();

exports.handler = async (event) => {
    const bucketName = event.Records[0].s3.bucket.name;
    const objectKey = event.Records[0].s3.object.key;

    console.log(`Arquivo recebido: ${objectKey} no bucket ${bucketName}`);

    // Aqui você pode adicionar processamento, por exemplo, conversão de imagem ou leitura de CSV
    return {
        statusCode: 200,
        body: JSON.stringify('Processamento concluído com sucesso!')
    };
};