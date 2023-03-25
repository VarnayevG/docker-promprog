FROM ubuntu:21.04
ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y cmake python3-pip sudo

COPY CMakeLists.txt CMakeLists.txt
COPY B B
COPY C C
RUN cmake .
RUN make

RUN useradd -m techproguser && echo "techproguser:techproguser" | chpasswd && adduser techproguser sudo
USER techproguser

EXPOSE 5000

RUN pip3 install flask


COPY app.py .
ENV FLASK_APP=app.py
CMD bin/C && python3 -m flask run --host=0.0.0.0