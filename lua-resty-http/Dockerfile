ARG NGINX_FROM_IMAGE=lowlevel1989/nginx:1.25.2-alpine-lua

FROM ${NGINX_FROM_IMAGE} as builder

ARG LUA_RESTY_REPO=https://github.com/ledgetech/lua-resty-http
ARG LUA_RESTY_HTTP_VERSION=0.17.1

RUN curl -o /tmp/lua-resty-http.tar.gz -LO \
        ${LUA_RESTY_REPO}/archive/refs/tags/v${LUA_RESTY_HTTP_VERSION}.tar.gz && \
        cd /tmp && ls -l && tar -xzvf lua-resty-http.tar.gz && \
        mv lua-resty-http-${LUA_RESTY_HTTP_VERSION} lua-resty-http

FROM ${NGINX_FROM_IMAGE}
COPY --from=builder /tmp/lua-resty-http/lib/resty /usr/share/nginx-luajit-2.1/resty
