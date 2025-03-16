# Стартовый докер для wordpress

## Структура

`/.tmp` - После запуска докера содержит файлы базы данных и wordpress  
`/docker` - Папка для конфигураций и прочих файлов докера  
`/plugin` - Папка для создания core-плагина  
`/theme` - Папка для создания темы  
`.env` - Файл содержит все переменные для докера  
`.gitignore` - Стандартный гитигнор файл  
`docker-compose.yml` - Конфигурация докера  
`readme.md` - Документация проекта

## Доступы по умолчанию
- **WordPress**
  - URL: http://localhost:8000
  - Dashboard: http://localhost:8000/wp-admin
  - Login: admin
  - Password: admin
- **phpMyAdmin**
  - Dashboard: http://localhost:8181
  - Login: wordpress
  - Password: wordpress

## Управление проектом

### Запустить докер

```bash
docker-compose up -d
```

### Остановить докер

```bash
docker-compose down -v
```

## Установка WP

1. Поднимаем WP-CLI
```bash
docker-compose run --rm wp-cli bash
```

2. Скачивание WP
```bash
wp core download --version=$WORDPRESS_VERSION
```

3. Генерация конфиг файла
```bash
wp config create --dbname=$WORDPRESS_DB_NAME --dbuser=$WORDPRESS_DB_USER --dbpass=$WORDPRESS_DB_PASSWORD --dbhost=$WORDPRESS_DB_HOST
```

4. Установка WP
```bash
wp core install --url=$WORDPRESS_URL --title="$WORDPRESS_TITLE" --admin_user=$WORDPRESS_LOGIN --admin_password=$WORDPRESS_PASSWORD --admin_email=$WORDPRESS_EMAIL
```

5. Выход из WP-CLI
```bash
exit
```

## Сервисы

### Composer

```bash
docker-compose run --rm composer bash
```

### Node.js

```bash
docker-compose run --rm node bash
```

### WP-CLI
```bash
docker-compose run --rm wp-cli bash
```

_`--rm` означает, что контейнер будет удалён после выхода._
