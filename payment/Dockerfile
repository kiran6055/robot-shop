#FROM python:3.9
#EXPOSE 8080
#USER root
#WORKDIR /app
#COPY requirements.txt /app/
#RUN pip install -r requirements.txt
#COPY *.py /app/
#COPY payment.ini /app/
#CMD ["python", "payment.py"]
#CMD ["uwsgi", "--ini", "payment.ini"]


FROM python:3.9
EXPOSE 8080

# Create a non-root user
WORKDIR /app
RUN addgroup payment && adduser --system payment && usermod -aG payment payment
RUN chown -R payment:payment /app/
USER payment
COPY requirements.txt /app/
RUN pip install --payment -r requirements.txt
COPY *.py /app/
COPY  payment.ini /app/
CMD ["uwsgi", "--ini", "payment.ini"]

FROM python:3.9
EXPOSE 8080

# Create a non-root user
#RUN useradd -ms /bin/bash myuser
#USER myuser

#WORKDIR /app
#COPY --chown=myuser:myuser requirements.txt /app/
#RUN pip install --user -r requirements.txt
#COPY --chown=myuser:myuser *.py /app/
#COPY --chown=myuser:myuser payment.ini /app/

#CMD ["uwsgi", "--ini", "payment.ini"]
