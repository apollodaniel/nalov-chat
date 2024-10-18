FROM node:22.10-bookworm AS builder

RUN mkdir /build
COPY nalov-chat-backend/ /build
WORKDIR /build

RUN npm install
RUN npx tsc --outDir dist

FROM node:23.0.0

WORKDIR /app
COPY --from=builder /build/dist ./
COPY --from=builder /build/node_modules ./node_modules
COPY --from=builder /build/public ./public
RUN apt update && apt install imagemagick -y
COPY ./policy.xml /etc/ImageMagick-6/policy.xml


CMD [ "node", "index.js"]
