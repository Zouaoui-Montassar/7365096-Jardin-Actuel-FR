
FROM php:8.1-fpm


RUN apt-get update && apt-get install -y \
    curl \
    libicu-dev \
    libpq-dev \
    libzip-dev \
    && docker-php-ext-install -j$(nproc) intl pdo pdo_mysql zip


EXPOSE 8081


WORKDIR /var/www/html

#Edited the installation command for composer due to an issue when trying to create an image 
RUN apt-get update && \
    apt-get install -y curl && \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer


COPY . .


CMD ["php", "-S", "0.0.0.0:8081", "-t", "public/"]




