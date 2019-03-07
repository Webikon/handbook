# Themosis Local

### Lando

[https://docs.devwithlando.io/](https://docs.devwithlando.io/) How to use it with WordPress [https://docs.devwithlando.io/tutorials/wordpress.html](https://docs.devwithlando.io/tutorials/wordpress.html)

How to initialise a new project

```text
// bash
export $PROJECT_NAME=project-name

// fish shell
set -x PROJECT_NAME project-name
```

```text
mkdir $PROJECT_NAME && cd $PROJECT_NAME
```

```text
lando init \
  --name project-name \
  --recipe wordpress \
  --source remote \
  --remote-url git@gitlab.com:webikon/$PROJECT_NAME.git \
  --webroot htdocs
```

.lando.yml

```text
name: project-name
recipe: wordpress
config:
  webroot: htdocs
services:
  mailhog:
    type: mailhog
    hogfrom:
      - appserver
```

Setup ENV variables in .env

```text
APP_ENV = "local"
APP_DEBUG = true
DATABASE_NAME = "wordpress"
DATABASE_USER = "wordpress"
DATABASE_PASSWORD = "wordpress"
DATABASE_HOST = "database"
APP_URL = "http://wp-themosis-test.lndo.site"
WP_URL = "http://wp-themosis-test.lndo.site/cms"
```

Spin up a project in Lando

```text
# Start it up
lando start

# List information about this app.
lando info
```

Install dependencies

```text
composer install

cd htdocs/content/themes/$PROJECT_NAME-theme

npm install
# or if you're using Yarn
yarn install

# For local development
npm run dev

npm run watch

npm run hot

# For production
npm run production
```

[https://framework.themosis.com/docs/2.0/theme/](https://framework.themosis.com/docs/2.0/theme/)

### Themosis structure

[https://framework.themosis.com/docs/2.0/structure/](https://framework.themosis.com/docs/2.0/structure/)



WordPress quick install

```text
lando wp core install --url=$PROJECT_NAME.lndo.site --title="$PROJECT_NAME" --admin_user=admin --admin_password=admin --admin_email=YOU@webikon.sk
```

[https://docs.devwithlando.io/tutorials/wordpress.html\#tooling](https://docs.devwithlando.io/tutorials/wordpress.html#tooling) [https://wp-cli.org/](https://wp-cli.org/)

[https://robotninja.com/blog/wp-cli-woocommerce-development/](https://robotninja.com/blog/wp-cli-woocommerce-development/)

* create a dir and open it

  ```text
  function mkdircd () { mkdir -p "$@" && cd "$@"; }
  ```

