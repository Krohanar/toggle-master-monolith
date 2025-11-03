# 🚀 API de Feature Flags

API simples e eficiente para **gerenciamento de feature flags** — permitindo ativar ou desativar funcionalidades do sistema de forma dinâmica.

---

## 🧩 Funcionalidades

- Criar uma nova *feature flag*  
- Listar todas as *feature flags*  
- Consultar o status de uma flag específica  
- Atualizar o status (`is_enabled`) de uma flag

---

## 🛠️ Tecnologias utilizadas

- **Python 3.x**
- **Flask**
- **PostgreSQL**
- **psycopg2**
- **Swagger (OpenAPI 3.0)** para documentação

---

## 🔗 Endpoints da API

| Método | Endpoint | Body (Exemplo) | Descrição |
|--------|-----------|----------------|------------|
| **POST** | `/flags` | `{ "name": "new-feature", "is_enabled": true }` | Cria uma nova feature flag |
| **GET** | `/flags` | — | Lista todas as flags existentes |
| **GET** | `/flags/<nome-da-flag>` | — | Retorna o status de uma flag |
| **PUT** | `/flags/<nome-da-flag>` | `{ "is_enabled": false }` | Atualiza o status de uma flag |

---

## 💬 Exemplos de uso

### ➕ Criar uma flag
```bash
POST http://15.228.243.35:5000/flags
Content-Type: application/json

{
    "name": "new-feature-2",
    "is_enabled": true
}
```
**Resposta:**
```json
{
    "message": "Flag 'new-feature-2' criada com sucesso"
}
```

---

### 📋 Listar todas as flags
```bash
GET http://15.228.243.35:5000/flags
```
**Resposta:**
```json
[
    {
        "is_enabled": false,
        "name": "new-feature"
    }
]
```

---

### 🔍 Consultar uma flag específica
```bash
GET http://15.228.243.35:5000/flags/new-feature
```
**Resposta:**
```json
{
    "is_enabled": false,
    "name": "new-feature"
}
```

---

### 🔄 Atualizar o status de uma flag
```bash
PUT http://15.228.243.35:5000/flags/new-feature-2
Content-Type: application/json

{
    "is_enabled": false
}
```
**Resposta:**
```json
{
    "message": "Flag 'new-feature-2' atualizada"
}
```
### Swagger:

Para visualizar no swagger, abrir o link: https://editor.swagger.io/
E colar o código que está no swagger.yaml.
