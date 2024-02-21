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
    docker compose up -d --build
    ```
6. Enter your mongodb container, and create the database for your application, replace MONGODB_USER and MONGODB_PASSWORD with your own credentials.

    ``` bash
    sudo docker exec -it mongodb mongosh --username [MONGODB_USER] --passwo
    rd [MONGODB_PASSWORD]
    ```


## Recomendations
Remember to put your applicacions in the same network. In this case, the network name is called "app-network"

When connecting an app to mongo use the admin auth connection. The db_name should be replaced by your own database name
``` bash
mongodb://root:password@mongodb:27017/[db_name]?authSource=admin
```
