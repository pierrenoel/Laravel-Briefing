# To be continued ... (4)

Like we saw in the previous lesson, we have to pass the ID of the article in the URL. Well now, you're going to create two more routes:

1. `Route::get('/articles/edit/{post:id}',['ArticleController::class','edit']);`
2. `Route::patch('/articles/edit/{post:id},['ArticleController::class','update']);`

## 1. Get the ID of the article

So in order to modify a specific article, we need its ID. So, the only way to do that is to pass the ID in the URL.

`Route::get('/articles/edit/{id}',['ArticleController::class','edit']);`

```php
    /**
     * Show the form for editing the specified resource.
     *
     * @param  \App\Article  $article
     * @return \Illuminate\Http\Response
     */
    public function edit(Article $article)
    {
        return view('articles.edit',['article' => $article]);
    }
```

## 2. Show data in the inputs

Something new things appear here:
1. In action meta, we add the link to the routes, of course with the id of the article.
2. And in each value, we set the result of the request called previously in the **edit()** function

```html
<form method="POST" action="/articles/edit/{{ $article->id }}">
    @csrf
    @method('PATCH')
    <input type="text" name="title" placeholder="Title" value="{{ $article->title }}">
    <input type="submit" value="Yeah"></input> 
</form>

```

## 3. Validation messages
When you add some validation rules in your controller, you can show these errors in your view.

```html
<form>
    ...
     @if($errors->has('title'))
        <small class="error">{{ $errors->first('title') }}</small>
    @endif
    ...
</form>

```
Before finishing this section, all the message errors can be changed in **/resources/lang/en**. 


#### Exercice (9)
1. Give the possiblity of updating a restaurant by using a form
2. Don't forget to display errors in your view!

- [Before](/03.Exercice/c.step3.md)