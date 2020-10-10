# laravel-nginx-starter
Wanted to limit the number of CLIs I had to install on my computer so I went with the docker approach.
Used nginx web server instead of apache...which am starting to think would've been easier/faster... 

***
Disclaimer: this is just something I'm using for personal stuff, it's not necessarily gonna be the best approach for everyone.
***

## Usage
- Copy the contents of any laravel app into the ***laravelapp*** directory.
- From the root directory (wherever the docker-compose.yml file is) run `docker-compose exec laravelapp composer install`.
- Go open your browser and navigate to `localhost:8000` to see your app.

***

### Database
This repo spins up a mysql container as well, if you wish to use it, you may place sql scripts in the ***mysql*** directory to have them executed when the container starts for the first time.
See the reference for the official [mysql docker image](https://hub.docker.com/_/mysql/)

### No Laravel CLI?
- If you need to create a new laravel app without having laravel installed on the host machine:
  - You could just download laravel from the [Official Repo](https://github.com/laravel/laravel)
  - OR - you could modify the Dockerfile.laravelapp file and uncomment the command to install the laravel CLI, then run laravel commands like so `docker-compose exec laravelapp <some command>`.
    - ex: Creating a new app -> `docker-compose exec laravelapp laravel new SuchNewLaravelApp`