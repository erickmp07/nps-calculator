<h1 align="center">NPS-calculator</h1>

<p align="center">
    <a href="#technologies">Technologies</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
    <a href="#project">Project</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
    <a href="#diagram">Diagram</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
    <a href="#how-to-run">How to run</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
    <a href="#license">License</a>
</p>

<p align="center">
    <img alt="License" src="https://img.shields.io/github/license/erickmp07/NPS-calculator">
</p>

<br>

<p align="center">
    <img alt="NPS-calculator" src="public/nps-calculator.png">
</p>

## Technologies

This project was developed with the following technologies:

- [TypeScript](https://www.typescriptlang.org)
- [Node.js](https://nodejs.org)
- [Yarn](https://yarnpkg.com/)
- [Docker](https://www.docker.com/)
- [Nodemailer](https://nodemailer.com)
- [Ethereal-Email](https://ethereal.email)
- [TypeORM](https://typeorm.io/#/)
- [Express](https://expressjs.com/)
- [Handlebars](https://handlebarsjs.com/)
- [Jest](https://jestjs.io/)
- [SQLite3](https://sqlite.org)

## Project

The NPS-calculator is an application that calculates a company's NPS (Net Promoter Score). We register user, survey, send email to users answer the surveys and then calculate the NPS.

## Diagram

<img alt="Application Diagram" src="public/diagram.png">

## How to run

### Locally

Prerequisites:

Download and install [Node.js](https://nodejs.org/en/download/) and [Yarn](https://classic.yarnpkg.com/en/docs/install/)

<br>

- Clone the repository
```bash
git clone https://github.com/erickmp07/NPS-calculator.git
```
- Install the dependencies with [`yarn` command](https://classic.yarnpkg.com/en/docs/usage):
```bash
yarn
```

<br>

To start the server:
```bash
yarn dev
```

<br>

To run the tests:
```bash
yarn test
```

<br>

The application can be accessed at [`localhost:3333`](http://localhost:3333) .

The available routes are:

```bash
# POST (JSON) - Create User
http://localhost:3333/users
body: {
    "name": "username",
    "email": "email@domain.com"
}

# POST (JSON) - Create Survey
http://localhost:3333/surveys
body: {
    "title": "title",
    "description": "description"
}

# GET - Show Surveys
http://localhost:3333/surveys

# POST (JSON) - Send Mail
http://localhost:3333/sendMail
body: {
    "email": "user_email",
    "survey_id": "survey_id"
}

# GET - Answer Survey
http://localhost:3333/answers/:value

# GET - Calculate NPS
http://localhost:3333/nps/:survey_id
```

<br>

### Docker container

Prerequisites:

Download and install [Docker](https://www.docker.com/products/docker-desktop)

<br>

- Clone the repository
```bash
git clone https://github.com/erickmp07/NPS-calculator.git
```
- Build the image with the command:
```bash
docker build -t <username>/<app-name> .
```
- Run the image with the command:
```bash
docker run -p 49160:3333 -d <username>/<app-name>
```

<br>

The application can be accessed at [`localhost:49160`](http://localhost:49160) .

The available routes are:

```bash
# POST (JSON) - Create User
http://localhost:49160/users
body: {
    "name": "username",
    "email": "email@domain.com"
}

# POST (JSON) - Create Survey
http://localhost:49160/surveys
body: {
    "title": "title",
    "description": "description"
}

# GET - Show Surveys
http://localhost:49160/surveys

# POST (JSON) - Send Mail
http://localhost:49160/sendMail
body: {
    "email": "user_email",
    "survey_id": "survey_id"
}

# GET - Answer Survey
http://localhost:49160/answers/:value

# GET - Calculate NPS
http://localhost:49160/nps/:survey_id
```

## License

Licensed under [MIT](LICENSE) license.