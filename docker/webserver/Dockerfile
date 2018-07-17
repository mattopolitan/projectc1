# 从官方PHP镜像构建 with PHP 7 image
FROM       php:7-apache

# 将index.php复制到容器内的/var/www目录下
# ADD        index.php /var/www/

# 对外暴露8080端口
# EXPOSE     8080

# 设置容器默认工作目录为/var/www
# WORKDIR    /var/www/

# 容器运行后默认执行的指令
# ENTRYPOINT ["php", "-S", "0.0.0.0:8080"]

# Install libpng-dev & libpng-dev curl libcurl4-openssl-dev
RUN apt-get update -y && apt-get install -y libpng-dev curl libcurl4-openssl-dev

# Install official Docker PHP modules PDO extension & MySQL driver & gd & curl
RUN docker-php-ext-install pdo pdo_mysql gd curl

# Enable mod_rewrite and restart Apache
RUN a2enmod rewrite
RUN service apache2 restart
