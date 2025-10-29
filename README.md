## CP02 
---
## Henrique marques sladkevicius RM560698
## Lucas Aurelio de Brito Chicote RM559366
## Lucas Gomes de Araujo Lopes RM559607

---

##  Funcionalidades

-  CRUD completo para usuários (`name`, `email`, `password`, `role`)  
-  Autenticação JWT com validação real de senha (BCrypt)  
-  Implementação de `UserDetailsService` e `AuthenticationProvider`  
-  Validação com Jakarta Validation  
-  Documentação com OpenAPI / Swagger  
-  PostgreSQL configurado via **docker-compose**  
-  pgAdmin incluído para facilitar testes  
-  Dockerfile para containerizar a aplicação  

---

## Como rodar com Docker

1. Instale **Docker** e **Docker Compose**.  
2. Ajuste credenciais em `src/main/resources/application.properties` (se necessário).  
3. Suba o banco e o pgAdmin:  
   ```bash
   docker compose up -d
   ```
4. Compile e execute a aplicação (local ou via Docker):  
   ```bash
   mvn clean package
   java -jar target/user-management-api-0.0.1-SNAPSHOT.jar
   ```
5. Endpoints principais:
   - Swagger UI → [http://localhost:8080/swagger-ui.html](http://localhost:8080/swagger-ui.html)  
   - Registro → `POST /api/auth/register`  
   - Login → `POST /api/auth/login`  
   - Users CRUD → `/api/users` (🔒 protegido — use `Authorization: Bearer <token>`)  
   - pgAdmin → [http://localhost:5050](http://localhost:5050) (login: `admin@local` / senha: `admin`)  
.