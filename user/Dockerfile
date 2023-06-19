FROM node:14
WORKDIR /opt/server/
RUN addgroup user && adduser --system user && usermod -aG user user
RUN chown -R user:user /opt/server
USER user
COPY package.json /opt/server/
COPY server.js /opt/server/
RUN npm install
EXPOSE 8080
ENTRYPOINT ["node", "server.js"]