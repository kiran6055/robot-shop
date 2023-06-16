FROM    node
RUN     npm install
WORKDIR /opt/server/
COPY    package.json /opt/server/
COPY    server.js /opt/server
EXPOSE  8080
ENTRYPOINT [ "node", "server.js"]