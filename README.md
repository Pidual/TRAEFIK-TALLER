Trabajado por CARLOS HERNANDO LOZANO PEREZ y DAVIDSANTIAGO CUBILLOS MÉNDEZ

# Proxy inverso Traefik con Nginx y Whoami
Como podemos ver esta es nuetra estructura de proyecto 
/traefik-taller
│── docker-compose.yml
│── nginx/
│   └── nginx.conf
└── traefik/
    ├── acme.json
    └── traefik.yml


## Correr el proycto 
### 1. VAmos a clondar el Nuestro repocitorio, con el siguiente comando 
```bash
git clone https://github.com/Pidual/TRAEFIK-TALLER.git
cd TRAEFIK-TALLER
```

### 2. Recuerda actualizar el `/etc/hosts`
Asegúrese de que su archivo `/etc/hosts` contenga las siguientes entradas:
```
127.0.0.1 nginx.localhost
127.0.0.1 whoami.localhost
```
Si de pronto encuentras un error de **404 No encontrado**, asegúrese de que no haya entradas en conflicto y que solo estén presentes estos dos dominios.

### 3. VAmos  A iniciar el contenedor 
```bash
docker compose up -d
```
Esto nos iniciará nuestro:
- Panel de control de Traefik (accesible en http://localhost:8080/dashboard/)
- Nginx (en https://nginx.localhost)
- Whoami (en https://whoami.localhost)

### 4. 
Autenticación
Para acceder al servicio Nginx, utilice:
- **Nombre de usuario:** `123`
- **Contraseña:** `123`
  Cuando entramos a https://nginx.localhost/ 

![image](https://github.com/user-attachments/assets/b5ffd626-4d99-4c2d-8781-4217a16d8867)


Respuesta al entar a  http://localhost:8080/dashboard/#/

![image](https://github.com/user-attachments/assets/a6288579-d3e3-4694-98c5-165e8446a9bc)

Respuesta al entar a https://whoami.localhost/ en un explorador
![image](https://github.com/user-attachments/assets/2beaeba1-5ecb-430d-908e-161f756cbbea)


### Para la solución del problema
- **404 No encontrado**: Asegúrese de que `/etc/hosts` esté configurado correctamente.
- Revise los registros de Traefik con:
```bash
docker logs traefik
```

