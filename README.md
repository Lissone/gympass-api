<h1 align="center">
  GymPass API style app
</h1>

<p align="center">
  <a href="#description">Description</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#requirements">Requirements</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#technologies">Technologies</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#usage">Usage</a>
</p>
<br />
<p align="center">
  <img src="https://img.shields.io/static/v1?label=license&message=MIT" alt="License">
  <img src="https://img.shields.io/github/repo-size/Lissone/gympass-api" alt="Repo size" />
  <img src="https://img.shields.io/github/languages/top/Lissone/gympass-api" alt="Top lang" />
  <img src="https://img.shields.io/github/stars/Lissone/gympass-api" alt="Stars repo" />
  <img src="https://img.shields.io/github/forks/Lissone/gympass-api" alt="Forks repo" />
  <img src="https://img.shields.io/github/issues-pr/Lissone/gympass-api" alt="Pull requests" >
  <img src="https://img.shields.io/github/last-commit/Lissone/gympass-api" alt="Last commit" />
</p>

<p align="center">
  <a href="https://github.com/Lissone/gympass-api/issues">Report bug</a>
  ·
  <a href="https://github.com/Lissone/gympass-api/issues">Request feature</a>
</p>

<br />

## Description

This project is a gym management API, inspired by the Gympass model. It provides core functionalities for users, such as registration, authentication, and the ability to check in at gyms. Users can also view their check-in history and personal profiles. The system includes features to search for nearby gyms and specific gyms by name, enhancing the overall user experience.

Additionally, administrators have special privileges to validate check-ins and register new gyms. A strong focus was placed on creating a well-structured project with thorough testing, ensuring reliability and making it easy to scale and expand with new features in the future.

### Functional Requirements

- [x] It must be possible to register;
- [x] It must be possible to authenticate;
- [x] It must be possible to retrieve the profile of a logged-in user;
- [x] It must be possible to get the number of check-ins made by the logged-in user;
- [x] It must be possible for the user to access their check-in history;
- [x] It must be possible for the user to search for nearby gyms (within 10km);
- [x] It must be possible for the user to search for gyms by name;
- [x] It must be possible for the user to check-in at a gym;
- [x] It must be possible to validate a user’s check-in;
- [x] It must be possible to register a gym;

###  Business Rules

- [x] The user must not be able to register with a duplicate email;
- [x] The user cannot check-in twice on the same day;
- [x] The user cannot check-in if they are not close (100m) to the gym;
- [x] The check-in can only be validated up to 20 minutes after being created;
- [x] The check-in can only be validated by administrators;
- [x] Gyms can only be registered by administrators;

### Non-functional Requirements

- [x] The user’s password must be encrypted;
- [x] The application’s data must be persisted in a PostgreSQL database;
- [x] All data lists must be paginated with 20 items per page;
- [x] The user must be identified by a JWT (JSON Web Token);

## Requirements

- [Nodejs](https://nodejs.org/en/)
- [Npm](https://www.npmjs.com/)
- [Yarn](https://yarnpkg.com/)
- [Docker](https://www.docker.com/)

## Technologies

- Nodejs
- Typescript
- Fastify
- Prisma
- Postgresql
- Zod
- Vitest
- Supertest
- Eslint
  - @rockeseat/eslint-config
- Prettier

## Usage

You can clone it on your pc using the command:

```bash
git clone https://github.com/Lissone/gympass-api.git
cd gympass-api
```

>  ❗  You must have **Docker installed** on your machine to get the container up.
**Up Postgres services** in a **Docker container** on your local machine using:

```bash
docker-compose up -d
# View all running containers
docker ps
```

### Add environment variables

```bash
# .\.env

NODE_ENV=dev
PORT=3333

# Auth
JWT_SECRET=

# Database
DATABASE_URL="postgresql://docker:docker@localhost:5432/gympass?schema=public"
```

### Install dependencies

```bash
yarn
#or
npm install
```

### Run migrations

You need to run a prisma script command to run all current migrations:

```bash
npx prisma migrate dev
```

### Run project

```bash
yarn start:dev
#or
npm run start:dev
```

> ℹ️  You can **view the database** from Prisma Studio on the two services that use Prisma, using:

```bash
yarn prisma-studio
#or
npm run prisma-studio
```

## License

Distributed under the MIT License. See `LICENSE` for more information.

<h4 align="center">
  Made with ❤️ by <a href="https://github.com/Lissone" target="_blank">Lissone</a>
</h4>

<hr />