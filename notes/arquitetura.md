# 🗺️ Arquitetura e Diagrama

## ⚙️ Fluxo da Arquitetura

1. O usuário envia um arquivo JSON ou requisição que é armazenado no **bucket S3**;
2. O **bucket S3** ativa a **função Lambda** através de **Trigger**;
3. A Lambda processa o conteúdo (por exemplo, dados de notas fiscais) e grava no **Dynamo DB**;
4. O **cliente** consulta a nota fiscal via **API Gateway**;
5. O API Gateway executa o Lambda que busca informações no Dynamo DB.

🧩 **Diagrama da Arquitetura**

<img width="741" height="691" alt="Desafio-DIO drawio" src="https://github.com/user-attachments/assets/770221f4-6c6f-4a70-b44c-9639e6d4c251" />

---

✍️ *Anotações e prática desenvolvidas por **Francine Souza**, como parte do desafio da DIO.*
