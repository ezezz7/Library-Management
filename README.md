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

### Verfique se o nodejs está instalado:

```bash
node -v

```
### Prossiga com a instalação do Adonis

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
**Para as configurações, selecione: `PostegreSQL` -> `Terminal`.
No arquivo `env.ts`, utilize as variáveis:**

```bash
PG_HOST: Env.schema.string({ format: 'host' }),
PG_PORT: Env.schema.number(),
PG_USER: Env.schema.string(),
PG_PASSWORD: Env.schema.string.optional(),
PG_DB_NAME: Env.schema.string(),
```

**No arquivo `.env`, selecione suas informações do docker. Se seguiu o guia, deve ficar assim:**
```bash
DB_CONNECTION=pg
PG_HOST=localhost
PG_PORT=5432
PG_USER=ṕostgres
PG_PASSWORD=secret
PG_DB_NAME=biblioteca
```

## 🔐 Autenticação

### Instale o Auth
```bash
yarn add @adonisjs/auth@8.2.3
```
### Configure o Auth
```bash
node ace configure @adonisjs/auth
```
**Para as configurações, selecione: `Lucid` -> `Api Tokens`, e digite `User` quando perguntado o nome do modelo para autenticação. Selecione em seguida `true` e `Database`**

## 🎲 Modelo de Banco de Dados
### Baseie-se no modelo de banco de dados a seguir para replicar e ajustar as configurações em `Models` e em `Migrations`

*Aqui colocar só a tabela de User*

### Feito isso, crie mais duas migrations, uma para `Livro` e uma para `Emprestimo`, e as configure em `Models` e em `Migrations, fazendo as relações necessárias`

node ace make:model Livro -c -m

node ace make:model Emprestimo -c -m

**Aqui está o diagrama completo para embasamento:**

*Colocar o diagrama completo aqui*

### Com tudo feito adequadamente, execute o comando a seguir para rodar as migrations:**
```bash
node ace migration:run
```
