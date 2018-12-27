FROM registry.gitlab.com/nepuntobiz/resource/docker-images/php:latest as develop

FROM develop as production
USER root

COPY . ./
RUN chown -R nobody:nobody *; \
    composer dump-autoload --no-dev --classmap-authoritative

CMD [ "sh", "-c", "php artisan optimize && php-fpm -R -F" ]
