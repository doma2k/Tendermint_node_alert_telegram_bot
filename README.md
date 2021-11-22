# Alert-Rules
Alert rules for prometheus and tendermint 

This is short guide how to set up alert rules for prometheus alertmanager and hook-up it with telegram bot.

I used this bot:
https://github.com/metalmatze/alertmanager-bot

We will need Prometheus,AlertMAnager and NodeExporter that can be downloaded:

wget https://github.com/prometheus/prometheus/releases/download/v2.31.1/prometheus-2.31.1.linux-amd64.tar.gz
wget https://github.com/prometheus/alertmanager/releases/download/v0.23.0/alertmanager-0.23.0.linux-amd64.tar.gz
wget https://github.com/prometheus/node_exporter/releases/download/v1.3.0/node_exporter-1.3.0.linux-amd64.tar.gz

Inside config.toml we need to change parameter "prometheus = true" port can be customised for security purposes.
~/.assetNode/config/config.toml 

Prometheus setup:
