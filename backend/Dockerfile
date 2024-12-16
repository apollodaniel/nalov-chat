FROM node:22.10-bookworm AS builder

RUN mkdir /build
COPY ./nalov-chat-backend/ /build
WORKDIR /build

RUN yarn install
RUN yarn exec tsc --outDir dist

FROM node:23.0.0

WORKDIR /app
COPY --from=builder /build/dist /app/
COPY --from=builder /build/node_modules /app/node_modules
COPY --from=builder /build/default /app/default
RUN apt update && apt install libvips-dev imagemagick-doc enscript gnuplot grads graphviz hp2xx html2ps libwmf-bin povray texlive-base-bin transfig libjxr-tools imagemagick -y

COPY policy.xml /etc/ImageMagick-6/policy.xml

CMD [ "node", "index.js"]
