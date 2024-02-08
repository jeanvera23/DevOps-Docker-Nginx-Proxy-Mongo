# DevOps Docker Nginx-Proxy - MongoDB

This is a template uses docker to create multiple containers including:
1. nginxproxy/nginx-proxy
2. nginxproxy/acme-companion.

## Steps
1. Clone this repo in your VM
2. Create a new `.env` file to include your `MONGODB_USER` and `MONGODB_PASSWORD` use the `.env.example` as an example.
4. Create a shared network to connect nginx with your application:
    ```bash
    docker network create app-network
    ```

5. Run:
    ```bash
    docker compose -p $(hostname) up -d
    ```
## Recomendations
Remember to put your applicacions in the same network. In this case, the network name is called "app-network"