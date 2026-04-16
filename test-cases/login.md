# 🔐 Testes de Login

## 📌 Endpoint
POST `/auth/login`

---

## ✅ Login com sucesso

**Objetivo:**  
Validar se o usuário consegue realizar login com credenciais válidas

**Pré-condição:**  
Usuário previamente cadastrado

**Dados de teste:**
```json
{
  "email": "dani@teste.com",
  "senha": "123456"
}
```
**Passos:**
1. Enviar requisição POST `/auth/login`
2. Informar email válido
3. Informar senha correta

**Resultado esperado:**
- Status 200
- Retorno de token JWT
- Estrutura da resposta válida

---

## ❌ Login com senha inválida

**Objetivo:**  
Validar comportamento ao informar senha incorreta

**Dados de teste:**
```json
{
  "email": "dani@teste.com",
  "senha": "senha_errada"
}
```
**Passos:**
1. Enviar requisição POST `/auth/login`
2. Informar email válido
3. Informar senha incorreta

**Resultado esperado:**
- Status 401 (Unauthorized)
- Mensagem de erro

---

## ❌ Login com usuário inexistente

**Objetivo:**  
Validar comportamento ao informar usuário não cadastrado

**Dados de teste:**
```json
{
  "email": "naoexiste@teste.com",
  "senha": "123456"
}
```
**Passos:**
1. Enviar requisição POST `/auth/login`
2. Informar email inexistente
3. Informar senha qualquer

**Resultado esperado:**
- Status 401 ou 403
- Mensagem de erro

## ⚠️ Campos obrigatórios

**Objetivo:**  
Validar comportamento ao enviar campos vazios

**Dados de teste:**
```json
{
  "email": "",
  "senha": ""
}
```

**Passos:**
1. Enviar requisição POST `/auth/login`
2. Deixar campos vazios

**Resultado esperado:**
- Status 400 (ou conforme regra da API)
- Mensagem informando campos obrigatórios
