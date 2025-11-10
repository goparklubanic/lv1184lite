FROM php:8.4-fpm-bookworm

# Install system dependencies
RUN apt-get update && apt-get install -y \
    git \
    curl \
    libpng-dev \
    libxml2-dev \
    libzip-dev \
    libonig-dev \
    zip \
    unzip \
    sqlite3 \
    libsqlite3-dev

# Install PHP extensions
RUN docker-php-ext-install \
    pdo \
    pdo_mysql \
    pdo_sqlite \
    sockets \
    exif \
    pcntl \
    bcmath \
    gd \
    zip \
    mbstring

# Install Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Create non-root user
RUN groupadd -g 1000 laravel && useradd -u 1000 -g laravel -m laravel

# Set working directory
WORKDIR /var/www/html

# Change ownership of our applications
RUN chown -R laravel:laravel /var/www/html

# Switch to non-root user
USER laravel

# Expose port 9000 for PHP-FPM
EXPOSE 9000

CMD ["php-fpm"]