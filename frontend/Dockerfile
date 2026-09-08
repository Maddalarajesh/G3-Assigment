FROM node:22-alpine As a builder
WORKDIR /app
RUN npm install --legacy-peer-deps
RUN npm run build
COPY . .
#stage-2
FROM Node:22-alpine as a production
RUN addgroup -S testfrontend && \
    adduser -S frontgroup -G testfrontend
RUN rm /var/nginx/conf.d/default.conf  
COPY nginx.conf /var/nginx/conf.d/default.conf
COPY --from=builder /app/dist /usr/share/nginx/html
RUN chown -R frontgroup:testfrontend \
             /usr/share/nginx/html \
             /var/log/nginx \
             /var/cache/nginx \
             /etc/nginx/conf.d \
             /run
USER frontgroup
EXPOSE 8080
CMD ["nginx","-g","daemon off"]
             
             
    
    
