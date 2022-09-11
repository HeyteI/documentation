# Heytel setup
To setup Heytel first of all you need to install it and all of required programs.
Install [Node.js](https://nodejs.org/en/download/), [Go](https://golang.org/dl/), [PostgreSQL](https://www.postgresql.org/download/), [Git](https://git-scm.com/downloads) and [mkcert](https://github.com/FiloSottile/mkcert).

Then install Heytel files:

```bash
git clone https://github.com/HeyteI/heytel-panel
git clone https://github.com/HeyteI/heytel-ws
git clone https://github.com/HeyteI/heytel-api
```

You need to install all dependencies. You can do it by running following command in every cloned directory:

```bash
npm install
```

# Setup PostgreSQL
First of all you need to create database. You can do it by running following command:

```bash
createdb heytel
```

Then you need to create user. You can do it by running following command:

```bash
createuser heytel
```

Then you need to grant all privileges to user. You can do it by running following command:

```bash
psql -c "GRANT ALL PRIVILEGES ON DATABASE heytel TO heytel"
```

Then you need to add required extension to database. You can do it by running following command (without it uuid won't work):

```bash
psql -c "CREATE EXTENSION IF NOT EXISTS 'uuid-ossp'";
```

There is no need to import database scheme because [GORM](https://gorm.io/) will do it automatically.

# Setup API
First of all you need to create `.env` file in `heytel-api` directory. You can do it by running following command:

```bash
cp .env.example .env
```

Then you need to edit `.env` file. You can do it by running following command and setting proper values:

```bash
nano .env
```

# Setup panel
First of all you need to create `.env` file in `heytel-panel` directory. You can do it by running following command:

```bash
cp .env.example .env
```

Then you need to edit `.env` file. You can do it by running following command and setting proper values:

```bash
nano .env
```

# Setup ws
Websockets server doesn't require any configuration.

# Setup SSL
To setup SSL in both `heytel-api` and `heytel-panel` directories do the following specified in [ssl_setup.md](/en/ssl_setup.md).