# Views

Now you understand how routes work, it is the right moment to learn views.

Remember that views are the **'V'** of the **'MVC'** design pattern, that means those are the files that all the users see from your app. The views are called only with **'HTTP'** request **'get'**

## Basic example

```console
|-resources
    |-views
        |-article
          index.blade.php
          show.blade.php
          create.blade.php  
```

```php
// Show each article by its id
Route::get('/article/show/{post:id}',function($id){
    return view('article.edit',['id' => $id]);
});

```

## Passing arguments to views

1. First of all, take the route "get" we have created in the previous page, now we adapt it.

```php
Route::get('/hello',function(){
    return view('hello');
})
```
2. Now I want my route displays my name in my new view.

```php
Route::get('/hello/{name}',function($name){
    return view('hello',compact('name'));
});
```
3. If we add **'/hello/John'** after our url, we are going to see ... nothing.

4. Well, if you want to fix this, you can add **{{$name}}** in your view. I will explain you better in a few chapters.

`FYI: files in the view end with a blade.php`

If we look, we see that we are passing the variable **'name'** with the compact function. 

### Parameters of compact function
>> compact() takes a variable number of parameters. Each parameter can be either a string containing the name of the variable, or an array of variable names. The array can contain other arrays of variable names inside it; compact() handles it recursively.

### Return values
>> Returns the output array with all the variables added to it.

#### Exercice (2)

1. Take your project **'RestaurantsLaravel'**
2. Create a folder **'restaurants'** in your views
3. In this folder, add three files 
   - index.blade.php
   - show.blade.php
   - create.blade.php
4. Adapt the web.php in order to show all the three routes
   - /restaurants
   - /restaurant/show/1
   - /restaurant/create
5. Each route must return a view
6. Passing and show the id of the **show** route

- [Before](/02.TheBasics/b.routes.md)
- [Next](d.controllers.md)
