# Rails App with Docker

## Building Rails from Scratch on Windows

### Prerequisites
- Docker Desktop installed and running
- Git (optional)

### Initial Setup Steps

1. **Create project directory**
   ```bash
   mkdir rails-app
   cd rails-app
   ```

2. **Create Gemfile**
   ```ruby
   source "https://rubygems.org"
   gem "rails", "~> 7.2.2"
   ```

3. **Create empty Gemfile.lock**
   ```bash
   touch Gemfile.lock
   ```

4. **Create Dockerfile** (see Dockerfile in repo)

5. **Create docker-compose.yml** (see docker-compose.yml in repo)

6. **Generate Rails app**
   ```bash
   docker-compose run web rails new . --force --database=postgresql
   ```

7. **Build and start services**
   ```bash
   docker-compose build
   docker-compose up
   ```

### Development Commands

- **Start services**: `docker-compose up`
- **Run Rails commands**: `docker exec -it rails-web ./bin/rails [command]`
- **Run tests**: `docker exec -it rails-test bundle exec rspec`
- **Access Rails console**: `docker exec -it rails-web ./bin/rails console`
- **Access database**: `docker exec -it rails-db psql -U postgres -d rails_app`

### Services

- **web**: Rails development server (localhost:3000)
- **test**: Rails test environment
- **db**: PostgreSQL database

The app automatically sets up databases and runs migrations on startup.
