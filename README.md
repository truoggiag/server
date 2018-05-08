# compile-php-7.2.4-ubuntu-16.04
Note biên dịch PHP 7.2.4 trên ubuntu server 16.04

# 1. Sau khi cài Ubuntu server xong, cài apache2:
$sudo apt-get install apache2
# 2. Cài các tool:
$sudo apt-get install autoconf build-essential curl libtool \\
  libssl-dev libcurl4-openssl-dev libxml2-dev \\
  libreadline-dev libzip-dev libzip4 openssl \\
  pkg-config zlib1g-dev  \\
  libsodium-dev;
# 3. Cài mysql
$sudo apt-get install mysql-server mysql-client
# 4. Tải file source và giải nén
$sudo wget http://php.net/distributions/php-7.2.4.tar.gz
$sudo tar -vxf php-7.2.4.tar.gz
$sudo cd php-7.2.4

# 5. Tạo thư mục build: 

$sudo mkdir /usr/php724 

# 6. Chạy config: 
$sudo ./configure --prefix=/usr/php724 \\
    --enable-mysqlnd \\
    --with-pdo-mysql \\
    --with-pdo-mysql=mysqlnd \\
    --enable-bcmath \\
    --enable-fpm \\
    --with-fpm-user=www-data \\
    --with-fpm-group=www-data \\
    --disable-cgi \\
    --enable-mbstring \\
    --enable-phpdbg \\
    --enable-shmop \\
    --enable-sockets \\
    --enable-sysvmsg \\
    --enable-sysvsem \\
    --enable-sysvshm \\
    --enable-zip \\
    --with-libzip=/usr/lib/x86_64-linux-gnu \\
    --with-zlib \\
    --with-curl \\
    --with-pear \\
    --with-openssl \\
    --enable-pcntl \\
    --with-readline \\
    --with-sodium;

# 7. chạy lệnh để compile:
$sudo make
$sudo make install
