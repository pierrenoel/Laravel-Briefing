# Controllers

Now it is time to create your first controller but before doing that, you need to know exactly what a controller is and how it works. 

The controller is like the conductor, that means its the controller who interacts with **Model** to create data for the **View**.

## How to setup them?

`php artisan make:controller PostsController --resource`

If you want to see some Artisan commands, you can type `php artisan`.

**'PostsController'** is the name of the controller, remind that:
- you have to (by convention) named your controllers in the plural
- you have to add the keyword **Controller**

**'--resource'** is a parameter to initiate default methods when the controller is created.

## Where to find them?

```console
|-app
    |-Htpp
        |-Controllers
          PostsController.php
```

## Short example

```php
<?php

namespace App\Http\Controllers;

use Illuminate\Http\Request;

class PostController extends Controller
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

`Route::get('/posts','PostsController@index');`

- **'/posts** is the name of the route.
- **'PostsController** is this route references to that controller, here it is the posts controller.
- **'@index'** means it searches after the method **index()** in the PostsController.

#### Exercice (3)

1. Take your previous exercice
2. Create the postsController file
3. Adapt your routes
4. Return views from the PostsController

- [Before](/02.TheBasics/c.views.md)
- [Next]()