### clonamos del repositorio oficial
~~~
$ git clone https://github.com/nginxinc/docker-nginx.git
$ cd docker-nginx/modules
~~~

### Version de la imagen de nginx y documentario
~~~
REF: https://hub.docker.com/_/nginx
~~~

### Documentación del modulo de lua
~~~
REF: https://github.com/openresty/lua-nginx-module
~~~

### Construimos nuestra imagen con el modulo deseado
~~~
$ podman build -t docker.io/lowlevel1989/nginx:1.25.2-alpine-lua \
                    --build-arg ENABLED_MODULES="ndk lua"        \
                    --build-arg NGINX_FROM_IMAGE="nginx:1.25.2-alpine" -f Dockerfile.alpine
~~~