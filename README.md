# Docker Rails

This project shows how Docker can help you to develop Rails app.

Docker will install all needed system libraries for you.

## Installation

1. Clone this repo
    ```bash
    git clone git@github.com:yesnik/docker-rails.git
    cd docker-rails
    ```
2. Build image for `rails` service and open bash console in the container:
    ```bash
    docker compose run rails bash
    ```
3. Let's check what we have inside container:
    ```bash
    ruby -v
    # ruby 3.3.0 (2023-12-25 revision 5124f9ac75) [x86_64-linux]
    
    bundle -v
    # Bundler version 2.5.3
    
    gem -v
    # 3.5.3
    
    rails -v
    # Rails 7.1.3
    ```
4. Create Rails app that will use Postgres:
    ```bash
    rails new . -d=postgresql --skip-git
    ```
5. Edit Rails DB configuration at `/rails_app/config/database.yml`:
    ```yml
    development:
      <<: *default
      database: rails_app_development
      username: postgres
      password: password
      host: db
    ```
7. Run Docker Compose: `docker compose up`
8. Open in browser: http://127.0.0.1:3000/
