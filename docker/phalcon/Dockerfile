FROM mattrayner/lamp:latest-1604-php7

COPY ./apache2.conf /etc/apache2/
COPY ./phaphalcon.com.conf /etc/apache2/sites-available/
COPY ./phaphalcon.com.conf /etc/apache2/sites-enabled/
COPY ./000-default.conf /etc/apache2/sites-enabled/
COPY ./000-default.conf /etc/apache2/sites-available/

RUN /usr/bin/apt-get update && apt-get -y install git
        
RUN git clone https://github.com/phalcon/phalcon-devtools.git /usr/local/lib/phalcon-devtools && \
    ln -s /usr/local/lib/phalcon-devtools/phalcon.php /usr/bin/phalcon && \
    chmod +x /usr/bin/phalcon

RUN apt-get update && apt-get -y install curl software-properties-common

RUN curl -s "https://packagecloud.io/install/repositories/phalcon/stable/script.deb.sh" | bash
RUN apt-get -y install php7.3-phalcon



