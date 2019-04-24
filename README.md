# Node JS Structure

## Overview

Node Structure for Orient Software

## Getting Started

Clone the repo:
```sh
git clone https://github.com/minhdang900/nodejs-structure.git
cd nodejs-structure
```

Set environment (vars):
```sh
cp .env.example .env
```

Start server:
```sh
# Start server
npm run start

# Selectively set DEBUG env var to get logs
DEBUG=node-structure:* npm run start
```
Tests:
```sh
# Run tests written in ES6 
npm run test

# Run test along with code coverage
npm run test:coverage

# Run tests on file change
npm run test:watch

# Run tests enforcing code coverage (configured via .istanbul.yml)
npm run test:check-coverage
```

Lint:
```sh
# Lint code with ESLint
npm run lint

# Run lint on any file change
npm run lint:watch
```

##### Deployment

```sh
# compile to ES5
1. npm run build

# upload dist/ to your server
2. scp -rp dist/ user@dest:/path

# install production dependencies only
3. npm run --production

# Use any process manager to start your services
4. pm2 start dist/index.js
```

In production you need to make sure your server is always up so you should ideally use any of the process manager recommended [here](http://expressjs.com/en/advanced/pm.html).
We recommend [pm2](http://pm2.keymetrics.io/) as it has several useful features like it can be configured to auto-start your services if system is rebooted.

## Logging

Universal logging library [winston](https://www.npmjs.com/package/winston) is used for logging. It has support for multiple transports.  A transport is essentially a storage device for your logs. Each instance of a winston logger can have multiple transports configured at different levels. For example, one may want error logs to be stored in a persistent remote location (like a database), but all logs output to the console or a local file. We just log to the console for simplicity, you can configure more transports as per your requirement.

#### API logging
Logs detailed info about each api request to console during development.

#### Error logging
Logs stacktrace of error to console along with other details. You should ideally store all error messages persistently.

## Code Coverage
Get code coverage summary on executing `npm run test`

`npm run test` also generates HTML code coverage report in `coverage/` directory. Open `lcov-report/index.html` to view it.

## Docker

#### Using Docker Compose for Development
```sh
# service restarts on file change
bash bin/development.sh
```

#### Building and running without Docker Compose
```bash
# To use this option you need to make sure mongodb is listening on port 27017

# Build docker 
docker build -t node-structure .

# Run docker
docker run -p 3000:3000 node-structure
```


## Coding Convetion Styles
```
# Use single quotes
Use single quotes, unless you are writing JSON.
Right:
  var foo = 'bar';
Wrong:
  var foo = "bar";
```
## Contributing
## Versioning
## Authors
## License 
## Acknowledgments
