# Models

Now we have to connect thoses migrations to our application. It means that we have created migrations but the controller doesn't know how to fetch data from the tables.

**So we need to create model for each migration!**

`php artisan make:model Article`


```php 
<?php

namespace App;

use Illuminate\Database\Eloquent\Model;

class Article extends Model
{
    protected $table = 'articles';
}

```

#### Exercice (5)

1. Take your previous exercice **learningLaravel**
2. Create a model Article
3. Add the variable $table

- [Before](/02.TheBasics/e.migrations.md)
- [Next]()