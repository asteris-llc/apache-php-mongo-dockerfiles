
##Overview

This dockerfile allows you to build a container that is suitable for running and testing PHP applications that use Mongo as a Data store.


##Components

- Base: Ubuntu 14.04
- PHP: 5.5x
- Mongo PHP driver (PECL install): 1.5x
- PHP composer
- MongoDB 2.2x binaries 
- Apache 2.4 with mod_rewrite enabled


##Running & Building
###Using this container as a base 
Use this container as a base for your application. Below is an example Dockerfile in which we add a VHost to the apache config:

	FROM asteris/apache-php-mongo:latest

    ADD MyVhost.conf /etc/apache2/sites-enabled/

    CMD ["/run.sh"]
    
###Running
    
    docker run -d -v /host/www:/app -p 80 asteris/apache-php-mongo:latest

##Copyright
Asteris, LLC 2014. Released under the Apache 2.0 License