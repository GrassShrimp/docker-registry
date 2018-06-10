# Docker Registry
1. generate self ssl certificate

        $ openssl req -newkey rsa:4096 -nodes -sha256 -keyout ./auth/domain.key -x509 -days 365 -out ./auth/domain.crt

2. create password file

        $ docker run --rm --entrypoint htpasswd registry -Bbn testuser testpassword > ./auth/htpasswd

3. service start up

        $ docker-compose up -d