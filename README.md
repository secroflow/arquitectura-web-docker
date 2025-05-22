# Proxecto Docker con mounts e volume

Arquitectura web con frontend, backend e base de datos. Inclúe persistencia e montaxes de código en tempo real.


## Descrición do proxecto  
Aplicación web básica despregada con Docker Compose, que inclúe:  
- **Frontend**: Servido con Nginx (páxina estática `index.html`).  
- **Backend**: Aplicación Python (`app.py`) con Flask/FastAPI.  
- **Base de datos**: PostgreSQL con persistencia de datos mediante volumes Docker.  

·Servizos e configuración  

1. Servizos
| Servizo   | Imaxe          | Porto | Volume/Bind Mount           |  
|-----------|----------------|-------|------------------------------|  
| Frontend  | `nginx:alpine` | 8080  | `./frontend:/usr/share/nginx/html` |  
| Backend   | Custom (Python)| 5000  | `./backend:/app`              |  
| PostgreSQL| `postgres:15`  | 5432  | `db_data:/var/lib/postgresql/data` + `./db/init.sql:/docker-entrypoint-initdb.d/init.sql` |  

2. Variables de entorno (BD)  
POSTGRES_USER=usuario 
POSTGRES_PASSWORD=abc123.  
POSTGRES_DB=postgres  
