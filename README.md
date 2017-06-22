# Wordpress Docker Compose
A simple docker-compose setup for Wordpress development

## Quick start
```
# Clone the repo
git clone git@github.com:woutrbe/wordpress-docker-compose.git

# Change working directory
cd wordpress-docker-compose

# Start containers
docker-compose up

# Stop containers
docker-compose stop

# Remove containers
docker-compose rm
```

## Configuration

### MYSQL root password
By default the root mysql password will be `rootpassword`, this can be changed in the docker-compose file

```
mysql:
  environment:
    MYSQL_ROOT_PASSWORD: rootpassword

wordpress:
  environment:
    WORDPRESS_DB_USER: root
    WORDPRESS_DB_PASSWORD: rootpassword
```

### MYSQL database name
By default the database name will be `mywordpresssite`, this can be changed in the docker-compose file

```
mysql:
  environment:
    MYSQL_DATABASE: mywordpresssite

wordpress:
  environment:
    WORDPRESS_DB_NAME: mywordpresssite
```

## Theme development
If you're only looking to develop themes, update the docker-compose file with:
```
wordpress:
  volumes:
    - ./src/wp-content/themes/:/var/www/html/wp-content/themes/
```

## Plugin development
If you're only looking to develop plugins, update the docker-compose file with:
```
wordpress:
  volumes:
    - ./src/wp-content/plugins/:/var/www/html/wp-content/plugins/
```