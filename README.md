## Simple cloning

1. Simply clone the repo `git clone ... <app_name>`
2. Go to app's directory `cd <app_name>`
3. Remove attached git directory `rm -rf .git`
4. Re-initialize your own local repository `git init`
5. Rename `.env.example` to `.env`: `rm .env.example .env`
6. Run application
   - `docker-compose build`
   - `docker-compose run phoenix mix deps.get` to install dependencies
   - `docker-compose run phoenix mix ecto.create` to create and initialize the database
   - `docker-compose up`
   - voila

## Your own installation

1. Create a directory where you want your app to reside at
2. Run:  
   `docker run -it --rm --volume <absolute_path_to_project>:/mnt/myapp elixir bash`
3. In dockerized elixir shell then run:
   - `cd /mnt/myapp`
   - `mix archive.install hex phx_new`
   - Type `Y` to confirm at every step
   - `exit` to close Elixir shell
   - `docker-compose build`
   - `docker-compose run phoenix mix deps.get` to install dependencies  
      (only if you selected "n" during application creation step)
   - `docker-compose run phoenix mix ecto.create` to create and initialize the database
   - `docker-compose up`
   - voila

## Change project name

You can use [this script](https://gist.github.com/wbednarski/fcd9a68f600971f6fab6114be44bd403) to rename project name in all the files.
