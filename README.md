# Telescope implementation in laravel

## Telescope installing step's :

<ul>
<li>Install the telescope package in the project,
    <pre>
        composer require laravel/telescope "2.1.7"
    </pre>
    <pre>
        php artisan telescope:install
    </pre>
    While run this command php artisan telescope:install in CMD,

    1. TelescopeServiceProvider.php file created in provider folder.
    2. With in public/assets/telescope folder design of telescope files will created like app.css,app.js and so on.
    3. In config folder Telescope.php file created.

</li>

<li>
    <pre>
        php artisan migrate
    </pre>
    While run this cmd, Telescope table will be created. 
</li>
<li>
    This CMD is no need for 5.8 and above laravel version
    <pre>
        php artisan telescope:publish
    </pre>
</li>
<li>
    <pre>
        php artisan serve
    </pre>
    Telescope will run in this url : http://127.0.0.1:8000/telescope
</li>
</ul>

## Config/telescope.php

    <li> path - you can change the URL. Like debugger or some thing else. </li>
    <li> enabled - You can be active or deactive the telescope</li>
    <li> middleware - you can be authorize user only view the telescope </li>
    <li> And some of the option that if you need try that also </li>

## Providers/TelescopeServiceProvider.php

    <li> Gate Function - In that you can be mention the Email,  that user only has a access to view that telescope. </li>
    <pre>
        protected function gate()
    {
        Gate::define('viewTelescope', function ($user) {
            return in_array($user->email, [
                // like that we have can give the access to the user
                "prasanth@ppstechwrdz.com"
            ]);
        });
    }
    </pre>
