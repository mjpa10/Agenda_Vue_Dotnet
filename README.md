# Agenda Vue Dotnet

**Descrição**:  
Este projeto combina o projeto **Vue.js_Agenda** para o frontend, o **.Net_Agenda** para o backend e o ambiente isolado do **Docker** para orquestrar tudo em um único container. 

A aplicação é um sistema de **agenda de contatos**, onde o **frontend** (Vue.js) se comunica com o **backend** (API em .NET) e com o **banco de dados** (MySQL) para gerenciar, exibir e atualizar informações de contatos. Tudo isso rodando de forma simplificada e eficiente em um **contêiner Docker**, que garante a portabilidade, escalabilidade e a facilidade de gerenciamento do projeto.

A arquitetura foi projetada para ser modular, permitindo que você execute e desenvolva cada parte do sistema de forma independente, mas sempre com a garantia de que o **frontend**, **backend** e **banco de dados** estão **perfeitamente conectados** e funcionando em harmonia.

**Projetos Incluídos**:
- **Frontend**: [Vue.js_Agenda](https://github.com/mjpa10/Vue.js_Agenda) – Um projeto Vue.js que fornece a interface interativa para gerenciamento de contatos.
- **Backend**: [API_Agenda](https://github.com/mjpa10/.Net_Agenda) – Uma API em .NET que lida com o processamento e armazenamento dos dados de contatos em um banco de dados, garantindo a integridade dos dados e evitando duplicidade.

---

## Índice

- [Visão Geral](#visão-geral)
- [Pré-requisitos](#pré-requisitos)
- [Como Instalar](#como-instalar)
- [Como Usar](#como-usar)
- [Estrutura de Diretórios](#estrutura-de-diretórios)

---

## Visão Geral

Este repositório reúne dois projetos essenciais em um único ambiente Docker: o **frontend** desenvolvido com **Vue.js** e a **API** construída com **.NET**. Juntos, eles formam uma aplicação completa de **gerenciamento de contatos**, onde o frontend interage com a API backend para realizar operações de CRUD (Criação, Leitura, Atualização e Exclusão) de contatos, com validações para garantir dados consistentes e sem duplicidade.

### Frontend (Vue.js)
O frontend é responsável pela interface interativa, permitindo aos usuários visualizar, adicionar, editar e excluir contatos de maneira intuitiva. Ele utiliza **Vue.js**, um framework progressivo para construção de interfaces dinâmicas, juntamente com o **Vue Router** para navegação e o **fetch** para comunicação com a API.

**Funcionalidades do Frontend:**
- Gerenciamento de contatos com operações CRUD.
- Validação de e-mails e números de telefone para garantir que sejam únicos.
- Navegação entre diferentes páginas da aplicação.
- Exibição de respostas dinâmicas com base nas requisições feitas à API.

### Backend (API .NET)
O backend é uma API desenvolvida em **.NET 7.0**, que gerencia os contatos e validações de dados, como garantir que não haja duplicação de **e-mails** e **telefones**. A API fornece endpoints para realizar operações CRUD e inclui recursos de **paginamento** e **filtros** para facilitar a busca e exibição dos dados.

**Funcionalidades do Backend:**
- Gerenciamento completo de contatos com CRUD.
- Validação de e-mails e telefones para garantir a unicidade.
- Suporte à **paginação** e **filtros** (por nome, e-mail e telefone).
- Utiliza **Entity Framework Core** para interagir com o banco de dados **MySQL**, garantindo uma arquitetura sólida e de fácil manutenção.

### Integração no Docker
O repositório também configura todos os serviços (frontend, backend e banco de dados) para rodarem de forma orquestrada e isolada dentro de contêineres **Docker**, facilitando o processo de desenvolvimento, execução e escalabilidade da aplicação. O uso do Docker garante que todos os componentes funcionem de forma integrada, sem a necessidade de configurações complexas para cada um dos ambientes.

Esta aplicação oferece uma solução completa e escalável para o gerenciamento de contatos, com todos os componentes perfeitamente conectados e funcionando de maneira simples e eficiente.

---

## Pré-requisitos

- **Docker** (para criar e gerenciar os contêineres)
- **Docker Compose** (para orquestrar os serviços frontend, backend e banco de dados)

Esses são os únicos pré-requisitos necessários para rodar o projeto, já que todos os componentes estão orquestrados dentro de contêineres Docker.

---

## Como Instalar

### 1. Clonar o Repositório
Clone o repositório para sua máquina local:

```bash
git clone https://github.com/mjpa10/Agenda_Vue_Dotnet.git
```

### 2. abrir pasta do projeto

```bash
cd Agenda_Vue_Dotnet
```

### 3. Rodar os Contêineres com Docker Compose

Na pasta do repositório clonado, utilize o Docker Compose para rodar os serviços de backend e frontend:

```bash
docker-compose -f docker-compose.yml -f docker-compose.override.yml up -d
```

## Como Usar

Após configurar e rodar os contêineres, você pode acessar a aplicação da seguinte forma:

### Frontend (Vue.js)
- Acesse a interface de usuário através do navegador:
  - [http://localhost:8080](http://localhost:8080/#/)

### Backend (API .NET)
- A API pode ser acessada através do seguinte endpoint:
  - [http://localhost:5000/api](http://localhost:5000/swagger/index.html)

Esses são os endpoints principais para interação com o sistema de **agenda de contatos**. A partir da interface, você pode:
- Visualizar, adicionar, editar e excluir contatos.
- A API garante que os dados sejam validados para evitar duplicidades no banco (e-mails e telefones).

### Banco de Dados (MySQL)
- O banco de dados é gerido pelo MySQL e está disponível dentro do contêiner, com a configuração fornecida no `docker-compose.yml`.
- Não é necessário interação direta com o banco de dados para utilizar a aplicação, mas ele está disponível para consulta ou manutenção, caso necessário.

---

