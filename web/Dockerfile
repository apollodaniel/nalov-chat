FROM node:22.10-bookworm AS builder

RUN mkdir /build
COPY nalov-chat-frontend/ /build
WORKDIR /build

RUN npm install
RUN npx vite build

FROM httpd:2.4
COPY --from=builder /build/dist /usr/local/apache2/htdocs/
COPY ./httpd.conf /usr/local/apache2/conf/httpd.conf
