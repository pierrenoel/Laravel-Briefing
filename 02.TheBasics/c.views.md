# Views

Now you understand how routes work, it is the right moment to learn views.

Remember that views are the **'V'** of the **'MVC'** design pattern, that means those are the files that all the users see from your app. The views are called only with **'HTTP'** request **'get'**

## Example

```console
|-resources
    |-views
        |-article
          index.blade.php
          create.blade.php
          edit.blade.php  
```

```php
// Display all the articles
Route::get('/articles',function(){
    return view('article.index');
});

// Show the form in order to create an article
Route::get('/article/create',function(){
    return view('article.create');
});

// Show the form of an article
Route::get('/article/edit/{id}',function($id){
    return view('article.edit');
});

```

- [Before](b.routes)
- [Next]()