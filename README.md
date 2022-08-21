# Simple Wordpress Docker Container

A simple and quicly docker container for wordpress development.

This container has Wordpress, Mysql and Adminer.

## Setup

1. Clone the repo or download it.
2. Run ``docker compose up -d``.
3. Access http://localhost:8080 in your browser ans setup wodpress.
4. Start coding your theme in ``theme`` folder.

### More details

- Only your theme folder is mapped, this covers most common wordpress projects. If you want map more folder, just added in ``docker-compose.yml`` file, like:
```
volumes:
    - ./theme:/var/www/html/wp-content/themes/mytheme
    - ./plugins:/var/www/html/wp-content/plugins
```
- You can access Adminer in http://localhost:8888.

- This container doesn't have ``restart: always`` config purposely, just to have more control what sites (containers) I am working in the moment. You can add in ``docker-compose.yml`` if you want.

- If you have to run multiple wordpress sites (containers) in the same time, make sure you change the ports mapped in ``docker-compose.yml``, use a different port for each site (dont forget Adminer's ports)

- If you have trouble with permission in theme folder (or another folder that you are mapped) in linux or WSL, use the command: ``sudo chown your_user ./theme``,