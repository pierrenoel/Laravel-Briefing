# Display data in our views

First, make sure you have at least more than one article in your table. 
Now, we are going to adapt your code in order to display the titles, the contents and the author of each article.

## ArticleController

```php
 public function index()
    {
        $articles = Article::get();
        
        return view('articles.index',compact('articles'));
    }
```

How easy is this, isn't it? 

