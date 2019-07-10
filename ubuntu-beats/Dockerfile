FROM ubuntu:latest

RUN apt-get update
RUN apt-get install -y wget gnupg
RUN wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | apt-key add -
RUN apt-get install -y apt-transport-https
RUN echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" | tee -a /etc/apt/sources.list.d/elastic-7.x.list
RUN apt-get update && apt-get install -y packetbeat filebeat heartbeat-elastic metricbeat
# RUN update-rc.d packetbeat defaults 95 10
# RUN update-rc.d filebeat defaults 95 10
# RUN update-rc.d heartbeat-elastic defaults 95 10
# RUN update-rc.d metricbeat defaults 95 10

CMD service filebeat start && service metricbeat start && service heartbeat-elastic start && bash