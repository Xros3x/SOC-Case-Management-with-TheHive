# deployment/README.md

# Deployment

TheHive was deployed via Docker Compose as a four-service stack (TheHive, Cassandra, 
Elasticsearch, MinIO) on a dedicated Ubuntu VM.

## Prerequisites
- Ubuntu 24.04 VM with 8GB RAM
- Docker + Docker Compose v2
- vm.max_map_count set to 262144

## Deploy

sudo sysctl -w vm.max_map_count=262144
echo "vm.max_map_count=262144" | sudo tee -a /etc/sysctl.conf
docker compose up -d

See docker-compose.yml for the full stack definition.

> Note: The application secret in the compose file has been replaced with a placeholder. 
> Generate your own for any real deployment.
