# ☁️ Conceitos Básicos dos Serviços Utilizados

Este documento reúne os conceitos fundamentais dos serviços AWS utilizados no projeto de **Infraestrutura Automatizada com CloudFormation**, explicando suas funções e como se integram para formar uma arquitetura automatizada, escalável e segura.

---

## 🧩 AWS CloudFormation

O **AWS CloudFormation** é um serviço de **Infraestrutura como Código (IaC)** que permite criar, configurar e gerenciar recursos da AWS por meio de **templates em YAML ou JSON**.

Esses templates definem tudo o que a infraestrutura precisa: redes, servidores, bancos de dados, permissões e muito mais — tudo de forma automatizada e versionada.

**Principais conceitos:**
- **Template:** arquivo que descreve os recursos e suas configurações.
- **Stack:** conjunto de recursos criados e gerenciados em conjunto.
- **Parâmetros:** permitem customizar valores dentro do template.
- **Outputs:** mostram informações úteis após a criação da stack (como IDs ou URLs).

**Benefícios:**
- Padronização de ambientes.
- Criação rápida e reproduzível de infraestrutura.
- Integração com CI/CD e controle de versão via GitHub.

---

## 💻 Amazon EC2 (Elastic Compute Cloud)

O **Amazon EC2** é o serviço que fornece **servidores virtuais na nuvem**.  
Com ele, é possível hospedar aplicações, executar processos ou configurar servidores web.

**No CloudFormation:**  
Você pode definir instâncias EC2 diretamente no template, configurando o tipo de instância, sistema operacional (AMI), regras de segurança e armazenamento.

**Exemplo prático:**
```yaml
Resources:
  MyEC2Instance:
    Type: AWS::EC2::Instance
    Properties:
      InstanceType: t2.micro
      ImageId: ami-0abcd1234abcd5678
```

---

## 🗃️ Amazon S3 (Simple Storage Service)

O Amazon S3 é o serviço de armazenamento de objetos da AWS.
Ele é usado para guardar arquivos, imagens, logs, backups e até templates do CloudFormation.

Características:

- Armazenamento escalável e seguro.
- Organização em buckets (pastas virtuais).
- Controle de acesso via políticas e permissões IAM.

Uso no projeto:

- Armazenar templates .yaml ou .json.
- Guardar dados gerados por funções Lambda (como uploads).
- Servir como ponto de integração em fluxos automatizados.

---

## ⚙️ AWS Lambda

O AWS Lambda é um serviço de computação serverless que executa código sob demanda, sem precisar gerenciar servidores.

Funcionamento básico:

- Você cria uma função em linguagens como Python, Node.js ou Go.
- A função é disparada por eventos (ex: upload no S3, requisição no API Gateway).
- O código roda automaticamente, e você paga apenas pelo tempo de execução.

No CloudFormation:
É possível definir e configurar funções Lambda diretamente no template, integrando-as a eventos do S3 ou DynamoDB.

---

## 🔗 Amazon API Gateway

O API Gateway é o serviço que permite criar e gerenciar APIs RESTful ou WebSocket.
Ele atua como um intermediário entre o cliente e os serviços backend (como Lambda ou EC2).

No projeto:

- O API Gateway foi usado para receber requisições HTTP e acionar a função Lambda (ProcessarNotasFiscais).
- Foi configurado via AWS CLI e LocalStack para testes locais.

---

## 🗄 Amazon DynamoDB

O Amazon DynamoDB é um banco de dados NoSQL totalmente gerenciado da AWS.
Ele é altamente escalável, rápido e não requer administração de servidores.

Principais características:

- Armazena dados em formato de tabelas com chaves primárias e atributos.
- Oferece alta disponibilidade e performance.
- Integra-se facilmente com Lambda e API Gateway.

No contexto do projeto:
O DynamoDB pode ser usado para registrar logs, armazenar dados processados por funções Lambda ou guardar metadados de arquivos no S3.

---

## 🛠️ AWS IAM (Identity and Access Management)

O AWS IAM gerencia usuários, permissões e políticas de acesso na AWS.
Com ele, é possível controlar quem pode criar, alterar ou excluir recursos dentro de uma conta.

Uso no CloudFormation:

- Definir roles (funções) para permitir que o CloudFormation crie recursos em nome do usuário.
- Associar permissões específicas às funções Lambda e aos serviços integrados.

---

## ⚙️ LocalStack (Ambiente de Teste Local)

O LocalStack é uma ferramenta que permite simular serviços da AWS localmente, ideal para testes e desenvolvimento offline.

Serviços suportados: S3, Lambda, API Gateway, DynamoDB, CloudFormation, entre outros.

Vantagens:

- Permite testar código sem custos na AWS.
- Integra-se facilmente à AWS CLI.
- Ideal para laboratórios e ambientes de aprendizado.

---

## 📍 Resumo Final

| Serviço            | Função Principal                       | Tipo       |
| ------------------ | -------------------------------------- | ---------- |
| **CloudFormation** | Automatiza a criação da infraestrutura | IaC        |
| **EC2**            | Servidor virtual escalável             | Compute    |
| **S3**             | Armazenamento de objetos               | Storage    |
| **Lambda**         | Execução de código sem servidor        | Serverless |
| **API Gateway**    | Criação e gerenciamento de APIs        | Networking |
| **DynamoDB**       | Banco de dados NoSQL gerenciado        | Database   |
| **IAM**            | Controle de identidade e acesso        | Security   |
| **LocalStack**     | Simula AWS localmente                  | Dev/Test   |

---

✍️ *Anotações e prática desenvolvidas por **Francine Souza**, como parte do desafio da DIO.*
