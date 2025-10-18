# 🧩 Boas Práticas — AWS CloudFormation

Este documento reúne boas práticas aplicadas durante a implementação da infraestrutura automatizada utilizando **AWS CloudFormation**, garantindo maior segurança, padronização e eficiência no provisionamento de recursos.

---

## 🧱 1. Estrutura e Organização dos Templates

- **Separar templates por responsabilidade:**  
  Criar arquivos distintos para cada camada da infraestrutura (rede, banco de dados, instâncias, etc.).
  
- **Utilizar parâmetros de forma inteligente:**  
  Permite reutilizar o mesmo template em diferentes ambientes (dev, stage, prod) apenas mudando os valores de entrada.
  
- **Definir nomes padronizados para recursos:**  
  Usar convenções de nomes consistentes, facilitando a identificação e manutenção dos recursos criados.

---

## 🧰 2. Boas Práticas de Implementação

- **Validação antes do deploy:**  
  Sempre utilizar o comando `aws cloudformation validate-template` para identificar erros de sintaxe antes da execução.

- **Testes em ambiente de desenvolvimento:**  
  Evitar aplicar diretamente em produção; usar stacks de teste para validar configurações e dependências.

- **Versionamento com Git:**  
  Manter o histórico dos templates e das atualizações em um repositório, documentando as mudanças em commits claros.

---

## 🔐 3. Segurança e Controle de Acesso

- **Usar políticas de IAM específicas:**  
  Evitar permissões amplas (como `*`). Conceder apenas o necessário para o CloudFormation operar.

- **Gerenciar chaves e segredos via AWS Systems Manager Parameter Store ou Secrets Manager:**  
  Nunca armazenar credenciais diretamente nos templates.

- **Controle de acesso ao S3:**  
  Garantir que buckets tenham criptografia habilitada e políticas de acesso restritas.

---

## ⚙️ 4. Eficiência e Escalabilidade

- **Uso de recursos gerenciados:**  
  Preferir serviços gerenciados como **Amazon RDS** e **DynamoDB**, reduzindo o esforço de manutenção.

- **Referências cruzadas (Outputs/Exports):**  
  Utilizar a funcionalidade de **Exports** para compartilhar informações entre stacks, evitando duplicação de recursos.

- **Definição de dependências claras:**  
  Utilizar o campo `DependsOn` para garantir a criação de recursos na ordem correta.

---

## 📚 5. Observabilidade e Auditoria

- **Habilitar logs e métricas no CloudWatch:**  
  Monitorar o desempenho e o status dos recursos criados automaticamente.

- **Usar tags em todos os recursos:**  
  Incluir tags para facilitar rastreamento, cobrança e auditoria de uso.

---

## 🧩 6. Aprendizados do Laboratório

Durante a prática, foi possível perceber que:
- A **automação com CloudFormation** reduz drasticamente o tempo de provisionamento.  
- O uso do **DynamoDB** como solução de armazenamento escalável simplifica a arquitetura sem necessidade de administração de servidores.  
- A **combinação de EC2, S3 e DynamoDB** cria uma base sólida para aplicações web seguras e escaláveis.
- O **LocalStack** é uma excelente ferramenta para testar stacks sem custos, tornando o aprendizado mais acessível e controlado.  

---

✍️ *Anotações e prática desenvolvidas por **Francine Souza**, como parte do desafio da DIO.*
