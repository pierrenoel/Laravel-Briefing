# To be continued ... (1)

**STOP: Before reading this section, you need to read the second section which is "step by step". If it is the case, welcome aboard!**

Before we continue on this pratice, we have learned three Artisan commands:
- `php artisan make:controller ArticleController --resource`
- `php artisan make:model Article`
- `php artisan make:migration create_articles_table`

Well, I have a surprise for you! We can initiate the three one in only one command:

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
>>> $article = new App\Models\Article;
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

#### Exercice (6)
1. Add some data to your table **restaurants** with tinker
   
- [Next](03.Exercice/../b.step2.md)
