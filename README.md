# Adana Residencial

La aplicación se encuentra realizada en React 18 y Laravel 10

## Requerimientos:

- php => 8.1
- nodeJs => 16.x
- mysql => 8.X

## Instalación

Ejecutar los siguientes comandos

`cp .env.example .env`

`composer install`

`php artisan key:generation`

`npm install`


## Ejecución

Crar un entorno y configurarlo en .env, por ejemplo adana.dev en Apache

```
APP_URL=https://adana.dev
SERVER_HOST=https://adana.dev
SERVER_HTTPS_KEY="adana.dev.key"
SERVER_HTTPS_CERT="adana.dev.cert"
```

`npm run dev`


En caso de no configurar, ejecutar:

`php artisan serve`

`npm run dev`


## Base de datos

Se puede agregar la base de datos de manera manual o si se desea empezar una base de datos nueva se pueden seguir los siguientes pasos:


**Crear base de datos nueva**

Se debera configurar el acceso en el .env

```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=root
DB_PASSWORD=
```

Ejecutar los comandos:

`php artisan migrate`

Si se desea motificar los lotes, la ruta en donde se encuentran es `database/data/lotes.json`, se puede actualizar la información antes de subir

`php artisan db:seed`

El acceso de admin se encuentra en `database/seeders/AdminSeeder`, se puede modificar a placer.

**Importar BD**

El acceso a admin sigue siendo el mismo que esta en `AdminSeeder`, la información de los lotes se encuentra en el ultimo estado o actualización realizada.

## Producción

Si se realizan cambios en Laravel, solo se deben descargar cambios mediante Git o subirlos de manera manual, en caso de realizar cambios en React, se debera ejecutar previamente el comando 

`npm run build`