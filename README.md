Ansible Playbook for CakePHP development on LAPP (CentOS 6.x + PostgreSQL 9.3 + PHP 5.5)
-------------------------------------------

This playbook requires Ansible 1.4

    TARGET_HOST=10.x.x.x
    MAIN_USERNAME=username
    MAIN_PASSWORD=password
    DOCROOT=/var/www/html/htdocs
    DBROOT=/var/lib/pgsql/9.3
    PERMIT_NETWORK=10.0.0.0/8
    CAKE_ENV_MODE=development
    ansible-playbook -i <(echo ${TARGET_HOST}) -u root -k site.yml \
      --extra-vars "main_username=${MAIN_USERNAME} main_password=`openssl passwd -salt salty -1 ${MAIN_PASSWORD}` docroot=${DOCROOT} dbroot=${DBROOT} permit_network=${PERMITE_NETWORK} cake_env_mode=${CAKE_ENV_MODE}"
