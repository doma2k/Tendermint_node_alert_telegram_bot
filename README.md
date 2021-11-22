# Prometheus with alert rules and telegram bot
As example i took assetMantle but will work with any ather tendermint based chain.
Will play more with alert rules and probably will slightly modify bot UI.
Config files coud be addjusted to extend list of nodes, add more or adjust alert rules.
Any one who want to contrbute to it, most welcome. 
To run this stack will need docker and docker-composer witch can be installed with scripts:

curl -fsSL https://get.docker.com -o get-docker.sh && sudo sh  get-docker.sh && rm get-docker.sh

sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose && sudo chmod +x /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

# Creat bot, guide:
https://core.telegram.org/bots

# Clone repo, modify config files 
Just follow "# comments" there is mostly need to input ips, bot token etc.

# Start 
docker-compose up -d 

<Now you can look at monitring little bit less>

Bot downloaded from:
https://github.com/metalmatze/alertmanager-bot
















