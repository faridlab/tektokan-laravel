<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400"></a></p>

<p align="center">
<a href="https://travis-ci.org/laravel/framework"><img src="https://travis-ci.org/laravel/framework.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

# Laravel

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains over 1500 video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the Laravel [Patreon page](https://patreon.com/taylorotwell).

### Premium Partners

- **[Vehikl](https://vehikl.com/)**
- **[Tighten Co.](https://tighten.co)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Cubet Techno Labs](https://cubettech.com)**
- **[Cyber-Duck](https://cyber-duck.co.uk)**
- **[Many](https://www.many.co.uk)**
- **[Webdock, Fast VPS Hosting](https://www.webdock.io/en)**
- **[DevSquad](https://devsquad.com)**
- **[OP.GG](https://op.gg)**

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).


# Installation
[Installation](https://laravel.com/docs/8.x/installation)

## Via Laravel Installer
```bash
$ composer global require laravel/installer
$ laravel new [your-project-name]
```

## Via Composer Create-Project
```bash
$ composer create-project --prefer-dist laravel/laravel [your-project-name]
OR
$ composer create-project --prefer-dist laravel/laravel=6.x [your-project-name]
```

```bash
Creating a "laravel/laravel" project at "./[your-project-name]"
Installing laravel/laravel (v8.4.1)
  - Installing laravel/laravel (v8.4.1): Downloading (100%)
Created project in /Users/utmostphere/Workspace/sagara.id/playground/tektokan-laravel
> @php -r "file_exists('.env') || copy('.env.example', '.env');"
Loading composer repositories with package information
Updating dependencies (including require-dev)
Package operations: 104 installs, 0 updates, 0 removals
  - Installing voku/portable-ascii (1.5.4): Downloading (100%)
  - Installing symfony/polyfill-php80 (v1.20.0): Downloading (100%)
  ...
  - Installing phpunit/phpunit (9.4.3): Downloading (100%)
Writing lock file
Generating optimized autoload files
> Illuminate\Foundation\ComposerScripts::postAutoloadDump
> @php artisan package:discover --ansi
Discovered Package: facade/ignition
Discovered Package: fideloper/proxy
Discovered Package: fruitcake/laravel-cors
Discovered Package: laravel/tinker
Discovered Package: nesbot/carbon
Discovered Package: nunomaduro/collision
Package manifest generated successfully.
71 packages you are using are looking for funding.
Use the `composer fund` command to find out more!
> @php artisan key:generate --ansi
Application key set successfully.
```

## Local Development Server
Run this command below at your root project

```bash
$ php artisan serve
Laravel development server started: http://127.0.0.1:8000
```

# Routing

## Available Router Methods
The router allows you to register routes that respond to any HTTP verb:
```php
Route::get($uri, $callback);
Route::post($uri, $callback);
Route::put($uri, $callback);
Route::patch($uri, $callback);
Route::delete($uri, $callback);
Route::options($uri, $callback);
```

## Example simple route
```php
// Public Transport
Route::get('/transportation/mrt', function () {
    return 'MRT is your transportation';
});

Route::get('/transportation/transjakarta', function () {
    return 'Trans Jakarta is your transportation';
});

Route::get('/transportation/metromini', function () {
    return 'Metromini is your transportation';
});

// Private Transport
Route::get('/transportation/car', function () {
    return 'Car is your transportation';
});

Route::get('/transportation/motorcycle', function () {
    return 'Motorcycle is your transportation';
});
```

## Route Parameters
```php
Route::get('user/{id}', function ($id) {
    return 'User with ID: '.$id;
});

// THis route will not known
Route::get('user/{name}', function ($name) {
    return 'User with name: '.$name;
});

Route::get('greeting/{name?}', function ($name = 'Someone') {
    return 'Hello '.$name;
});
```

## Regular Expression Constraints
```php
Route::get('user/{id}', function ($id) {
    return 'User with ID: '.$id;
})->where('id', '[0-9]+');

// Router knows this route
Route::get('user/{name}', function ($name) {
    return 'User with name: '.$name;
})->where('name', '[A-Za-z]+');

Route::get('greeting/{name?}', function ($name = 'Someone') {
    return 'Hello '.$name;
});
```

## Route Groups
```php
// Share attributes Middleware
Route::middleware(['first', 'second'])->group($callback);
Route::group([
    'middleware' => ['first', 'second']
], function () {
    Route::get($uri, $callback);
    Route::post($uri, $callback);
});

// Nested route with prefix
Route::group([
    'prefix' => 'books',
], function () {
    Route::get('/', function() {
        return 'Here list of Books';
    });
    Route::post('/', function() {
        return 'Post new Book?.';
    });
});
```

# Middleware

## Defining Middleware
To create a new middleware, use the `make:middleware` Artisan command:
```s
$ php artisan make:middleware CheckAge
```

`/app/Http/Middleware/CheckAge.php`
```php
<?php

namespace App\Http\Middleware;

use Closure;

class CheckAge
{
    /**
     * Handle an incoming request.
     *
     * @param  \Illuminate\Http\Request  $request
     * @param  \Closure  $next
     * @return mixed
     */
    public function handle($request, Closure $next)
    {
        if ($request->age <= 18) {
            return redirect('teenager');
        }
        return $next($request);
    }
}
```

## Registering Middleware
`app/Http/Kernel.php`
```php
...
protected $routeMiddleware = [
    ...
    'checkage' => \App\Http\Middleware\CheckAge::class,
];
...
```

Add route and checkage middleware
```php
Route::get('teenager', function () {
    return 'Youre smell like kencur';
});

Route::get('adult', function () {
    return 'Youre adult now';
})->middleware('checkage');
```

# Controllers

## Creating Controller
To create a new controller, use the `make:controller` Artisan command:
```s
$ php artisan make:controller PhotoController
```

`/app/Http/Controllers/PhotoController.php`
```php
<?php

namespace App\Http\Controllers;

use Illuminate\Http\Request;

class PhotoController extends Controller
{
    public function index()
    {
        return 'You see all photos in the gallery';
    }

    public function show($id)
    {
        return 'Showing photo by ID: '.$id;
    }
}
```

Route
```php
// Add namespace
Route::group([
    'namespace' => 'App\Http\Controllers'
], function() {
    Route::get('photos', 'PhotoController@index');
    Route::get('photos/{id}', 'PhotoController@show');
});

// OR

// import class controller
use App\Http\Controllers\PhotoController;

Route::get('photos', [PhotoController::class, 'index']);
Route::get('photos/{id}', [PhotoController::class, 'show']);
```

## Resource Controllers
To create a new controller, use the `make:controller` Artisan command:
```s
$ php artisan make:controller PhotoController --resource
```

`/app/Http/Controllers/PhotoController.php`
```php
<?php

namespace App\Http\Controllers;

use Illuminate\Http\Request;

class PhotoController extends Controller
{
    /**
     * Display a listing of the resource.
     *
     * @return \Illuminate\Http\Response
     */
    public function index()
    {
        //
    }

    /**
     * Show the form for creating a new resource.
     *
     * @return \Illuminate\Http\Response
     */
    public function create()
    {
        //
    }

    /**
     * Store a newly created resource in storage.
     *
     * @param  \Illuminate\Http\Request  $request
     * @return \Illuminate\Http\Response
     */
    public function store(Request $request)
    {
        //
    }

    /**
     * Display the specified resource.
     *
     * @param  int  $id
     * @return \Illuminate\Http\Response
     */
    public function show($id)
    {
        //
    }

    /**
     * Show the form for editing the specified resource.
     *
     * @param  int  $id
     * @return \Illuminate\Http\Response
     */
    public function edit($id)
    {
        //
    }

    /**
     * Update the specified resource in storage.
     *
     * @param  \Illuminate\Http\Request  $request
     * @param  int  $id
     * @return \Illuminate\Http\Response
     */
    public function update(Request $request, $id)
    {
        //
    }

    /**
     * Remove the specified resource from storage.
     *
     * @param  int  $id
     * @return \Illuminate\Http\Response
     */
    public function destroy($id)
    {
        //
    }
}
```

Route
```php
// Add namespace
Route::group([
    'namespace' => 'App\Http\Controllers'
], function() {
    Route::resource('photos', 'PhotoController');
});

// OR

// import class controller
use App\Http\Controllers\PhotoController;

Route::resource('photos', PhotoController::class);
```

# Views

## Create Layout
```php
<!-- Stored in resources/views/layouts/app.blade.php -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Laravel - @yield('title')</title>
    @yield('css')
</head>
<body>
@section('header')
    <header>HEADER</header>
@show
<div class="container">
    @yield('content')
</div>
@section('footer')
    <footer>FOOTER</footer>
@show
@yield('js')
</body>
</html>
```

```php
<!-- Stored in resources/views/photos/index.blade.php -->
@extends('layouts.app')

@section('title', 'Photos Gallery')

@section('header')
    @parent
    <p>SIDEBAR.</p>
@endsection

@section('content')
    <p>This is my body content.</p>
@endsection

```