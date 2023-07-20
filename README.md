<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel
Este proyecto requiere de php 8.2 y una base de datos (mariaDB de preferencia).

Esta es una versión basica de laravel 10 implementando autenticación mediante JWT con la libreria jwt-auth, una vez implementado se debe probar con el checkin e intentar acceder a los usuarios. Por defecto se ha colocado 1h de duración del token, pero es personalizable.

Enlaces de referencias


https://jwt-auth.readthedocs.io/en/develop/laravel-installation/

Video base del proyecto realizado (omitiendo detalles) - 
https://www.youtube.com/watch?v=N1QQ1qQP0wo


## Instalación de prueba

* clonar el repositorio, ingresar a la carpeta del repo.
* copiar el archivo .env.example como .env 
* configurar la conexión a la base de datos en el archivo .env
* posteriormente se instalan las librerias y se generan las llaves.

```BASH
composer install
php artisan key:generate
php artisan jwt:secret
php artisan migrate --seed   
```

finalmente se ejecuta el servicio (que se ejecuta por defecto en el puerto 8000)
```
php artisan serve
```

Para probar dentro de insomnia y Postman debe de configurar la autenticacion
* POST - http://127.0.0.1:8000/api/checkin
* dato - JSON 

```JSON
{
	"email":"test@test.com",
	"password":"test.com"
}
```


para la prueba de usuario:
* GET - http://127.0.0.1:8000/api/user
* Auth: Bearer token (aca debe colocar el token generado)
## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
