# Laravel and its files & folders

```console
|-app
    |-Htpp
        |-Controllers
          PostController.php
  Post.php
|-bootstrap
|-config
    app.php
    auth.php
    broadcasting.php
    ...
    database.php
|-database
    |-migrations
      2014_10_12_000000_create_users_table
|-public
    |-css
    |-img
    |-js
|-resources
    |-assets
        |-js
        |-sass
    |-views
        |-posts
          index.blade.php    
|-routes
  web.php

```

* Models are in the folder **app**
* Controllers are in the folder **app/Http/Controllers**
* Views are in the folder **resources/views**
* Migrations are in the folder **database/migrations**

Remain that to add some style and some javascript, you need to place them in the **resources** folder!

- [Next](b.routes.md)