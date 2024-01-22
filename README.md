# cricoIsBack

## Instalation

Copy Folder + BD
Edit .env file
Edit .htacess (folder project name :line 7 e 9)
Delete /public/storage(shortcut)
Go backoffice config:
 	run code "storage:link"
	Reset database

#### change api token

  config\app.php

#### Status code
    <div class="custom-control custom-switch">
        <input type="checkbox" name="status" class="custom-control-input" id="statusSwitch{{$language->LANGUAGE_ID}}"
        @if ($language->STATUS === 1) checked @endif>
        <label onclick="window.location = '{{route('updateStatus', ['id'=>$language->LANGUAGE_ID,'table'=> 'a_languages','column'=>'LANGUAGE_ID', 'back'=>'languages', 'prevStatus'=>$language->STATUS])}}'" class="custom-control-label" for="statusSwitch{{$language->LANGUAGE_ID}}"></label>
    </div>

### Must Read

#### - Cors problems
    This is always hard to catch
    Tips:
     - MOST COMMON: (to see if that is the case, open the console and see
     if there is the app_url printed (This print is in the layout/app line 374 if you want to remove),
     if there is a empty string, you must do the following:  
       - In the server, go to bootsrap/cache and delete config.php
     - Try using $.ajax() with $.ajaxSetup() as shown in public/js/files.js
     - Sometimes the error is in the server:
       - The middleware 'cors' is handling the cors requests. If there is any errors in the server.
         It will cause the cors middleware to fail.
       - You can try to download the project and disable the middleware (App/Http/Kernel.php, comment the line with the '\Barryvdh\Cors\HandleCors::class') and try to search for the error.
#### Instalation on server
    - Use the proper .env file.
    - Have the database set properly
    - Do login in the backoffice

#### How API Works
    - The api is done with API Resources (read https://laravel.com/docs/5.7/eloquent-resources)
    - Basicaly a resource is an json representation of a model (Example User model that is linked to users table)
    - API file - App\Htpp\Controller\API\api.php


## backPath are present in views and controllers but not implemented, it is suposed to be a link that on click back to that url

## Artisan

Usage:
  command [options] [arguments]

Options:
  -h, --help            Display this help message
  -q, --quiet           Do not output any message
  -V, --version         Display this application version
      --ansi            Force ANSI output
      --no-ansi         Disable ANSI output
  -n, --no-interaction  Do not ask any interactive question
      --env[=ENV]       The environment the command should run under
  -v|vv|vvv, --verbose  Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

Available commands:
  clear-compiled       Remove the compiled class file
  down                 Put the application into maintenance mode
  dump-server          Start the dump server to collect dump information.
  env                  Display the current framework environment
  help                 Displays help for a command
  inspire              Display an inspiring quote
  list                 Lists commands
  migrate              Run the database migrations
  optimize             Cache the framework bootstrap files
  preset               Swap the front-end scaffolding for the application
  serve                Serve the application on the PHP development server
  tinker               Interact with your application
  up                   Bring the application out of maintenance mode
 app
  app:name             Set the application namespace
 auth
  auth:clear-resets    Flush expired password reset tokens
 cache
  cache:clear          Flush the application cache
  cache:forget         Remove an item from the cache
  cache:table          Create a migration for the cache database table
 config
  config:cache         Create a cache file for faster configuration loading
  config:clear         Remove the configuration cache file
 db
  db:seed              Seed the database with records
 event
  event:cache          Discover and cache the application's events and listeners
  event:clear          Clear all cached events and listeners
  event:generate       Generate the missing events and listeners based on registration
  event:list           List the application's events and listeners
 key
  key:generate         Set the application key
 make
  make:auth            Scaffold basic login and registration views and routes
  make:channel         Create a new channel class
  make:command         Create a new Artisan command
  make:controller      Create a new controller class
  make:event           Create a new event class
  make:exception       Create a new custom exception class
  make:factory         Create a new model factory
  make:job             Create a new job class
  make:listener        Create a new event listener class
  make:mail            Create a new email class
  make:middleware      Create a new middleware class
  make:migration       Create a new migration file
  make:model           Create a new Eloquent model class
  make:notification    Create a new notification class
  make:observer        Create a new observer class
  make:policy          Create a new policy class
  make:provider        Create a new service provider class
  make:request         Create a new form request class
  make:resource        Create a new resource
  make:rule            Create a new validation rule
  make:seeder          Create a new seeder class
  make:test            Create a new test class
 migrate
  migrate:fresh        Drop all tables and re-run all migrations
  migrate:install      Create the migration repository
  migrate:refresh      Reset and re-run all migrations
  migrate:reset        Rollback all database migrations
  migrate:rollback     Rollback the last database migration
  migrate:status       Show the status of each migration
 notifications
  notifications:table  Create a migration for the notifications table
 optimize
  optimize:clear       Remove the cached bootstrap files
 package
  package:discover     Rebuild the cached package manifest
 queue
  queue:failed         List all of the failed queue jobs
  queue:failed-table   Create a migration for the failed queue jobs database table
  queue:flush          Flush all of the failed queue jobs
  queue:forget         Delete a failed queue job
  queue:listen         Listen to a given queue
  queue:restart        Restart queue worker daemons after their current job
  queue:retry          Retry a failed queue job
  queue:table          Create a migration for the queue jobs database table
  queue:work           Start processing jobs on the queue as a daemon
 route
  route:cache          Create a route cache file for faster route registration
  route:clear          Remove the route cache file
  route:list           List all registered routes
 schedule
  schedule:run         Run the scheduled commands
 session
  session:table        Create a migration for the session database table
 storage
  storage:link         Create a symbolic link from "public/storage" to "storage/app/public"
 vendor
  vendor:publish       Publish any publishable assets from vendor packages
 view
  view:cache           Compile all of the application's Blade templates
  view:clear           Clear all compiled view files
