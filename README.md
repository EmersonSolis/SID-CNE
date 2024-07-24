# ---------------------------------------------------------------------------
Antes de inciar se deben instalar los prerrequisitos, dirigirse a la carpeta 'Prrerequisitos' y ejecutar desde consola
./Prerrequisitos.sh

# ---------------------------------------------------------------------------
Para levantar la PKI ingresar a la carpeta 'cne-network'
Dentro de la carpeta ejecutar desde consola

Levantar la infraestructura con las CAs
./network.sh up -ca 

Crear y unir las Orgs a los canales
 ./network.sh up createChannel -c cnechannel

 Deploy Chaincode
 ./network.sh deployCC -c cnechannel -ccn basic -ccp ../asset-consortium-cne/chaincode-go -ccl go

# ---------------------------------------------------------------------------
Para bajar la Infraestructura ejecutar
./network.sh down

# ---------------------------------------------------------------------------
En caso de errores ejecutar
docker stop $(docker ps -a -q)  ; docker rm -f $(docker ps -aq) ; docker system prune -a ; docker volume prune ; docker ps -a ; docker images -a ; docker volume ls
