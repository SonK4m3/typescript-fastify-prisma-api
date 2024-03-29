# fastify-ts-prima

This project is a small but feature complete application build with Fastify, Prisma, PostgreSQL and Docker, and it aims to show all concepts of Fastify.

There is no attached to blog post or tutorial, you should go to through the application code and read the comments, which will explain you.

## What is this application doing?

This application provides API functions for interacting with the login, management book and product.

The user logins via JWT authentication.

## Project structure

The project follows a well established pattern within the Fastify community.

```
D:\NODEJS\FASTIFY-TS-PRISMA\SRC
│   index.ts
│   prisma.ts
│
├───controllers
│       book.controller.ts
│       product.controller.ts
│       user.controller.ts
│
├───middleware
│       authorize.ts
│       index.ts
│
├───models
├───plugins
│       authenticate.plugin.ts
│       authorization.plugin.ts
│
├───repositories
│       book.repository.ts
│       product.repository.ts
│       user.repository.ts
│
├───routes
│       book.route.ts
│       foo.route.ts
│       index.ts
│       product.route.ts
│       user.route.ts
│
├───services
│       book.services.ts
│       product.services.ts
│       user.services.ts
│
├───tests
├───utils
│       formater.ts
│       hash.ts
│
└───validators
        book.schema.ts
        product.schema.ts
        user.schema.ts
```

### Why aren't you using a try-catch block in route declarations?

Fastify supports promises/async-await [out of the box](https://www.fastify.io/docs/latest/Routes/#async-await).
Everything is handled for you, if you throw an error inside a route handler (same goes
for hooks or plugins) the error will be caught automatically by Fastify and return
the most approriate error.
