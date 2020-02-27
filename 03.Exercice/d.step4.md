# Updating
One of the most important step of developing an application is to giving the opportunity to update data from table.

## 1. Get the ID of the article

`Route::get('/articles/edit/{id}','ArticleController@edit');`

```php
    /**
     * Show the form for editing the specified resource.
     *
     * @param  \App\Article  $article
     * @return \Illuminate\Http\Response
     */
    public function edit(Article $article,$id)
    {
        $article = Article::findOrFail($id);

        return view('articles.edit',compact('articles'));
    }
```

## 2. Show data in the inputs

```html
<form method="POST" action="/articles/edit/{{ $article->id }}">
    {{ csrf_field()}}
    {{ method_field('PATCH') }}
    <input type="text" name="title" placeholder="Title" value="{{ $article->title }}">
    <input type="submit" value="Yeah"></input> 
</form>

```

## 3. Validation & updating in the database

