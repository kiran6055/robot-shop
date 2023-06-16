FROM python
EXPOSE 8080
USER root
WORKDIR /app
COPY rabbitmq.py payment.ini payment.py rabbitmq.py requirements.txt /app/
RUN pip install -r requirements.txt
ENTRYPOINT ["uwsgi", "--ini", "payment.ini"]