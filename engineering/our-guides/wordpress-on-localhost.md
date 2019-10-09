# WordPress on localhost

## Symfony Local Web Server

### 0. Installation...

{% embed url="https://symfony.com/doc/current/setup/symfony\_server.html\#installation" %}

```text
symfony proxy:start
```

[https://symfony.com/doc/current/setup/symfony\_server.html\#setting-up-the-local-proxy](https://symfony.com/doc/current/setup/symfony_server.html#setting-up-the-local-proxy)

> If you prefer to use a different TLD, edit the `~/.symfony/proxy.json` file \(where `~` means the path to your user directory\) and change the value of the `tld` option from `wip` to any other TLD.

### 1. Spin up the services \(MySQL, Redis, Mailhog...\)

```bash
docker-compose up -d
```

```yaml
#docker-compose.yml

version: "3.7"

services:

    database:
        image: mysql:5.7
        restart: always
        environment:
            MYSQL_ROOT_PASSWORD: root
            MYSQL_USER: wordpress
            MYSQL_PASSWORD: wordpress
            MYSQL_DATABASE: wordpress
        ports: [3306]
```

### 2. Import the database

```text
docker-compose exec -T database mysql -uwordpress -pwordpress wordpress < database/dumps/some-dump.sql
```

```text
wp search-replace 'http://live-project.tld' 'http://project-domain.test'
```

### 3. Start development server

```bash
symfony server:start --dir=htdocs

# start the server in the background
symfony server:start -d --dir=htdocs
```

### 4. Add the domain

```bash
symfony proxy:domain:attach project-domain --dir=htdocs
```

### 5. Configuration requirements

```php
// FILE: config/wordpress.php

define('DB_HOST', config('database.connections.mysql.host'));
// change to
define('DB_HOST', config('database.connections.mysql.host').':'.config('database.connections.mysql.port'));
```

