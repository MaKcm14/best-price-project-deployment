# Best-price-project
This project lets to get and analyze the products' prices from different markets.

<hr>

## Main project description
The main parts of this project are:
- [price-service](https://github.com/MaKcm14/price-service)

  This service provides API for getting, filtering and monitoring prices in the most popular markets.

- [price-service-tg-bot](https://github.com/MaKcm14/price-service-tg-bot)

  This is the telegram-UI for the best-price-project. It integrates with the *price-service* and provides UI.

## How to install
1. Install the [Docker](https://docs.docker.com/engine/install/)
2. `mkdir best-price-project`
3. `cd best-price-project`
4. `git clone https://github.com/MaKcm14/best-price-project-deployment.git`
5. `cd best-price-project-deployment`
6. `git clone https://github.com/MaKcm14/price-service`
7. `git clone https://github.com/MaKcm14/price-service-tg-bot`
8. Obtain the **bot token** from [**@BotFather**](https://t.me/BotFather).
9. Configure the .env file at the price-service and price-service-tg-bot according to their rules

   (see the README.md of [price-service](https://github.com/MaKcm14/price-service) and [price-service-tg-bot](https://github.com/MaKcm14/price-service-tg-bot))

## How to start
At the `best-price-project-deployment` dir:
1. `docker compose -f docker-compose-services.yml build`
2. `docker compose -f docker-compose-services.yml up -d`
3. Wait 2-3 minutes until the services are fully launched and ready for the next step.
4. Just for *the first start*:
   
   - `docker compose -f ./price-service-tg-bot/docker-compose-migrations.yml build`
   
   - `docker compose -f ./price-service-tg-bot/docker-compose-migrations.yml up -d`
  
6. `docker compose -f docker-compose.yml build`
7. `docker compose -f docker-compose.yml up -d`

## How to stop
At the `best-price-project-deployment` dir:
1. `docker-compose -f docker-compose.yml down`
2. Wait 2-3 minutes until the services are fully stopped and ready for the next step.
3. `docker-compose -f docker-compose-services.yml down`

## Customize settings:
The settings of the project are enough to use it locally without some problems.

But if you want to change some settings, for example the passwords, you need to check that the **compose files** and **.env files are up to date**.
