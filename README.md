# Hypersomnia homepage

Currently hosted at https://hypersomnia.xyz/

## Installation

```bash
sudo add-apt-repository ppa:ondrej/php
sudo apt update
sudo apt install memcached php8.2 php8.2-zip php8.2-curl php8.2-memcached -y

php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php composer-setup.php
php -r "unlink('composer-setup.php');"
sudo mv composer.phar /usr/local/bin/composer

cd /var/www/html
composer update
```

## Configuration

`sudo nano /etc/php/8.2/fpm/php.ini`
```ini
session.save_handler = memcached
session.save_path = "localhost:11211"
```

`sudo nano /var/www/html/.env`
```env
# Base URL
APP_URL=http://localhost/Hypersomnia-homepage/

# Cache (true or false)
CACHE=false

# Path to arenas directory
ARENAS_PATH=C:\hypersomnia\content\arenas

# YouTube API Key
APIKEY_YOUTUBE=

# Admins (comma-separated format)
ADMINS=550080230161645592,231574084931026944

# Discord OAuth settings
DISCORD_CLIENT_ID=
DISCORD_CLIENT_SECRET=
DISCORD_REDIRECT_URI=
```
