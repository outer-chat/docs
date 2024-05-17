---
title: Docker
sidebar_position: 2
---

```bash
git clone git@github.com:outer-chat/outer-chat.git --recurse-submodules
cd outer-chat
docker compose up -d
```

This snippet only up the database. So you need to start the server with :

```bash
npm install
npm run build
npm run start:prod
```

You can now access the server !

---

But, if you want to up the whole stack, you can use the `compose.prod.yml` file at the root of the project.

```bash
docker compose -f compose.prod.yml up -d
```

As you may, you can edit the env variables in your `.env` file.
And edit the Caddyfile to match your domain.

:::note

The `compose.prod.yml` also launch the clientapp. If not already done, I invite you to pull the submodule located in : `./client` (From the outer-chat repository).

```bash
git submodule init
git submodule update
```
:::

