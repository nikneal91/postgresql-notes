https://pgexercises.com/gettingstarted.html

docker volume create postgres-data


# use -v to bind host directory to the docker image directory host:docker 
docker run --rm -v postgres-data:/data -v $(pwd):/host busybox cp /host/clubdata.sql /data/


#bind the volume to the scripts folder in the container 
docker run -it --rm --network postgres-network -v postgres-data:/scripts postgres psql -h some-postgres -U postgres -f /scripts/clubdata.sql


docker run --rm -d -p5432:5432 --name some-postgres --network postgres-network -e POSTGRES_PASSWORD=mysecretpassword -e PGDATA=/var/lib/postgresql/data/pgdata  -v C:\Users\nikhilsharma03\Downloads\docker-volumes\postgres-volume\:/var/lib/postgresql/data postgres


Now learning 

for window use complete path in window format 

2 ways to bind mount

1. host mount giving the whole path on local machine
2. using volumes create the directory path inside docker handled by docker, can be attached to multiple containers


docker run -it --rm --network postgres-network postgres psql -h some-postgres -U postgres -f /var/lib/postgresql/data/pgdata/scripts/insert.sql


