# # To be continued ... (3)

## Introduction

We don't want to create an article each time with **Tinker**. We prefer using a form. So, remember that you can create a route in order to show the form.

`localhost/article/create` => `Route::get('article/create',['CreateController::class','create']');`

This route returns only a form, in which you are going to display all the inputs.

## The form

```html
<form action="#" method="#">
    <label for="title">Title of the article</label>
    <input type="text" name="title" id="title"">
</form>
```
The basic of you form is created, Laravel needs some more informations in order to treat your data in a better way.

- **method="POST"** 
- **action="/article/create"**

Don't forget to add this route:

`Route::post('/article/create',['ArticleController::class','store']);`

There is a thing that we need to add in our form. **The csrf token**

>>Laravel makes it easy to protect your application from cross-site request forgery (CSRF) attacks. Cross-site request forgeries are a type of malicious exploit whereby unauthorized commands are performed on behalf of an authenticated user.

>> Laravel automatically generates a CSRF "token" for each active user session managed by the application. This token is used to verify that the authenticated user is the one actually making the requests to the application.

```html
<form method="POST" action="/article/create">
    @csrf
    <label for="title">Title of the article</label>
    <input type="text" name="title" id="title">
    <input type="submit" value="Submit"></input> 
</form>
```

## Get data from the view
We see that we send the data to the route **'/article/create'** using the HTTP verb **POST** with references to the controller and the method **store()** **'ArticleController'**.

So now if we want to display all we get from the inputs, we can check by using the object **Request**

```php
public function store(Request $request){
    dd($resquest->title()); // dd($request['title'])
}
```

### Saving data into the database
Now, in order to save data into the article table, we have to call the model **Article**.

```php
public function store(Request,$request){
    Article::create([
        'title' => $request['title'],
        ...
    ]);
}
```

### Validate data before sending them into the database

Now, one of the most important step to do is to check if the user did his job, fill all the fields. But, it is not always the case.

**NEVER TRUST USER INPUTS**

```php
public function store(Request $request){
    $this->validate(request(),[
        'title' => 'required|min:5|max:10'
    ])
}
```

If you try to save data to the table, it is going to show an error:

`Add [title] to fillable property to allow mass assignment on [App\Article].`

To fix this problem, the error says you must set the property `title` to fillable. So, you can do this in your model **Article**.

```php
protected $fillable = ['title'];
```
#### Exercice (8)
1. Take your project **RestaurantLaravel**
2. Show a form, get inputs and save them to the database

- [Before](/03.Exercice/b.step2.md)
- [Next](03.Exercice/../d.step4.md)