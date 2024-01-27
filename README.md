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

5. Create Rails app that will be using Postgres:
```bash
rails new . -d=postgresql --skip-git
```
