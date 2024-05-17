---
title: From source
sidebar_position: 3
---

```bash
git clone git@github.com:outer-chat/outer-chat.git --recurse-submodules
cd outer-chat
npm ci
```

:::note
`npm ci` is used to install the dependencies from the `package-lock.json` file. Instead of the `npm install` command, it is faster and more reliable.
:::

Now edit the `.env` file to match your configuration. (you can use the [`.env.example`](.env.example) file as an example)

:::note
In the future, there will be a configuration file for the server and the client.  
At the moment everything all user defined configuration will be fetched from the `.env` file.
:::

Now you can start the server in developpement mode with :

```bash
npm run start:dev
```

Or in production mode with :

```bash
npm run build
npm run start:prod
```

:::note
If you do not want to setup a database, you can use the `compose.yml` file at the root of the project. It will launch a mongodb database. You can edit the env variables in the `compose.yml` file.
:::
