FROM node:14
WORKDIR /opt/server/
RUN addgroup cart && adduser --system cart && usermod -aG cart cart
RUN chown -R cart:cart /opt/server
USER cart
COPY package.json /opt/server
COPY server.js /opt/server
RUN npm install
EXPOSE 8080
ENTRYPOINT ["node", "server.js"]