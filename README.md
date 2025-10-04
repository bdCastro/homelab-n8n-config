# homelab n8n

This directory contains the configuration files and setup instructions for deploying n8n, an open-source workflow automation tool, in a homelab environment using Docker and Docker Compose.

### Prerequisites

- Docker and Docker Compose installed on your server.

In macOS, you can install Docker Desktop though Homebrew:

```bash
brew install --cask docker
```

### Setup Instructions

1. **Clone the Repository**: If you haven't already, clone the repository containing this `n8n` directory.

   ```bash
   git clone <repository-url>
   cd <repository-directory>/n8n
   ```

2. **Configure Environment Variables**: Create a `.env` file in the `n8n` directory to store your environment variables. You can use the provided `example.env` as a template.

   ```bash
   cp example.env .env
   ```

Edit the `.env` file to set your desired configuration, such as database connection details, n8n credentials, and other settings.

3. **Install an SSL Certificate**: If you want to secure your n8n instance with HTTPS, you can use a reverse proxy like Nginx or Traefik along with Let's Encrypt to obtain an SSL certificate. This step is optional but recommended for production environments.

- Nginx: [Nginx Reverse Proxy with Let's Encrypt](https://docs.nginx.com/nginx/admin-guide/security-controls/terminating-ssl-http/)
- Traefik: [Traefik with Let's Encrypt](https://doc.traefik.io/traefik/https/acme/)

4. **Start n8n with Docker Compose**: Use Docker Compose to start the n8n service.

   ```bash
   docker-compose up -d
   ```

5. **Access n8n**: Once the service is up and running, you can access the n8n web interface by navigating to `http://<your-server-ip>:5678` in your web browser.

6. **Stop n8n**: To stop the n8n service, you can use the following command:

   ```bash
   docker-compose down
   ```