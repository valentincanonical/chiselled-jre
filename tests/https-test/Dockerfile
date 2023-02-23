FROM ubuntu:22.04 AS builder

RUN apt-get update && apt-get install -y openjdk-8-jdk

WORKDIR /app
ADD src ./

RUN javac -source 8 -target 8 Main.java -d .

FROM ubuntu/chiselled-jre:8-22.04_edge

WORKDIR /
COPY --from=builder /app/Main.class .

CMD [ "Main" ]
