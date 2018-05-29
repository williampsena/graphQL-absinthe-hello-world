# Hello World Absinthe GraphQL

## Techs Involved

- PostGres as database
- Elixir as language
- GraphQL by Absinthe Framework
- Docker as PostGres provider

## Install dependencies

First of all, install all dependencies.

```bash
mix deps.get
```

## Start

To start your Phoenix app:

`mix phoenix.server`

Now you can visit [`localhost:4000`](http://localhost:4000) from your browser.

## Create PostGres Database

I recommend you to use Postgres on Docker:

```bash
sudo docker run --name my-postgres -d -p 5432:5432 -e POSTGRES_PASSWORD=postgres -e POSTGRES_DATABASE=dev postgres:alpine

sudo docker run --name my-pgadmin -d -p 1234:80 \
-e "PGADMIN_DEFAULT_EMAIL=postgres" \
-e "PGADMIN_DEFAULT_PASSWORD=postgres" \
-d dpage/pgadmin4
```

After prepare Postgres database, run ecto migrations

```bash
mix ecto.setup
```

## GraphQL

Queries sample to run and test on browser using GraphiQL.

### Queries

Get all links

```
{
	allLinks {
    id
    description
    url
  }
}
```

### GraphQL Mutation
Create a link

```
mutation {
  createLink(
    url: "http://www.google.com",
    description: "Google!",
  ) {
    id
    url
    description
  }
}
```

## Learn more

  - Phoenix instructions:

  * Official website: http://www.phoenixframework.org/
  * Guides: http://phoenixframework.org/docs/overview
  * Docs: https://hexdocs.pm/phoenix
  * Mailing list: http://groups.google.com/group/phoenix-talk
  * Source: https://github.com/phoenixframework/phoenix

  - GraphQL instructions:

  * GraphQL: https://graphql.org/
  * Absinthe GraphQL: http://absinthe-graphql.org/
