# 🆕 Testes de Cadastro

## 📌 Endpoint
POST `/auth/register`

---

## ✅ Cadastro com sucesso

**Objetivo:**  
Validar se o usuário consegue se cadastrar com dados válidos

**Dados de teste:**
```json
{
  "name": "Dani",
  "email": "dani@teste.com",
  "password": "123456"
}
```

**Passos:**
1. Enviar requisição POST `/auth/register`
2. Informar nome válido
3. Informar email válido
4. Informar senha válida

**Resultado esperado:**
- Status 200 (ou 201)
- Usuário cadastrado com sucesso
- Retorno com dados do usuário (ou mensagem de sucesso)

---

## ❌ Cadastro com email duplicado

**Objetivo:**  
Validar comportamento ao tentar cadastrar um email já existente

**Dados de teste:**
```json
{
  "nome": "Dani",
  "email": "dani@teste.com",
  "senha": "123456"
}
```

**Passos:**
1. Enviar requisição POST `/auth/register`
2. Informar email já cadastrado

**Resultado esperado:**
- Status 400 (ou conforme regra da API)
- Mensagem informando que o email já está em uso

---

## ❌ Cadastro com email inválido

**Objetivo:**  
Validar comportamento ao informar email em formato inválido

**Dados de teste:**
```json
{
  "nome": "Dani",
  "email": "dani@teste.com",
  "senha": "123456"
}
```

**Passos:**
1. Enviar requisição POST `/auth/register`
2. Informar email inválido

**Resultado esperado:**
- Status 400
- Mensagem informando formato inválido

---

## ⚠️ Campos obrigatórios

**Objetivo:**  
Validar comportamento ao enviar campos vazios

**Dados de teste:**
```json
{
  "nome": "",
  "email": "",
  "senha": ""
}
```

**Passos:**
1. Enviar requisição POST `/auth/register`
2. Deixar campos vazios

**Resultado esperado:**
- Status 400
- Mensagem informando campos obrigatórios

---

## ⚠️ Senha inválida

**Objetivo:**  
Validar regras mínimas de senha (se aplicável)

**Dados de teste:**
```json
{
  "nome": "Dani",
  "email": "dani@teste.com",
  "senha": "123"
}
```

**Passos:**
1. Enviar requisição POST `/auth/register`
2. Informar senha fora do padrão

**Resultado esperado:**
- Status 400
- Mensagem informando regra de senha inválida
