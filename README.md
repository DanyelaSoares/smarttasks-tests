# 🧪 SmartTasks - Testes de API

Projeto de testes manuais e de API para o sistema **SmartTasks**, com foco na validação de funcionalidades, regras de negócio e autenticação, utilizando Postman.

---

## 🎯 Objetivo

Garantir a qualidade das funcionalidades do sistema SmartTasks por meio de testes manuais e testes de API, validando comportamentos esperados, tratamento de erros e regras de negócio.

---

## 🛠️ Ferramentas utilizadas

- Postman
- Testes manuais
- JSON (requisições e respostas)
- GitHub (documentação)

---

## 🔍 Escopo dos Testes

- Cadastro de usuário (`POST /auth/register`)
- Login (`POST /auth/login`)
- Teste de disponibilidade da API (`GET /test`)
- Validação de autenticação com JWT
- Testes positivos (fluxos válidos)
- Testes negativos (erros e exceções)

---
## 📁 Estrutura do Projeto

```
smarttasks-tests/
│
├── README.md
├── postman/
│   └── smarttasks_collection.json
│
└── test-cases/
    ├── login.md
    └── register.md
```
---

## 🧪 Casos de Teste

### 🧪 Teste de disponibilidade da API

**Objetivo:**  
Validar se a API está respondendo corretamente.

**Passos:**
1. Enviar requisição **GET** `/test`

**Resultado esperado:**
- Status 200 (OK)
- Retorno "API OK!"

---

### 🔐 Login com sucesso

**Objetivo:**  
Validar se o usuário consegue realizar login com credenciais válidas.

**Pré-condição:**  
Usuário previamente cadastrado.

**Passos:**
1. Enviar requisição **POST** `/auth/login`
2. Informar email válido
3. Informar senha correta

**Resultado esperado:**
- Status 200 (OK)
- Retorno de token JWT

---

### ❌ Login com senha inválida

**Objetivo:**  
Validar comportamento do sistema ao informar senha incorreta.

**Passos:**
1. Enviar requisição **POST** `/auth/login`
2. Informar email válido
3. Informar senha incorreta

**Resultado esperado:**
- Status 401 (Unauthorized)
- Mensagem informando credenciais inválidas

---

### 🆕 Cadastro de usuário

**Objetivo:**  
Validar criação de novo usuário.

**Passos:**
1. Enviar requisição **POST** `/auth/register`
2. Informar nome, email e senha válidos

**Resultado esperado:**
- Status 201 (Created)
- Cadastro realizado com sucesso.

---

## 📬 Testes com Postman

A coleção de testes está disponível em:

```text
/postman/smarttasks_collection.json
```

### Como utilizar:

1. Abrir o Postman  
2. Importar a coleção  
3. Executar as requisições  

---

## 🔐 Autenticação

O sistema utiliza autenticação via **JWT (JSON Web Token)**.

Para acessar endpoints protegidos, incluir no header:

```text
Authorization: Bearer {token}
```

---

## 🧠 Considerações

Durante os testes, foi identificado que:

- A API não valida formato de email
- A API não possui validação de complexidade de senha

Esses pontos foram registrados como oportunidades de melhoria.

---

## 🚀 Sobre o projeto

Este projeto foi desenvolvido para aplicar na prática conceitos de **Qualidade de Software (QA)**, testes de API e validação de sistemas, com foco na análise de regras de negócio e comportamento de aplicações.

---

## 📌 Observações

Os testes foram elaborados com base no comportamento esperado da API, considerando cenários reais de uso, incluindo validações de sucesso e falha.

---

## 👩‍💻 Autora

**Daniela Soares**  
🔗 https://www.linkedin.com/in/danielasoares3/
