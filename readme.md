# creacion con supabase
npx create-next-app@latest my-next-app --typescript

root/
├─ frontend/           # tu app creada con v0.dev (Next.js / React)
├─ supabase/           # configuración de Supabase autohospedado
├─ docker-compose.yml  # orquestación de todos los contenedores
└─ .env                # variables del entorno (seguras)
este seria el ejemplo de la estructura
### Supabase provee un stack Docker oficial que incluye:

- PostgreSQL + extensión PostgREST
- Supabase Auth
- Storage (archivos)
- Realtime (WebSockets)
- Studio (panel web tipo dashboard)

## clonas supabase
- git clone --depth 1 https://github.com/supabase/supabase
