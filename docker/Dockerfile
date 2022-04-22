FROM ubuntu AS build

RUN apt-get -y update 
RUN apt-get -y install gcc 
RUN apt-get -y install g++
WORKDIR /gourav
COPY hello.cpp .
RUN g++ -o helloworld hello.cpp
#CMD [ "./helloworld" ]




FROM alpine:latest
WORKDIR /last
COPY --from=build /gourav/helloworld .
CMD [ "./helloworld" ]

