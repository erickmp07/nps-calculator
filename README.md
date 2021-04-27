# nps-calculator

A [Node.js](https://nodejs.org) API to calculate a company NPS (Net Promoter Score).

The nps-calculator is an API where you can register user, survey, send email to users answer the surveys and then the API calculates the NPS.

## Table of Contents

- [Install](#install)
- [Usage](#usage)
- [Technologies](#technologies)
- [API](#api)
- [Contributing](#contributing)
- [License](#license)

## Install

### Locally

Prerequisites:

Download and install [Node.js](https://nodejs.org/en/download/) and [Yarn](https://classic.yarnpkg.com/en/docs/install/).

- First, clone the repository:
```bash
git clone https://github.com/erickmp07/nps-calculator.git
```

- Install its dependencies with [`yarn`command](https://classic.yarnpkg.com/en/docs/usage):
```bash
cd nps-calculator
yarn
```

### Docker container

Prerequisites:

Download and install [Docker](https://www.docker.com/products/docker-desktop).

- First, pull the image with the command:
```bash
docker pull erickmp07/nps-calculator:latest
```

## Usage

### Locally

Start the server:
```bash
yarn dev
```

Note: To run the tests:
```bash
yarn test
```

The application can be accessed at [`localhost:3333`](http://localhost:3333).

### Docker container

Run the image with the command:
```bash
docker run -p 49160:3333 -d erickmp07/nps-calculator
```

The application can be accessed at [`localhost:49160`](http://localhost:49160).


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

## API

The available routes are:

```bash
# POST (JSON) - Create User
http://localhost:{port}/users
body: {
    "name": "username",
    "email": "email@domain.com"
}

# POST (JSON) - Create Survey
http://localhost:{port}/surveys
body: {
    "title": "title",
    "description": "description"
}

# GET - Show Surveys
http://localhost:{port}/surveys

# POST (JSON) - Send Mail
http://localhost:{port}/sendMail
body: {
    "email": "user_email",
    "survey_id": "survey_id"
}

# GET - Answer Survey
http://localhost:{port}/answers/:value

# GET - Calculate NPS
http://localhost:{port}/nps/:survey_id
```

## Contributing

PRs and stars are always welcome.

To ask a question, please [contact me](mailto:erimacedo_92@hotmail.com).

## License

Licensed under [MIT](LICENSE) license.