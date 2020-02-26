# Exercice learningLaravel

Before we continue on this pratice, we have learned three Artisan commands:
- `php artisan make:controller ArticleController --resource`
- `php artisan make:model Article`
- `php artisan make:migration create_articles_table`

Well, I have a surprise for you! We can initiate the three one in one command:

`php artisan make:model Article -mcr`

- **'-mcr'** means *migration*,*controller*,*resource*
  
## Add some data into the table Articles

There are two ways for adding data to a table. The first one is using the tool **phpmyadmin** and the second one is to use **tinker**. We are going to use the second one.

### Use tinker

To active tinker : `php artisan tinker`

We are going to check if there are already data in the table **articles** : `App\Article::get()`;

it returns

```terminal
=> Illuminate\Database\Eloquent\Collection {#3016
     all: [],
   }

```

That means there is nothing in the table yet

### Add data into the articles table

```terminal
>>> $article = new App\Article;
=> App\Article {#3010}
>>> $article->title = "first title";
=> "first title"
>>> $article->content = "first content";
=> "first content"
>>> $article->author = 'Pierre';
=> "Pierre"
>>> $article->save()
=> true

```

### Check the table now

```terminal
>>> App\Article::get()
=> Illuminate\Database\Eloquent\Collection {#3019
     all: [
       App\Article {#3020
         id: 1,
         title: "first title",
         content: "first content",
         author: "Pierre",
         created_at: "2020-02-26 12:41:19",
         updated_at: "2020-02-26 12:41:19",
       },
     ],
   }

```

## Add some style to our views
