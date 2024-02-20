NOTE! Before Starting over... PLEASE DELETE SRC directory and the .gitignore file first

# docker-laravel

docker-laravel setup
Step 1: Create .env file

Step 2: Run the following command.
docker run --rm -v $(pwd):/app composer create-project --prefer-dist laravel/laravel /app/src
docker-compose up --build docker_laravel_app

Step 3: create .env file inside "scr" directory

Step 4: Install dependencies
docker-compose run --rm composer install

Step 5:
Setup Login and Register Scafollding
docker-compose run --rm composer require laravel/breeze --dev
docker-compose run artisan breeze:install
Note: Questions and Options
┌ Which Breeze stack would you like to install? ───────────────┐
│ Blade with Alpine │
└──────────────────────────────────────────────────────────────┘

┌ Would you like dark mode support? ───────────────────────────┐
│ No │ (depends on you if you want dark mode support - i prefer not)
└──────────────────────────────────────────────────────────────┘

┌ Which testing framework do you prefer? ──────────────────────┐
│ PHPUnit │
└──────────────────────────────────────────────────────────────┘

docker-compose run --rm npm install

Step 6: Setup Database
set ther following on .env file inside src
DB_HOST=mysql
docker-compose run --rm artisan migrate:fresh
