This is the legacy MaxMind v1 GeoIP PHP extension. This will work on PHP 7.x and PHP 8.x.

Unless you have old code that needs this, you are better off using [GeoIP2](https://github.com/maxmind/GeoIP2-php)

Install (Ubuntu 24.04 / PHP 8.3 / Apache)
```bash
apt update
apt install php8.3-dev libgeoip-dev
git clone https://github.com/rlerdorf/geoip.git
cd geoip/
phpize8.3
./configure 
make 
make install
echo "extension=geoip.so" > /etc/php/8.3/mods-available/geoip.ini
ln -s /etc/php/8.3/mods-available/geoip.ini /etc/php/8.3/fpm/conf.d/20-geoip.ini
ln -s /etc/php/8.3/mods-available/geoip.ini /etc/php/8.3/apache2/conf.d/geoip.ini
systemctl restart php8.3-fpm
systemctl restart apache2
