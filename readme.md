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

## Управление проектом

### Запустить докер

```bash
docker-compose up -d
```

### Остановить докер

```bash
docker-compose down -v
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

_`--rm` означает, что контейнер будет удалён после выхода._