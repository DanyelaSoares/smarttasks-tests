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
  "nome": "Dani",
  "email": "dani@teste.com",
  "senha": "123456"
}
```

**Passos:**
1. Enviar requisição POST `/auth/register`
2. Informar nome válido
3. Informar email válido
4. Informar senha válida

**Resultado esperado:**
- Status 201 (Created)
- Usuário cadastrado com sucesso
- Retorno com dados do usuário (ou mensagem de sucesso)

---

## ❌ Cadastro com email duplicado

**Objetivo:**  
Validar comportamento ao tentar cadastrar um email já existente.

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
- Status 409 (Conflict)
- Mensagem informando que o email já está em uso
  
---

## ❌ Cadastro com email em formato inválido

**Objetivo:**  
Validar o comportamento da API ao informar email em formato inválido.

**Dados de teste:**
```json
{
  "nome": "Dani",
  "email": "email_invalido",
  "senha": "123456"
}
```

**Passos:**
1. Enviar requisição POST `/auth/register`
2. Informar email em formato inválido

**Resultado esperado:**
- Comportamento atual: cadastro permitido (sem validação de formato)
- Observação: a API não possui validação de formato de email implementada
- Sugestão de melhoria: implementar validação para garantir formato válido

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
Validar o comportamento da API ao informar uma senha fora de um padrão mínimo esperado.

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
2. Informar senha fora do padrão esperado

**Resultado esperado:**
- Comportamento atual: cadastro permitido (sem validação de regras de senha)
- Observação: a API não possui validação de complexidade de senha implementada
- Sugestão de melhoria: implementar regras mínimas de senha (ex: tamanho mínimo, combinação de caracteres)
