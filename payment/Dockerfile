FROM python
EXPOSE 8080
WORKDIR /app
RUN addgroup payment && adduser --system payment && usermod -aG payment pyament
RUN chmod -R payment:payment /app/
RUN ls - lrt
USER payment
COPY rabbitmq.py payment.ini payment.py rabbitmq.py requirements.txt /app/
RUN pip install -r requirements.txt
ENTRYPOINT ["uwsgi", "--ini", "payment.ini"]