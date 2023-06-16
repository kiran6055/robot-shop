FROM    node
WORKDIR /opt/server/
COPY    package.json /opt/server/
COPY    server.js /opt/server
RUN     npm install
EXPOSE  8080
ENTRYPOINT [ "node", "server.js"]