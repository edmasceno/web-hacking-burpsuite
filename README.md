# Web Hacking: SQL Injection com Burp Suite 🕷️

Este projeto demonstra uma vulnerabilidade crítica de aplicações web: **SQL Injection**. O objetivo foi burlar a autenticação de uma loja virtual intencionalmente vulnerável (OWASP Juice Shop) para obter acesso de Administrador sem possuir a senha.

## 🛠️ Ferramentas
* **Alvo:** OWASP Juice Shop (Aplicação Node.js/Express)
* **Atacante:** Burp Suite Community Edition
* **Conceito:** Proxy HTTP e Manipulação de Payload (JSON).

## 🕵️‍♂️ O Ataque: Injeção de Payload
O ataque foi realizado interceptando a requisição de login e modificando o payload (corpo da mensagem).

1.  **Vulnerabilidade:** A aplicação falha em sanitar (limpar) o input do campo de email antes de enviar para a query SQL.
2.  **Payload Injetado:** Utilizei o código SQL: `' or 1=1 --`
3.  **Resultado no Servidor:** O servidor executa a query, que se torna logicamente verdadeira para o primeiro usuário encontrado (que geralmente é o Admin).

### 📸 Prova de Sucesso
Abaixo, o print screen mostra a loja logada com sucesso com o e-mail do administrador, provando que o ataque de injeção foi eficaz:

![SQL Injection Proof](sql_injection_proof.png)

## 🧠 Aprendizado
Ataques de SQL Injection provam que a validação de dados deve ser feita pelo lado do **servidor** (backend), e não apenas pelo navegador (frontend). A manipulação de requisições via Burp Suite é a principal técnica de reconhecimento para falhas web.

---
*Projeto de estudo focado em OWASP Top 10 e AppSec.*
