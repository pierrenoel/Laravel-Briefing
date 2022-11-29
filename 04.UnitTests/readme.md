# Unit Tests

Unit tests are a great way to ensure that your code is working as expected. They are also a great way to ensure that your code continues to work as expected as you make changes to it.

## The process of writing unit tests

1. We initialize the data,
2. We act on these data,
3. We check that the result is in accordance with our expectations.

```php 
$data = ["10,20,30"];
$result = array_sum($data);
$this->assertEquals(60, $result);
```

## Now, practice in Laraval (CRUD)

### Uncomment those two lines in phpunit.xml (root folder)

```xml

<env name="DB_CONNECTION" value="sqlite"/>
<env name="DB_DATABASE" value=":memory:"/>
```

### 1. Setup the sqlite database 

Don't forget to uncomment ```PDO_SQLite``` in php.ini

```bash 
touch database/database.sqlite
php artisan config:clear
```

### 2. Create the file

```terminal 
php artisan make:test PostTest
```

This file will be created in ```tests/Feature/PostTest.php```

### 3. Write the test

- In this file, you will found a function ```testExample()```. This is the function that will be executed when you run the test. (You can delete it)

- To run the test, you can use the command ```php artisan test```

Let us focus on the Crud (Create) for the moment, then it will be your turn to write the test for the other methods.

Put this fellowing code in the file ```tests/Feature/PostTest.php```

```php
// ...
use RefreshDatabase; // It is a trait that will be used to refresh the database after each test

    public function test_can_create_a_post() : void 
    {
      $request = $this->post('/post/create',[
            'title' => 'This is a title',
            'content' => 'This is the content of the post'
        ]);

        $request->assertValid(['title','content']);

        $request->assertOk();

        $request->assertRedirect(route('posts'));
    }
//...
```

Please, don't forget to add ```use RefreshDatabase;``` at the top of the file. This will allow you to use the function ```RefreshDatabase``` in your test. This function will allow you to reset the database after each test.

## Update the post 

- Call the route ```/post``` and pass an array with the title and the content of the post. (See below)

- In a variable post, select the first item of the model Post.
       
- In a variable response, call the route ```/post/update/{id}``` and pass an array with the updated title and the updated content of the post.

- Use ```$this->assertEquals(string $expected, string $actual)``` to check that the title and the content of the post are the same as the ones you passed in the array.

```php 
$this->assertEquals('This my first post updated',Post::first()->title);
```

- Test if the response is a redirection to the route ```/post```

## Delete the route

Now, it is your turn to write the test for the delete method. You have all the keys in your hands.

## Resources

- [Laravel documentation](https://laravel.com/docs/9.x/http-tests#response-assertions)