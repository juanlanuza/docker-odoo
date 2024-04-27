Este tiene mezcla de todo para probar a hacer un definitivo


Tengo que lanzar lo siguiente:

    chmod +x entrypoint.sh


También tener un odoo.conf en la raiz, porque si no peta









DEBO TENER EN CUENTA CUANDO SUBA LOS ARCHIVOS AL SERVIDOR QUE TENDRÉ QUE LANZAR UNOS COMANDOS MINIMOS DANDO PERMISO DE ACCESO:

  chmod 644 /home/docker/apps/odoo_pd/odoo_pg_pass

Y a las carpetas de odoo que las he  pegado de nuevas:

  chmod 777 /odoo-web-data
  chmod 777 /config
  chmod 777 /addons

  chmod 777 config/odoo.conf

AQUI NO CREO PORQUE ESTAS CARPETAS NO EXISTEN CUANDO LO SUBIMOS:::::

      - POSTGRES_DB=postgres
      - POSTGRES_PASSWORD_FILE=/run/secrets/postgresql_password
      - POSTGRES_USER=odoo
      - PGDATA=/var/lib/postgresql/data/pgdata

# PERMISOS LOCOS TOTALES
  
    chmod 777 odoo-web-data && chmod 777 config && chmod 777 addons && chmod 777 config/odoo.conf && chmod 644 /home/docker/apps/odoo_pd/odoo_pg_pass





REVISAR LO SIGUIENTE::::


#!/bin/bash

# Para crear el archivo y pegar el contenido usa:

# touch installDocker2.sh && chmod +x installDocker2.sh && nano installDocker2.sh
# ./installDocker2.sh







## Crear Directorios
mkdir -p '/home/docker/apps/odoo_pd/config'


################################################################################
## ODOO- Directorios EXTRA - REVISAR SI HACEN FALTA
################################################################################

mkdir -p '/home/docker/apps/odoo_pd/addons'
mkdir -p '/home/docker/apps/odoo_pd/odoo-db-data'
mkdir -p '/home/docker/apps/odoo_pd/odoo-web-data'

mkdir -p '/etc/odoo'


################################################################################
## ODOO- RAROS - REVISAR SI HACEN FALTA
################################################################################

########## ESTE EN PRINCIPIO NO HACE FALTA EN EL SERVIDOR VPS

mkdir -p '/mnt/extra-addons'

## Yo creo que el error es dentro del contenedor con lo que no tengo que crear carpeta en el vps

########## REVISAR LO DE LOS LOGS POR SI TENGO QUE DAR PERMISOS A ODOO
mkdir -p '/etc/odoo'

## Crear fichero de log
touch '/etc/odoo/odoo-server.log'


################################################################################
## Docker-Compose - Start Odoo
################################################################################

## Lanzo el archivo de Docker-Compose creado
cd /home/docker/apps/odoo_pd/
docker-compose up

## Lanzo Docker-Compose para que quede arrancado
docker-compose up -d









DEBO TENER EN CUENTA CUANDO SUBA LOS ARCHIVOS AL SERVIDOR QUE TENDRÉ QUE LANZAR UNOS COMANDOS MINIMOS DANDO PERMISO DE ACCESO:

  chmod 644 /home/docker/apps/odoo_pd/odoo_pg_pass

Y a las carpetas de odoo que las he  pegado de nuevas:

  chmod 777 /odoo-web-data
  chmod 777 /config
  chmod 777 /addons

  chmod 777 config/odoo.conf

AQUI NO CREO PORQUE ESTAS CARPETAS NO EXISTEN CUANDO LO SUBIMOS:::::

      - POSTGRES_DB=postgres
      - POSTGRES_PASSWORD_FILE=/run/secrets/postgresql_password
      - POSTGRES_USER=odoo
      - PGDATA=/var/lib/postgresql/data/pgdata

# PERMISOS LOCOS TOTALES
  
    chmod 777 odoo-web-data && chmod 777 config && chmod 777 addons && chmod 777 config/odoo.conf && chmod 644 /home/docker/apps/odoo_pd/odoo_pg_pass