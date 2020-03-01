# Authentification in Laravel

One of the greatest thing in Laravel is the authentification. Laravel provides an auth package.

## 1. Use Auth from Laravel

## a. Install the dependances
`composer required ui bootstrap --auth`

## b. Install bootstrap
```terminal
npm install
npm run dev
```

## 2. Do your own auth
One of the greatest thing is to create our own auth system without install any packages... 

Nothing new for this section, you already know a lot of things...

### A.Middlewares

Sometimes, you want to "protect" some of your routes, for instance, in order to create a dashboard, to do that, you are going to use a middleware. 

>> Middleware acts as a bridge between a request and a response.

```php
Route::group(['middleware' => 'auth'],function(){
    Route::get('/dashboard','dashboardController@index');
});
```


#### Exercice (10)
1. You create a dashboard for the **RestaurantLaravel** project
2. That means, you create the model, the controller and the views
3. In your loginController, add this function to attempt the login `attempt([])`
4. Protect your dashboard routes with the **auth** middleware
 