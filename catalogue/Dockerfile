FROM    node
WORKDIR /opt/server/
RUN addgroup catalogue && adduser --system catalogue && usermod -aG catalogue catalogue
RUN chown -R catalogue:catalogue /opt/server
RUN ls - lrt
USER catalogue
COPY    package.json /opt/server/
COPY    server.js /opt/server
RUN     npm install
EXPOSE  8080
ENTRYPOINT [ "node", "server.js"]