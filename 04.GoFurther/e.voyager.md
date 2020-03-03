# Voyager

![logo Voyager](../assets/logoVoyager.jpeg)

In this section, we are going to learn how to user **Voyager**, but before doing this, let us see what **Voyager** is.

## About Voyager

- An admin interface for your Laravel app
- An easy way to add/edit/delete data for your app
- A menu builder (build menus in Voyager for your app)
- A media manager for your files
- CRUD/BREAD generator (learn more about BREAD here)

Voyager is simply an admin for your Laravel app. Whatever you want. ([source](https://voyager-docs.devdojo.com/getting-started/what-is-voyager))

## How to install it?

``` terminal
require tcg/voyager
php artisan voyager:install
php artisan serve
```

**Tips:** Don't forget to add a database to your project!

Now you can launch your app : `http://127.0.0.1:8000/admin`

![Voyager](../assets/voyager.jpg)

## Configuration

You have to create a new admin user in order to connect to your new dashboard page.

`php artisan voyager:admin yourmail@mail.com --create`

## Making a blog

