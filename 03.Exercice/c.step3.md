# Create / update an article
We don't want to create an article each time with **Tinker**. We prefer using a form. So, remember that you can create a route in order to show the form.

`localhost/article/create` => `Route::get('article/create','ArticleController@create');`

This route returns only a form, in which you are going to display all inputs.

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

`Route::post('/article/create','articleController@store');`

There is a thing that we need to add in our form. **The csrf token**

>>Laravel makes it easy to protect your application from cross-site request forgery (CSRF) attacks. Cross-site request forgeries are a type of malicious exploit whereby unauthorized commands are performed on behalf of an authenticated user.

>> Laravel automatically generates a CSRF "token" for each active user session managed by the application. This token is used to verify that the authenticated user is the one actually making the requests to the application.

```html
<form method="POST" action="/article/create">
    {{ scrf_field() }}
    <label for="title">Title of the article</label>
    <input type="text" name="title" id="title"">
</form>
```

- [Next](03.Exercice/../c.step3.md)