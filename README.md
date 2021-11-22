# Alert-Rules

Alert rules for prometheus and tendermint

For the sake of experiment all the services will appleyid on localhost.

This is short guide how to set up alert rules for prometheus alertmanager and hook-up it with telegram bot.

I used this bot:
https://github.com/metalmatze/alertmanager-bot

We will need Prometheus,AlertMAnager and NodeExporter that can be downloaded:

wget https://github.com/prometheus/prometheus/releases/download/v2.31.1/prometheus-2.31.1.linux-amd64.tar.gz

wget https://github.com/prometheus/alertmanager/releases/download/v0.23.0/alertmanager-0.23.0.linux-amd64.tar.gz

wget https://github.com/prometheus/node_exporter/releases/download/v1.3.0/node_exporter-1.3.0.linux-amd64.tar.gz

Inside config.toml we need to change parameter "prometheus = true" port can be customised for security purposes.
~/.assetNode/config/config.toml 


Instaletion steps logs:

1. 
# To use bot i will install docker and docker-compose first:

curl -fsSL https://get.docker.com -o get-docker.sh && sudo sh  get-docker.sh && rm get-docker.sh

sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

2.
# Creating docker-compose for bot

sudo mkdir alert_bot && cd alert_bot && nano docker-compose.yml

# Past this text to the file:

networks:
  alertmanager-bot: {}
services:
  alertmanager-bot:
    command:
    - --alertmanager.url=http://localhost:9093
    - --log.level=info
    - --store=bolt
    - --bolt.path=/data/bot.db
    environment:
      TELEGRAM_ADMIN: "1234" # number of your user id 
      TELEGRAM_TOKEN: XXXXXXX # obtain token with bot_father in telegram
    image: metalmatze/alertmanager-bot:0.4.3
    networks:
    - alertmanager-bot
    ports:
    - 8080:8080
    restart: always
    volumes:
    - ./data:/data
version: "3"

3.
# Run your node by lunching docker-compose:

docker-compose up -d

# Now your bot will reply in chat






