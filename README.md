# mosquitto-py-export-data

Mosquitto plugin in Python.

Build
=========
        apt install libwebsockets8 libwebsockets-dev libc-ares2 libc-ares-dev openssl uuid uuid-dev python3-dev

        wget http://mosquitto.org/files/source/mosquitto-1.5.7.tar.gz && tar xzvf mosquitto-1.5.7.tar.gz && cd mosquitto-1.5.7

        make
        make install

        groupadd mosquitto && useradd -s /sbin/nologin mosquitto -g mosquitto -d /var/lib/mosquitto
        mkdir -p /var/log/mosquitto/ /var/lib/mosquitto/ /etc/mosquitto/conf.d/
        chown -R mosquitto:mosquitto /var/log/mosquitto/ && chown -R mosquitto:mosquitto /var/lib/mosquitto/ && chown -R mosquitto:mosquitto /etc/mosquitto/conf.d/

        =========== /etc/mosquitto/mosquitto.conf ===================
        pid_file /var/run/mosquitto.pid

        persistence true
        persistence_location /var/lib/mosquitto/

        log_dest file /var/log/mosquitto/mosquitto.log

        include_dir /etc/mosquitto/conf.d
        ==============================================================

        cd

        git clone https://github.com/kolesnikov-a-p/mosquitto-py-export-data.git

        cd mosquitto-py-export-data

        make
        make install

        /usr/local/sbin/mosquitto -c /etc/mosquitto/mosquitto.conf