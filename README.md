# Projeto {Saudogs} - Backend (trabalho-api)

## Descrição

## Descrição
O Saudogs é um sistema desenvolvido para facilitar a gestão de clínicas veterinárias, permitindo o acompanhamento de consultas, tratamentos, pacientes (animais), histórico médico, controle de estoque de medicamentos e muito mais. O projeto visa otimizar o tempo e os processos administrativos da clínica, oferecendo uma solução completa para gerenciar tanto os aspectos clínicos quanto administrativos.


## Tecnologias Utilizadas

- Java {11}
- Banco de Dados {pgAdmin 4}

## Pré-requisitos

- JDK {JDK 11}
- Maven {Maven 3.6.3} 
- Postman
- Swagger

## Instalação

1. **Clone o repositório:**

   ```bash
   git clone https://github.com/costasouza/projeto-cl-nica.git
   ```

2. **Navegue até o diretório do projeto:**

   ```bash
   cd projeto-cl-nica
   ```

3. **Configure o banco de dados:**

   Edite o arquivo [application.yaml](src/main/resources/application.yaml) com as configurações do seu banco de dados.

4. **Compile e execute o projeto:**

   ```bash
   mvn clean install
   mvn spring-boot:run
   ```

   A API estará disponível em `http://localhost:8080`.

## Documentação da API (Swagger)

A documentação da API pode ser acessada por meio do Swagger. Após iniciar o backend, você pode acessar a documentação por meio da seguinte URL:

[/swagger-ui/index.html](http://localhost:8080//swagger-ui/index.html)

## Endpoints

Abaixo está a descrição dos principais endpoints da API:

{Alterar os endpoints conforme os endpoints do projeto}

### **1. GET /api/usuarios**

- **Descrição:** Retorna uma lista de usuários.
- **Parâmetros de Consulta:**
  - `page` (opcional): Número da página.
  - `size` (opcional): Número de itens por página.
- **Resposta:**
  - **200 OK**
    ```json
    [
      {
    "id": 1,
    "nome": "Dug",
    "raca": "Pug",
    "nome_responsavel": "Maria Lurdes Aparecida Gonzaga",
    "cpf_responsavel": "965.587.662-74",
    "endereco": "Rua Mogi das Cruzes, 45-vila poa",
    "telefone_contato": "(11) 96541-6352"
  },
      // ...
    ]
    ```

### **2. POST /api/usuarios**

- **Descrição:** Cria um novo usuário.
- **Corpo da Requisição:**
  ```json
  {
  "nome": "Rex",
  "raca": "Labrador",
  "nome_responsavel": "João Americo",
  "cpf_responsavel": "123.456.789-00",
  "endereco": "Rua ABC, 123",
   "telefone_contato": "(11) 99555-5555"
  }
  ```
- **Resposta:**
  - **201 Created**
    ```json
   {
  "id": 2,
  "nome": "Rex",
  "raca": "Labrador",
  "nome_responsavel": "João Americo",
  "cpf_responsavel": "123.456.789-00",
  "endereco": "Rua ABC, 123",
   "telefone_contato": "(11) 99555-5555"
  }
    ```

### **3. GET /api/usuarios/{id}**

- **Descrição:** Retorna um usuário específico pelo ID.
- **Parâmetros de Caminho:**
  - `id`: 1.
- **Resposta:**
  - **200 OK**
    ```json
  {

  "nome": "Dug",
  "raca": "Pug",
  "nome_responsavel": "Maria Lurdes Aparecida Gonzaga",
  "cpf_responsavel": "965.587.662-74",
  "endereco": "Rua Mogi das Cruzes, 45-vila poa",
  "telefone_contato": "(11) 96541-6352"

  }
    ```
  - **404 Not Found** (se o usuário não for encontrado)

### **4. PUT /api/usuarios/{id}**

- **Descrição:** Atualiza um usuário existente.
- **Corpo da Requisição:**
  ```json
  {
    "telefone_contato": "(11) 98888-8888",
    "endereco": "Rua XYZ, 456",
  }
  ```
- **Parâmetros de Caminho:**
  - `id`: 2.
- **Resposta:**
  - **200 OK**
    ```json
  {

  "id": 2,
  "nome": "Rex ",
  "raca": "Labrador",
  "nome_responsavel": "João Atualizado",
  "cpf_responsavel": "123.456.789-00",
  "endereco": "Rua XYZ, 456",
  "telefone_contato": "(11) 98888-8888"

  }
    ```
  - **404 Not Found** (se o usuário não for encontrado)

### **5. DELETE /api/usuarios/{id}**

- **Descrição:** Remove um usuário pelo ID.
- **Parâmetros de Caminho:**
  - `id`: 2.
- **Resposta:**
  - **204 No Content**
  - **404 Not Found** (se o usuário não for encontrado)
