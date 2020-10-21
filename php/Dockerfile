FROM php:7.4-fpm
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install -j$(nproc) gd
RUN docker-php-ext-install gettext
RUN docker-php-ext-install pdo_mysql
#RUN apt install -y mysql-client 
RUN docker-php-ext-install mysqli
RUN apt-get install -y locales
RUN locale-gen pl_PL.UTF-8
# Set the locale
RUN sed -i '/pl_PL.UTF-8/s/^# //g' /etc/locale.gen && \
    locale-gen
ENV LANG pl_PL.UTF-8
ENV LANGUAGE pl_PL.UTF-8
ENV LC_ALL pl_PL.UTF-8
