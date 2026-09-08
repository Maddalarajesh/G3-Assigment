FROM node:22-slim As builder
WORKDIR /app
COPY . .
RUN apt-get update -y && apt-get install -y openssl
RUN npm install --legacy-peer-deps
RUN npm run build
#Stage-2
FROM node:22-slim as production
WORKDIR /app
RUN groupadd --system non-root \
    && useradd --system non-user -G non-root
COPY --from=builder --chown=non-user:non-root /app/node_modules ./node_modules
COPY --from=builder --chown=non-user:non-root /app/package.json ./package.json
COPY --from=builder --chown=non-user:non-root /app/dist ./dist
EXPOSE 3000
USER non-user
CMD ["node","dist/index.js"]    
