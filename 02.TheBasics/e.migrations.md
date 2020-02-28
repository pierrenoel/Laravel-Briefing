# Migrations

Don't feel asleep, we are now see how to link a database to your project.

In the root of your project, you have an .env file where you add some details about your database.

## Let us have a look

1. Create your database
```terminal
mysql -u username -p
create database learningLaravel;
```
2. Update the .env file

```terminal
...
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=root
DB_PASSWORD=
...
```

3. Reinitialize your app `php artisan config:clear`
   

## Create your first migration

Before doing that amazing Artisan command, you have to know what is a migration.

> Migrations are a way to alter and update the database in a structured way instead of using for example "phpmyadmin" directly.

### Artisan command
`php artisan make:migration create_articles_table`

### Where to find them?

```console
|-database
    |-migrations
      2014_10_12_000000_create_users_table
      2014_10_12_000001_create_articles_table
```

### Explanation
In a migration file, you have two methods **up()** and **down()**
- **up()** is for runing the migration
- **down()** is for reversing the migration

### let us focus on the **up()** method:
If we want to add some fields in our table, we need to call the object $table and call a specific method. Look at the example below;

```php
  public function up()
    {
        Schema::create('articles', function (Blueprint $table) {
            $table->bigIncrements('id');
            $table->string('title');
            $table->text('content');
            $table->timestamps();
        });
    }
```

### Run an Artisan command to add your new table in your database
`php artisan migrate`

#### Exercice (4)

1. Take your previous exercice **RestaurantsLaravel**
2. Create a migration called **Restaurant**
3. Add three fields 
   1. name => string type
   2. address => string type
   3. zipCode => int type
   4. town => string type
   5. country => sting type
   6. description => text type
   7. review => int type
4. Run your migration

- [Before](/02.TheBasics/d.controllers.md)
- [Next](f.models.md)