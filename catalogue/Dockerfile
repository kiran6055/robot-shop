FROM    node
RUN     npm install
RUN     mkdir /opt/server/
WORKDIR /opt/server/
COPY    /*/ /opt/server/
EXPOSE  8080
ENTRYPOINT [ "node", "server.js"]