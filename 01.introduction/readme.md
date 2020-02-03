# Introduction

Laravel is a free PHP framework created by Taylor Otwell. Like many frameworks, Laravel provides a way of organizing and designing an application's souce code. If we take a look at its own organisation, we see that Laravel uses the "Model View Controller" (MVC). 

## Explanation

Let's see the MVC Design Pattern:

![MCV](../assets/mvc.png)

- Model, which defines the data structure and communicate with the database
- View, which handles the interface between the application and the users
- Controller, which manages data flow and communicate between the Model and the View

All these features make building an app in Laravel much faster than building from scratch. This makes Laravel a popular tool for rapid PHP development.

## Composer

Now you know how a laravel application is based on, it is time to start a new project. The first thing you need is Composer

> Composer is an application-level package manager for the PHP programming language that provides a standard format for managing dependencies of PHP software and required libraries. 

1. Update & upgrade

```terminal
sudo apt update
sudo apt upgrade
 ```

 2. Install Composer

 ```terminal
sudo apt install composer
```

3. Check if it is installed
   
```terminal
composer -v
```

## Laravel

1. Choose your directory
   
```terminal
cd ~ 
cd Desktop
```

2. Create a new laravel project using Composer

```terminal
composer create-project --prefer-dist laravel/laravel my-app
```

