
# 🚀 FórumHub API

Bem-vindo ao **FórumHub**, uma API RESTful desenvolvida como o desafio final da trilha de Spring Boot da Alura. Este projeto simula o back-end de um fórum de dúvidas, permitindo o gerenciamento completo de tópicos com regras de negócio sólidas e controle de acesso rigoroso.

## 🎯 Objetivo do Projeto

O FórumHub foi criado para replicar a lógica por trás de fóruns de discussão (como o StackOverflow ou o próprio fórum da Alura). Ele permite que usuários autenticados criem, visualizem, atualizem e deletem seus tópicos de dúvidas relacionados a cursos específicos.

## 🛠️ Tecnologias Utilizadas

Este projeto foi construído utilizando o que há de mais moderno no ecossistema Java:

* **Java 25**
* **Spring Boot 4.0.3**
* **Spring Security** (Autenticação e Autorização Stateless)
* **Token JWT** (Auth0 java-jwt)
* **Spring Data JPA & Hibernate** (Persistência de Dados)
* **MySQL 8.4** (Banco de Dados Relacional)
* **Flyway** (Migrations para controle de versão do banco)
* **Spring Validation** (Validação de dados de entrada)
* **Springdoc OpenAPI 3.0.1** (Documentação interativa - Swagger)

## ✨ Funcionalidades

- **Autenticação:** Login via e-mail e senha gerando um Token JWT.
- **Segurança:** Rotas da API protegidas contra acesso anônimo; exigência de token Bearer no Header.
- **CRUD de Tópicos:**
  - `POST` Criação de novos tópicos (com validação contra tópicos duplicados).
  - `GET` Listagem de tópicos com paginação e ordenação nativa do Spring.
  - `GET` Detalhamento de um tópico específico por ID.
  - `PUT` Atualização de título, mensagem ou status do tópico.
  - `DELETE` Exclusão de tópicos.
- **Tratamento de Erros:** Respostas customizadas e padronizadas (Códigos 400, 403, 404) para validações de regras de negócio.

## 🚀 Como executar o projeto localmente

### Pré-requisitos
* Java 25 instalado.
* Maven instalado.
* MySQL rodando localmente na porta `3306`.

### Passo a Passo

1. **Clone o repositório:**
   ```bash
   git clone [https://github.com/SEU-USUARIO/api-forum-hub.git](https://github.com/SEU-USUARIO/api-forum-hub.git)
```

2. **Configure o Banco de Dados:**
   Acesse seu terminal MySQL e crie o banco de dados da aplicação:

```sql
CREATE DATABASE forumhub DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

3. **Inicie a Aplicação:**
   Execute a classe `ApiApplication.java` na sua IDE (IntelliJ, Eclipse, VS Code).
   *O Flyway se encarregará de criar todas as tabelas (usuarios, cursos, topicos) automaticamente.*

4. **Popule os dados iniciais:**
   Para conseguir fazer o primeiro login e criar um tópico, insira um usuário e um curso manualmente no banco:

```sql
USE forumhub;
INSERT INTO usuarios (login, senha) VALUES ('josecarlos@email.com', '$2a$10$Y50UaMFOxteibQEYLrwuHeehHYfcoafCopUazP12.rqB41bsolF5.');
INSERT INTO cursos (nome, categoria) VALUES ('Spring Boot 3', 'Programacao');
```

## 📚 Documentação da API (Swagger)

A API está totalmente documentada. Com a aplicação rodando, você pode testar todas as rotas diretamente pelo navegador através do Swagger UI.

1. Acesse: `http://localhost:8080/swagger-ui.html`
2. Utilize a rota `POST /login` informando as credenciais de teste:

```json
{
  "login": "josecarlos@email.com",
  "senha": "123456"
}
```

3. Copie o Token JWT retornado.
4. Clique no botão **Authorize** no topo da página do Swagger, cole o token e comece a gerenciar os tópicos!

---

*Projeto desenvolvido por José Carlos para a formação Back-end da Alura.*

```
```
