# Controllers

Now it is time to create your first controller but before doing that, you need to know exactly what a controller is and how it works. 

The controller is like the bandleader, that means it is the controller who interacts with **Model** to create data for the **View**.

## How to setup them?

`php artisan make:controller ArticleController --resource`

If you want to see some Artisan commands, you can type `php artisan`.

**'ArticleController'** is the name of the controller, remind that (by convention):
- it begins with a capital letter
- you have to add the keyword **Controller**

**'--resource'** is a parameter to initiate default methods when the controller is created.

## Where to find them?

```console
|-app
    |-Htpp
        |-Controllers
          ArticleController.php
```

## Short example

```php
<?php

namespace App\Http\Controllers;

use Illuminate\Http\Request;

class ArticleController extends Controller
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
    ...

```

## About routes
Now you have learned how to setup a new controller and you know what a controller is, it is the right moment to combine both. 

### How routes reference to a controller?

```php
use App\Http\Controllers\ArticleController;

Route::get('/articles',['AuthController::class','index']);

```

- **'/articles** is the name of the route.
- **['AuthController:class,'index',]** is this route who references to that controller directly assign to the index method.

#### Exercice (3)

1. Take your previous exercice
2. Create the RestaurantController file
3. Adapt your routes
4. Return views from the RestaurantController

- [Before](/02.TheBasics/c.views.md)
- [Next](e.migrations.md)