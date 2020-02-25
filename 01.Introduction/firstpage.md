# First page
Now you have your env made, we are going to create a first page.

## Launch your new app

```terminal
composer create-project --prefer-dist laravel/laravel firstApp
cd firstApp
php artisan serve
```

## Routes/web.php
1. Create a new route in *web.php*

```php
Route::get('/hello',function({
    return 'hello';
}))
```

## Set up a new view
1. In your resources directory, create a new blade file **hello.blade.php**
2. Put some classical html

## Now the you can show the page when the new url is called
```php
Route::get('/hello',function({
    return view('hello');
}))
```

## Passing your name into the view
```php
Route::get('/hello/{name}',function({
    return view('hello);
}))
```

```html
...
<body>
{{ name }}
</body>
...
```

