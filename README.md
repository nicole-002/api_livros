<div align="center">

# 💜 📚 BIBLIOTECA API

### Sistema Web para Gerenciamento de Livros

**3º Ano · Técnico em Informática para Internet · Sistemas Web II**

<br>

![Python](https://img.shields.io/badge/Python-8B5CF6?style=for-the-badge\&logo=python\&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-A855F7?style=for-the-badge\&logo=fastapi\&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-C084FC?style=for-the-badge\&logo=mysql\&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-7C3AED?style=for-the-badge\&logo=javascript\&logoColor=white)

<br>

> 🚀 **Da persistência dos dados à interface web:** uma aplicação desenvolvida para praticar a integração entre **Banco de Dados, API e Front-end**.

</div>

---

## 💜 Sobre o projeto

O **Biblioteca API** é um projeto acadêmico desenvolvido durante o **3º ano do Curso Técnico em Informática para Internet**, na disciplina de **Sistemas Web II (SW-II)**.

A aplicação tem como foco o **gerenciamento de livros**, utilizando uma arquitetura que integra um banco de dados **MySQL**, uma **API REST desenvolvida em FastAPI** e uma interface web construída com **HTML, CSS e JavaScript**.

O projeto foi desenvolvido com o objetivo de colocar em prática conceitos de desenvolvimento **Back-end, Front-end, banco de dados e integração de sistemas**.

---

## 🎯 Objetivos

|        Objetivo        | Descrição                                                          |
| :--------------------: | ------------------------------------------------------------------ |
|     🔌 **API REST**    | Criar uma API utilizando FastAPI                                   |
| 🗄️ **Banco de dados** | Armazenar e manipular informações utilizando MySQL                 |
|       🔄 **CRUD**      | Implementar operações de criação, consulta, atualização e exclusão |
|    🌐 **Front-end**    | Desenvolver uma interface para interação com a API                 |
|    🔗 **Integração**   | Conectar Front-end, API e banco de dados                           |
|      🧪 **Testes**     | Validar o funcionamento dos endpoints                              |
|  🌱 **Versionamento**  | Utilizar Git e GitHub durante o desenvolvimento                    |

---

# 🏗️ Arquitetura

A aplicação é organizada em **três camadas principais**, permitindo separar as responsabilidades de cada parte do sistema.

```text
                    👤 USUÁRIO
                        │
                        ▼
              ┌──────────────────┐
              │    🌐 FRONT-END  │
              │ HTML · CSS · JS  │
              └────────┬─────────┘
                       │
                    HTTP / Fetch
                       │
                       ▼
              ┌──────────────────┐
              │   ⚡ FASTAPI     │
              │      REST API    │
              └────────┬─────────┘
                       │
                    SQLAlchemy
                       │
                       ▼
              ┌──────────────────┐
              │   🗄️ MYSQL      │
              │  biblioteca_db   │
              └──────────────────┘
```

### 🔄 Fluxo de dados

| Etapa | Responsável       | Função                           |
| :---: | ----------------- | -------------------------------- |
|   01  | 🌐 **Front-end**  | Interface utilizada pelo usuário |
|   02  | ⚡ **FastAPI**     | Recebe e processa as requisições |
|   03  | 🔷 **SQLAlchemy** | Faz a comunicação com o banco    |
|   04  | 🗄️ **MySQL**     | Armazena os dados dos livros     |

---

# 📚 Entidade Livro

O principal recurso da aplicação é o **Livro**.

| Campo               |   Tipo  | Descrição                         |
| ------------------- | :-----: | --------------------------------- |
| 🆔 `id`             | Integer | Identificador único               |
| 📖 `titulo`         |  String | Título da obra                    |
| ✍️ `autor`          |  String | Autor do livro                    |
| 📅 `ano_publicacao` | Integer | Ano de publicação                 |
| ✅ `disponivel`      | Boolean | Indica a disponibilidade do livro |

### 📌 Exemplo

```json
{
  "id": 1,
  "titulo": "Dom Casmurro",
  "autor": "Machado de Assis",
  "ano_publicacao": 1899,
  "disponivel": true
}
```

---

# 🔄 CRUD

O sistema implementa as quatro operações fundamentais para manipulação dos livros.

|    Método   |  Operação  | Endpoint       | Descrição                     |
| :---------: | :--------: | -------------- | ----------------------------- |
|  🟢 `POST`  | **Create** | `/livros`      | Cadastrar um novo livro       |
|   🔵 `GET`  |  **Read**  | `/livros`      | Listar todos os livros        |
|   🔵 `GET`  |  **Read**  | `/livros/{id}` | Consultar um livro específico |
|   🟠 `PUT`  | **Update** | `/livros/{id}` | Atualizar um livro            |
| 🔴 `DELETE` | **Delete** | `/livros/{id}` | Excluir um livro              |

---

# ⚡ API

A API foi construída utilizando o **FastAPI**, seguindo o padrão REST para comunicação entre o sistema e os dados armazenados.

## 📡 Endpoints

### 🟢 Criar livro

```http
POST /livros
```

Responsável por cadastrar um novo livro no banco de dados.

---

### 🔵 Listar livros

```http
GET /livros
```

Retorna todos os livros cadastrados.

---

### 🔎 Consultar livro

```http
GET /livros/{livro_id}
```

Busca um livro específico utilizando seu identificador.

---

### 🟠 Atualizar livro

```http
PUT /livros/{livro_id}
```

Permite alterar as informações de um livro existente.

---

### 🔴 Excluir livro

```http
DELETE /livros/{livro_id}
```

Remove um livro do banco de dados.

---

# 🗄️ Banco de dados

O banco utilizado no projeto é o **MySQL**, administrado por meio do **phpMyAdmin**, através do ambiente **XAMPP**.

| Configuração      | Valor                |
| ----------------- | -------------------- |
| 🗃️ SGBD          | MySQL                |
| 📦 Banco          | `biblioteca_db`      |
| 🛠️ Administração | phpMyAdmin           |
| 🖥️ Ambiente      | XAMPP                |
| 🔗 Comunicação    | SQLAlchemy + PyMySQL |

O projeto também possui um arquivo SQL para possibilitar a reconstrução do banco de dados:

```text
database/
└── biblioteca_db.sql
```

---

# 🧩 Tecnologias

<div align="center">

|     Tecnologia     | Utilização                            |
| :----------------: | ------------------------------------- |
|    🐍 **Python**   | Linguagem principal do Back-end       |
|    ⚡ **FastAPI**   | Desenvolvimento da API REST           |
|   🚀 **Uvicorn**   | Servidor da aplicação                 |
|  🔷 **SQLAlchemy** | ORM e comunicação com o banco         |
|    🐬 **MySQL**    | Banco de dados relacional             |
|   🔌 **PyMySQL**   | Driver de conexão com MySQL           |
|    🖥️ **XAMPP**   | Ambiente para execução do MySQL       |
| 🗂️ **phpMyAdmin** | Administração do banco                |
|    🌐 **HTML5**    | Estrutura do Front-end                |
|     🎨 **CSS3**    | Estilização da interface              |
|  ⚙️ **JavaScript** | Interação e consumo da API            |
|     🌱 **Git**     | Controle de versão                    |
|    🐙 **GitHub**   | Hospedagem e versionamento do projeto |

</div>

---

# 📁 Estrutura do projeto

```text
📦 biblioteca-api
│
├── 📂 database
│   └── 🗄️ biblioteca_db.sql
│
├── 📂 frontend
│   ├── 🌐 index.html
│   ├── 🎨 style.css
│   └── ⚙️ script.js
│
├── ⚡ main.py
├── 🗄️ database.py
├── 📚 models.py
├── 📋 schemas.py
├── 📦 requirements.txt
└── 📖 README.md
```

> 📌 A estrutura pode variar conforme a organização final dos arquivos do projeto.

---

# 🧪 Testes

Durante o desenvolvimento foram realizados testes para verificar o comportamento dos endpoints e das operações do CRUD.

Também foram utilizados **mocks** para possibilitar testes da API sem depender diretamente de uma instância real do banco de dados.

### 🔬 Principais pontos testados

| Teste          | Verificação                         |
| -------------- | ----------------------------------- |
| 📋 Listagem    | Retorno dos livros cadastrados      |
| ➕ Criação      | Cadastro de novos registros         |
| 🔎 Consulta    | Busca por ID                        |
| ✏️ Atualização | Alteração de registros              |
| 🗑️ Exclusão   | Remoção de registros                |
| ⚠️ Erros       | Tratamento de recursos inexistentes |

---

# 🚀 Como executar

## 1️⃣ Clonar o repositório

```bash
git clone URL_DO_REPOSITORIO
cd biblioteca-api
```

---

## 2️⃣ Criar ambiente virtual

```bash
python -m venv venv
```

### Windows

```bash
venv\Scripts\activate
```

---

## 3️⃣ Instalar dependências

```bash
pip install -r requirements.txt
```

---

## 4️⃣ Configurar o MySQL

Abra o **XAMPP** e inicie:

```text
☑ Apache
☑ MySQL
```

Depois, abra o **phpMyAdmin** e importe:

```text
database/biblioteca_db.sql
```

---

## 5️⃣ Executar a API

```bash
uvicorn main:app --reload
```

A API estará disponível em:

```text
http://127.0.0.1:8000
```

### 📖 Documentação automática

O FastAPI disponibiliza uma interface interativa para visualizar e testar os endpoints:

```text
http://127.0.0.1:8000/docs
```

---

# 🌐 Front-end

A interface web utiliza **HTML, CSS e JavaScript** para consumir os endpoints da API.

As requisições são realizadas utilizando o `fetch()` do JavaScript.

```text
🌐 Interface
     │
     ▼
JavaScript
     │
     │ fetch()
     ▼
⚡ API FastAPI
     │
     ▼
🗄️ MySQL
```

Dessa forma, as ações realizadas pelo usuário na interface são comunicadas à API, que processa as operações e realiza a persistência dos dados.

---

# 📚 Conteúdos desenvolvidos

O projeto reúne conhecimentos trabalhados ao longo da disciplina de **Sistemas Web II**:

```text
🐍 Python
   │
   ├── ⚡ FastAPI
   ├── 📋 Pydantic
   └── 🔷 SQLAlchemy
          │
          ▼
     🗄️ MySQL
          │
          ▼
     🔌 API REST
          │
          ▼
   🌐 HTML + CSS + JS
          │
          ▼
       👤 Usuário
```

### 💡 Conceitos aplicados

* APIs REST
* Métodos HTTP
* CRUD
* Modelagem de banco de dados
* ORM
* Validação de dados
* Tratamento de exceções HTTP
* Integração Back-end e Front-end
* Consumo de API com `fetch`
* Testes automatizados
* Git e GitHub

---

# 🎓 Contexto acadêmico

| Informação        | Detalhes                             |
| ----------------- | ------------------------------------ |
| 🏫 **Curso**      | Técnico em Informática para Internet |
| 🎓 **Ano**        | 3º Ano                               |
| 📘 **Disciplina** | Sistemas Web II                      |
| 📅 **Período**    | 3º Bimestre                          |
| 📚 **Tema**       | Gerenciamento de livros              |
| 💻 **Tipo**       | Projeto acadêmico                    |

---

# 👩‍💻 Desenvolvimento

Projeto desenvolvido como parte das atividades acadêmicas do **Curso Técnico em Informática para Internet**.

### 💜 Sistemas Web II

> **Banco de Dados → API → Front-end**

O projeto representa a aplicação prática dos conhecimentos adquiridos durante o desenvolvimento da disciplina, integrando diferentes tecnologias para construir uma aplicação web funcional.

---

<div align="center">

## 💜 Desenvolvido com tecnologia, código e muitos livros. 📚

**Sistemas Web II · 3º Ano · Técnico em Informática para Internet**

<br>

`Python` · `FastAPI` · `MySQL` · `HTML` · `CSS` · `JavaScript`

</div>
