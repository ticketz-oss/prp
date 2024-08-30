# Docker: Postgres + Redis + PgAdmin4

Este projeto contém um setup simples para o *docker compose* subir serviços
de *Postgres*, *Redis* e *PgAdmin* em Docker.

## Como usar

### Configuração

Crie um arquivo `.env` usando como base o arquivo `.env-example` e defina
nele o nome do usuário e banco padrões e também o login para acesso ao
pgadmin4

> # ATENÇÃO
> 
> O postgres está no modo "trust", por isso este setup não deve ser utilizado
> em servidores na internet, pois aceita conexão sem senha

Se você quiser utilizar as configurações padronizadas, os valores padrão
são:

* Usuário Postgres: `prp`
* Banco de dados: `prp`
* Login do PgAdmin4: `admin@example.com`
* Senha do PgAdmin: `123456`


### Execução

Apenas digitando o seguinte comando executará os três containers:

```bash
docker compose up -d
```

Após alguns segundos o Postgres estará disponível na porta 5432, o redis na
porta 6379 e o PgAdmin4 na porta 8088

Para conectar no banco de dados a partir do PgAdmin4 você deve utilizar o
hostname `postgres` e o usuário que você definiu no .env (ou o default
`admin`). A conexão com o banco de dados não tem senha.
