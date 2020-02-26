# Controllers

```console
|-app
    |-Htpp
        |-Controllers
          PostController.php
```

## Initiate a new controller
```php artisan make:controller PostsController --resource```

If we add the parameter **--resource** at the end of the command, it because we need that Laravel set the basic methods of an application.

```php
public function index(){
    //
};

public function create(){
    //
};

public function store(Request $request){
    //
};

public function edit(Request $request){
    //
};

public function  
```


```php
Route::get('/articles',function(){
    return view('article.index')
})
```

```php 
Route::get('/articles','ArticleController@index');
```

