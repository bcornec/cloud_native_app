FROM debian:stretch
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update
RUN apt-get install -y python3.5 
RUN apt-get install -y python3-pip
RUN apt-get install -y python3-flask
RUN apt-get install -y default-libmysqlclient-dev sed
RUN pip3 install mysqlclient
RUN useradd i
COPY config.py i.conf i.py /home/i/
RUN chown -R i:i /home/i/
RUN sed -i -e 's/dbhost=.*/dbhost=db/' /home/i/i.conf
EXPOSE 8080
USER i
WORKDIR /home/i
CMD ["./i.py"]
