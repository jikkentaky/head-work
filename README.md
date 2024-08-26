# Installation

```Bash
cd your-project-name
npm install
npm run dev
```

## Using with Docker

Pre-requisites:

- Install [Docker](https://www.docker.com/get-docker) for your platform.
- Install [docker-compose](https://docs.docker.com/compose/install/) for your platform.

### Try with Docker

Making sure you're in your project directory, run:

```bash
docker-compose -f docker-compose-dev.yml up
```

### Using on Production with Docker

DISCLAIMER: This Docker configuration is for demonstration purposes only. If you plan to use this configuration in a production remember to adjust the Dockerfile for your project's needs!

Making sure you're in your project directory, run:

```bash
docker-compose -f docker-compose.yml up
```

_By default it uses port 80_

The production Dockerfile uses an nginx instance to run the built website, for more configuration options, see [nginx's dockerhub page](https://hub.docker.com/_/nginx)

# Commits

This project have commits configured to follow the Conventional Commits's best practice and it's configured with ESLint, Prettier and Stylelint.

To commit, you must follow the convention `<type>[optional scope]: <description>`. In practice, it would be as follow:

```git
git commit -m "feat: add button component"
```

Then, Husky will start the pre-commit hook and run lint-staged, who will run `prettier`, `lint` and `stylelint` to validate code format and code lint. If you fail to follow any of these validations, the commit will be aborted.

After that, if everything is validated correctly, Husky will proceed with the commit-msg hook, where it will evaluate if your commit message is following the Conventional Commit's best practice and later run the tests of your project. If any of the tests are broken, the commit will be aborted. You must fix the tests before proceed.

You can also commit your files with the help of the CLI. To do so, just run `npm run commit`. From there, the CLI will assist you in the proccess. As before: if your changes fails the validation, you must fix it before proceed.

As a best practice, it is strongly recommended that you do not skip the validations. If you need to change the way your commit messages are written, just go to file `commitlint.config.ts` and you will find there the config needed.

Check out [commitlint](https://commitlint.js.org/#/) docs to see further configurations that you can do.
