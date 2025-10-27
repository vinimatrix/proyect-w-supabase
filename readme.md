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
## vas a la carpeta de supabase y copias el .env-example
- cd supabase/docker
- windows: COPY .env-example .env / linux: cp env-example .env
- cambias lo necesario

## inicias los contenedores
- docker-compose up -d


## adicional puedes meter el front en el mismo contenedor (recomendado separarlos)
''' frontend:
            build: ./frontend
            container_name: frontend_app
            depends_on:
            - api
            - auth
            ports:
            - "3000:3000"
            environment:
            NEXT_PUBLIC_SUPABASE_URL: ${NEXT_PUBLIC_SUPABASE_URL}
            NEXT_PUBLIC_SUPABASE_ANON_KEY: ${NEXT_PUBLIC_SUPABASE_ANON_KEY}
            networks:
            - supabase_net

    networks:
    supabase_net:
        driver: bridge '''
