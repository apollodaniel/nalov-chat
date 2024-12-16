FROM node:22.10-bookworm AS builder

RUN mkdir /build
COPY nalov-chat-frontend/ /build
WORKDIR /build

RUN yarn install
RUN yarn run vite build

FROM nginx:1.27.3

COPY --from=builder /build/dist /usr/share/nginx/html
COPY nginx.conf /etc/nginx/nginx.conf
