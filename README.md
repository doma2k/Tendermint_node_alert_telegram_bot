# Prometheus with alert rules and telegram bot
As example i took assetMantle but will work with any ather tendermint based chain.
Will play more with alert rules and probably will slightly modify bot UI.
Config files coud be addjusted to extend list of nodes, add more or adjust alert rules.
Any one who want to contrbute to it, most welcome. 
To run this stack will need docker and docker-compose:

docker: https://docs.docker.com/engine/install/ubuntu/

docker-compose: https://docs.docker.com/compose/install/

# Creat telegram bot, guide:
https://core.telegram.org/bots

# Clone repo, modify config files 
Just follow "# comments" there is mostly need to input ips, bot token etc.

# Start 
docker-compose up -d 

<Now you can look at monitring little bit less>

  
Credits:  
Bot downloaded from:
https://github.com/metalmatze/alertmanager-bot
















