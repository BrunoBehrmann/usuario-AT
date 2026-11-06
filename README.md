# 👤 Microsserviço de Usuários

> API responsável pelo gerenciamento, cadastro e validação dos dados de usuários do ecossistema.

---

## 🎯 Sobre o Projeto

O microsserviço **usuario** centraliza as regras de negócio associadas aos perfis de usuários do sistema. Ele permite o cadastro de novos usuários e fornece os dados necessários para vinculação com o agendamento de tarefas e envio de notificações por e-mail.

---

## 🏛️ Arquitetura do Ecossistema

O sistema completo é composto por 4 microsserviços independentes e containerizados com **Docker**:

1. **[bff-agendador-tarefas](https://github.com/BrunoBehrmann/bff-agendador-tarefas-AT)**: Gateway / BFF que recebe as chamadas externas e orquestra os fluxos.
2. **[agendador-tarefas](https://github.com/BrunoBehrmann/agendador-tarefas-AT)**: Microsserviço responsável pelas regras de agendamento, persistência e execução temporizada (Cron/Task).
3. **[usuario](https://github.com/BrunoBehrmann/usuario-AT)** *(Repositório Atual)*: Microsserviço de gestão, cadastro e validação dos dados de usuários.
4. **[notificacao](https://github.com/BrunoBehrmann/notificacao-AT)**: Microsserviço dedicado ao disparo automatizado de e-mails e alertas.

---

## 🛠️ Tecnologias e Dependências

* **Core & Framework:**
  * **Java 17+**
  * **Spring Boot**
  * **Spring Data JPA / Hibernate**
  * **Spring Web** (Endpoints RESTful)
* **Banco de Dados:**
  * **PostgreSQL** (Persistência dos dados de usuários)
* **DevOps & Build:**
  * **Docker**
  * **Maven**

---

## 📌 Endpoints Internos

| Método | Endpoint | Descrição |
| :--- | :--- | :--- |
| `POST` | `/usuario` | Cadastra um novo usuário no sistema |
| `GET` | `/usuario/{id}` | Busca informações detalhadas do usuário |
| `PUT` | `/usuario/{id}` | Atualiza dados cadastrais do usuário |
