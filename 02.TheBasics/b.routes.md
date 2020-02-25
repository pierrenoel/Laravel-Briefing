# Routes

For this first step, you are going to create your very first route. But before doing that you need to understand what a route is and how it works.

Routes are the main entrance of a laravel application. That means that when you create a route, you call its controller and of course an specific action.

But before making your very first route, we have to see what a facade is:

>> Facades provide a "static" interface to classes that are available in the application's service container. Laravel ships with many facades which provide access to almost all of Laravel's features. Laravel facades serve as "static proxies" to underlying classes in the service container, providing the benefit of a terse, expressive syntax while maintaining more testability and flexibility than traditional static methods.

## In real case:
``` Route::get('')```

Here **'get'** is a **request method** In laravel, there are many **HTTP request methods**.

- get
- post
- put
- delete

## Defintion of HTTP

>> HTTP defines a set of request methods to indicate the desired action to be performed for a given resource. Although they can also be nouns, these request methods are sometimes referred to as HTTP verbs. Each of them implements a different semantic, but some common features are shared by a group of them: e.g. a request method can be safe, idempotent, or cacheable.

## Here are some examples on how routes work.

```php
// Display all the articles
Route::get('/articles',function(){
    ...
});
// Show the form in order to create an article
Route::get('/article/create',function(){
    ...
});
// Post/public the article
Route::post('/article/create',function(){
    ...
});
// Show the form of an article
Route::get('/article/edit/{id}',function($id){
    ...
});
// Update this specific article
Route::put('/article/edit/{id}',function($id){
    ...
})
// Delete a specific article
Route::delete('/article/{id}',function($id){
    ...
});

```

### Exercice (1)
```terminal
1. Create a new laravel app called learningLaravel
2. Create a route 'article' whom return an hello world
```


- [Before](a.hierachy.md)
- [Next](c.views.md)