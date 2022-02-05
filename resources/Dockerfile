FROM debian:buster

ENV DEBIAN_FRONTEND="noninteractive" TZ=Europe/UTC    

RUN apt-get update -yy

RUN apt-get install -yy cmake pkg-config

RUN apt-get install -yy libssl-dev libplist-dev libavahi-compat-libdnssd-dev libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev gstreamer1.0-libav gstreamer1.0-plugins-bad gstreamer1.0-plugins-good gstreamer1.0-pulseaudio

COPY ./ /uxplay

WORKDIR ./uxplay

RUN cmake .

RUN make

RUN make install

CMD uxplay -as pulsesink
