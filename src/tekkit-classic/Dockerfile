FROM openjdk:20-slim-buster

RUN apt-get update && apt-get install -y curl unzip wget tmux


RUN mkdir -p /tekkit-classic

RUN wget -O /tmp/tekkit.zip https://servers.technicpack.net/Technic/servers/tekkit/Tekkit_Server_3.1.2.zip
RUN unzip /tmp/tekkit.zip -d /tekkit-classic
RUN rm tekkit-classic.zip

ADD ./launch.sh /tekkit-classic/launch.sh
RUN chmod +x /tekkit-classic/launch.sh

VOLUME /tekkit-classic
EXPOSE 25565

WORKDIR /tekkit-classic
RUN chmod +x Tekkit.jar
RUN echo "eula=true" > eula.txt

CMD ["./launch.sh"]

#ENTRYPOINT [ "/tekkit-classic/launch.sh" ]

#CMD ["java", "-Xmx1024M", "-Xms1024M", "-jar", "Tekkit.jar", "nogui"]
