 Aqui está um modelo básico de README.md para o seu projeto:

```markdown
# API de Sensores com FastAPI e PostgreSQL

Este projeto é uma API desenvolvida com FastAPI e PostgreSQL para coletar e gerenciar dados de sensores de um ESP. A API permite a inserção e consulta de dados, como ID, RFID, peso, preço e nome dos produtos.

## Tecnologias Utilizadas

- **Python**: Linguagem de programação utilizada.
- **FastAPI**: Framework para criar APIs rápidas e modernas.
- **PostgreSQL**: Sistema de gerenciamento de banco de dados relacional.
- **SQLAlchemy**: ORM para interagir com o banco de dados.
- **Uvicorn**: Servidor ASGI para rodar a aplicação FastAPI.

## Configuração do Ambiente

1. **Clone o Repositório**

   ```bash
   git clone https://github.com/SEU_USUARIO/SEU_REPOSITORIO.git
   cd SEU_REPOSITORIO
   ```

2. **Crie e Ative um Ambiente Virtual**

   ```bash
   python -m venv .venv
   ```

   - No Windows:

     ```bash
     .venv\Scripts\activate
     ```

   - No macOS/Linux:

     ```bash
     source .venv/bin/activate
     ```

3. **Instale as Dependências**

   ```bash
   pip install -r requirements.txt
   ```

4. **Configure o Banco de Dados**

   Certifique-se de substituir a URL do banco de dados no código pela URL do seu banco de dados PostgreSQL.

5. **Execute a API**

   ```bash
   uvicorn main:app --reload
   ```

   A API estará disponível em `http://127.0.0.1:8000`.

## Endpoints da API

### Inserir Dados do Sensor

- **Método**: `POST`
- **Endpoint**: `/sensor_data/`
- **Request Body**:

  ```json
  {
    "esp_id": "ESP32_001",
    "rfid": "123456789",
    "peso": 12.5,
    "preco": 35.0,
    "nome": "Produto A"
  }
  ```

- **Resposta**: 

  ```json
  {
    "id": 1,
    "esp_id": "ESP32_001",
    "rfid": "123456789",
    "peso": 12.5,
    "preco": 35.0,
    "nome": "Produto A"
  }
  ```

### Consultar Dados do Sensor

- **Método**: `GET`
- **Endpoint**: `/sensor_data/`
- **Resposta**:

  ```json
  [
    {
      "id": 1,
      "esp_id": "ESP32_001",
      "rfid": "123456789",
      "peso": 12.5,
      "preco": 35.0,
      "nome": "Produto A"
    }
  ]
  ```
