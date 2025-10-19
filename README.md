# 🚀 Desafio de Projeto — Executando Tarefas Automatizadas com Lambda Function e S3

Este projeto faz parte do laboratório da **DIO** e tem como objetivo **consolidar o uso de funções Lambda integradas ao Amazon S3**, aplicando os conceitos de **Infraestrutura como Código (IaC)** com **AWS CloudFormation**.  
Durante o desafio, foi utilizado o **LocalStack** para simular os serviços AWS localmente.

---

## 🎯 Objetivo do Laboratório

O laboratório teve como propósito:
- Criar e gerenciar recursos AWS com **CloudFormation** (em YAML ou JSON);
- Automatizar tarefas com **AWS Lambda** acionadas por **eventos no S3**;
- Integrar funções Lambda a uma **API Gateway** para envio e leitura de dados;
- Aplicar boas práticas de versionamento, segurança e modularização de stacks.

---

## 📂 Estrutura de Pastas

| Pasta / Arquivo | Descrição |
|------------------|------------|
| [`notes/conceitos-basicos.md`](notes/conceitos-basicos.md) | Explicação dos serviços usados. |
| [`notes/boaspraticas.md`](notes/boaspraticas.md) | Padrões de IaC e segurança. |
| [`notes/insights.md`](notes/insights.md) | Aprendizados e reflexões. |
| [`notes/arquitetura.md`](notes/arquitetura.md) | Diagrama e explicação da arquitetura criada. |

---

## 💻 Tecnologias e Serviços Utilizados

- **AWS Lambda** – execução de funções automatizadas sem servidor;
- **Amazon EC2** → instâncias de servidor virtual para hospedar aplicações. 
- **Amazon S3** – armazenamento e gatilho de eventos;
- **Amazon DynamoDB** → banco NoSQL totalmente gerenciado para armazenamento de dados de baixa latência e alta escala;
- **AWS API Gateway** – criação de endpoints REST para invocar a Lambda;
- **AWS IAM** – controle de permissões entre os serviços;
- **YAML / JSON** → linguagens para estruturar os templates da infraestrutura.  
- **AWS CloudFormation** – provisionamento automatizado da infraestrutura;
- **LocalStack** – ambiente local de emulação da AWS.

---

## 🧠 Principais Aprendizados

- Compreensão do gatilho de eventos entre S3 e Lambda;
- Automação completa com CloudFormation;
- Testes e deploy com LocalStack;
- Integração de API Gateway → Lambda → S3;
- Reforço do conceito de Infraestrutura como Código (IaC).

---

🧩 **Diagrama da Arquitetura**

<img width="741" height="691" alt="Desafio-DIO drawio" src="https://github.com/user-attachments/assets/4fd330ec-19fa-497a-89d0-bfd13db5db03" />

---

## 📚 Referências

- [📘 AWS CloudFormation — Documentação oficial](https://docs.aws.amazon.com/cloudformation/index.html)  
- [⚙️ Guia de Boas Práticas AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/best-practices.html)  
- [💾 Amazon S3 — Automação com CloudFormation](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/olap-using-cfn-template.html)  
- [📚 AWS CloudFormation — Secção “Working with Templates”](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-guide.html)
- [🧠 AWS Free Tier — Serviços gratuitos para prática](https://aws.amazon.com/free/)  

---

🔗 Desafio de Projeto da [Digital Innovation One (DIO)](https://www.dio.me/) \
📅 Concluído em: Outubro/2025 
