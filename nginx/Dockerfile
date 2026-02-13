# Base image
FROM nginx:latest

# Installer bash
RUN apt-get update && apt-get install -y bash

# Créer les dossiers pour logs et cache à l'intérieur du conteneur
RUN mkdir -p /var/log/nginx /var/cache/nginx \
    && touch /var/log/nginx/access.log /var/log/nginx/error.log /var/log/nginx/fastcgi_cache.log \
    && chown -R nginx:nginx /var/log/nginx /var/cache/nginx \
    && chmod 644 /var/log/nginx/*.log





# Copier la configuration Nginx
COPY ./nginx.conf /etc/nginx/nginx.conf
COPY ./conf.d/ /etc/nginx/conf.d/

# Exposer le port HTTP
EXPOSE 80

# Lancer Nginx au premier plan
CMD ["nginx", "-g", "daemon off;"]
