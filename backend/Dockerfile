FROM node:22-alphine  as a builder
WORKDIR /app
RUN npm install --legacy-peer-deps
RUN npm run build
COPY . .
#Stage-2
FROM node:22-alphine as a production
WORKDIR /app
RUN groupadd -S non-root && \
    useradd -S non-user -G non-root
COPY --from=builder --chown=non-user:non-root && \
    /app/node_modules ./node_modules
COPY --from=builder --chown=non-user:non-root && \
    /app/package.json ./package.json
COPY --from=builder --chown=non-user:non-root && \
    /app/dist ./app
EXPOSE 3000
USER non-user
CMD ["node","dist/server.js"]    
