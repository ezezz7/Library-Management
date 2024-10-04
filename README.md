# 📚 Sistema de Gestão de Bibliotecas

O projeto em questão é um sistema para gestão de livros em uma biblioteca. Utilizamos AdonisJS para a simplificação do desenvolvimento de APIs robustas, aproveitando sua arquitetura estruturada para acelerar criação de funcionalidades como rotas, controladores e migrações de banco de dados. 

## 📋 Funcionalidades

- 📕 **Cadastro de livros**: Adicione novos livros ao sistema.
- 🔍 **Pesquisa de livros**: Busque livros por título ou autor.
- 📝 **Registro de empréstimos e devoluções**: Controle quem pegou qual livro e quando deve devolvê-lo.
- 🔐 **Autenticação**: Controle de usuários, permitindo a criação de contas e a autenticação para realizar operações no sistema.

# 🚀 Guia de Projeto

**Siga os passos abaixo para configurar o projeto em sua própria máquina.**
## **🐳 Docker**

### Certifique-se de instalar o Docker, e então crie um container padrão

```bash
docker run –name postgres -p 3333 -e POSTGRES_PASSWORD=secret -d postgres

```

### Rode o SQL 
```bash
docker exec -it postgres sql -U postgres
```

### Crie uma database (colocamos biblioteca)
```bash
create database biblioteca;
```

### Saia do docker com:
```bash
\q
```
## 🏁 Inicialização do AdonisJS

### 👣 Verfique se o nodejs está instalado:

```bash
node -v

```
### ➡️ Prossiga com a instalação do Adonis

```bash
npm init adonis-ts-app@latest api
```
**Ou utilize yarn**

```bash
yarn add adonis-ts-app@latest api
```
**Para as configurações do projeto, selecione: API -> Insira o nome como API -> Selecione "True" para ambos eslint e prettier**

## 📚 Database

### Instale o Lucid

```bash
yarn add @adonisjs/lucid@18.4.0
```
### Configure a biblioteca

```bash
node ace configure @adonisjs/lucid
```
