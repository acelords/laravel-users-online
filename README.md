# Laravel Users Online

[![Latest Stable Version](https://poser.pugx.org/acelords/laravel-users-online/v/stable)](https://packagist.org/packages/acelords/laravel-users-online)
[![Total Downloads](https://poser.pugx.org/acelords/laravel-users-online/downloads)](https://packagist.org/packages/acelords/laravel-users-online)
[![License](https://poser.pugx.org/acelords/laravel-users-online/license)](https://packagist.org/packages/acelords/laravel-users-online)

## Laravel compatibility

 Laravel      | Package
:-------------|:----------
  9.x.x        | 3.0.x
  8.x.x        | 3.0.x
  7.x.x        | 3.0.x
  6.x.x        | 3.0.x
  5.8.x        | 3.0.x
  5.7.x        | 2.3.x
  5.6.x        | 2.3.x
  5.5.x        | 2.3.x
  5.4.x        | 2.2.x
  5.3.x        | 2.0.x
  5.2.x        | 1.0.x

## Installation

Add the new required package in your composer.json

```
"acelords/laravel-users-online": "^3.0"
```
Run `composer update` or `php composer.phar update`.

Or install directly via composer

```
composer require acelords/laravel-users-online
```

After composer command, add the trait in your model User in `app/User.php`:

```php

class User extends Authenticatable
{
    use \HighIdeas\UsersOnline\Traits\UsersOnlineTrait;
...

```
Finally run `php artisan vendor:publish` for add the namespaces

## Usage

For show the users online just use the method `allOnline()`:

```php
$user = new User;
$user->allOnline();
```
Or if you want to check if a specific user is online use the method `isOnline()`:

```php
$user = User::find($id);
$user->isOnline();
```

You can sort all users online with the methods `mostRecentOnline()` and `leastRecentOnline()`:

```php
$user = new User;
$user->mostRecentOnline();
$user->leastRecentOnline();
```
Using with [Real-time Facades](https://laravel.com/docs/6.x/facades#real-time-facades):
```php
use Facades\App\User as UserFacade;

UserFacade::mostRecentOnline();
UserFacade::leastRecentOnline();
```

**Installation and usage on last versions of framework:**

[Laravel 5.5 - 5.7](instructions/5.5-7.md)

[Laravel 5.4](instructions/5.4.md)

[Laravel 5.3](instructions/5.3.md)

[Laravel 5.2](instructions/5.2.md)
