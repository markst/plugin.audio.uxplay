FROM debian:buster

ENV DEBIAN_FRONTEND="noninteractive" TZ=Europe/UTC    

RUN apt-get update -yy

RUN apt-get install -yy cmake pkg-config

RUN apt-get install -yy libssl-dev libplist-dev 
RUN apt-get install -yy libavahi-compat-libdnssd-dev 
RUN apt-get install -yy libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev gstreamer1.0-libav gstreamer1.0-plugins-bad gstreamer1.0-plugins-good gstreamer1.0-pulseaudio

# hardware-accelerated Intel graphics, but not NVIDIA
#RUN apt-get install -yy gstreamer1.0-vaapi

COPY ./ /uxplay

WORKDIR ./uxplay

RUN cmake .

RUN make

RUN make install

CMD uxplay -as pulsesink
