# Laradock
## Full PHP development environment based on Docker.

Based on [Laradock](https://github.com/laradock/laradock).

### Prerequisites

- Docker
- Docker Compose

### First steps

After clone this repository, run this:

```bash
$ cp env-example .env
```

Consider this directory structure:

```
.
+-- your_php_project/
|   +-- index.php
|   +-- ...
+-- laradock/
|   +-- docker-compose.yml
|   +-- env-example
|   +-- ...
```

1. Open the `.env` file in your text editor;
2. Find the `APP_CODE_PATH_HOST` environment variable;
3. Change their value to `../your_php_project` (replace following your directory structure);
4. The result will be `APP_CODE_PATH_HOST=../your_php_project`;
5. Save the file.

### Running the containers

Inside the Laradock folder, run this command (`redis` is optional):

```bash
$ docker-compose up -d nginx php-fpm mysql redis
```

### Working on container

To execute some Composer or Artisan command, you must be connected to the workspace container.

```bash
$ docker-compose exec --user=laradock workspace bash
```

In workspace bash you'll be in the `your_php_project` directory.

### Stopping the containers

```bash
$ docker-compose down
```
