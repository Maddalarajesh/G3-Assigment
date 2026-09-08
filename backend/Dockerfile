FROM node:22-alpine As builder
WORKDIR /app
COPY . .
RUN npm install --legacy-peer-deps
RUN npm run build
COPY . .
#Stage-2
FROM node:22-alpine as production
WORKDIR /app
RUN addgroup -S non-root && adduser -S non-user -G non-root
COPY --from=builder --chown=non-user:non-root /app/node_modules ./node_modules
COPY --from=builder --chown=non-user:non-root /app/package.json ./package.json
COPY --from=builder --chown=non-user:non-root /app/dist ./app
EXPOSE 3000
USER non-user
CMD ["node","dist/server.js"]    
