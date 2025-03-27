# Traefik Reverse Proxy with Nginx and Whoami

## 📁 Project Structure
```
/traefik-taller
│── docker-compose.yml
│── nginx/
│   └── nginx.conf
└── traefik/
    ├── acme.json
    └── traefik.yml
```

## 🚀 Running the Project
### 1. Clone the Repository
```bash
git clone https://github.com/Pidual/TRAEFIK-TALLER.git
cd TRAEFIK-TALLER
```

### 2. Update `/etc/hosts`
Make sure your `/etc/hosts` file contains the following entries:
```
127.0.0.1 nginx.localhost
127.0.0.1 whoami.localhost
```
If you encounter a **404 Not Found** error, ensure there are no conflicting entries and only these two domains are present.

### 3. Start the Containers
```bash
docker compose up -d
```
This will start:
- Traefik dashboard (accessible at http://localhost:8080/dashboard/)
- Nginx (at https://nginx.localhost)
- Whoami (at https://whoami.localhost)

### 4. Authentication
To access the Nginx service, use:
- **Username:** `123`
- **Password:** `123`

### 🛠️ Troubleshooting
- **404 Not Found**: Ensure `/etc/hosts` is correctly configured.
- Check Traefik logs with:
```bash
docker logs traefik
```

Feel free to contribute or report issues!

