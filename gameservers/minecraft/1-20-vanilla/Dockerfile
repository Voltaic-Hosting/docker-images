FROM bitnami/java:latest

# Set default values for environment variables
ENV SERVER_NAME="A Dank Minecraft Server"
ENV GAMEMODE="survival"
ENV DIFFICULTY="normal"
ENV LEVEL_TYPE="default"
ENV MOTD="A Dank Minecraft Server"
ENV PVP="true"
ENV MAX_PLAYERS="20"
ENV VIEW_DISTANCE="13"
ENV ONLINE_MODE="false"
ENV WHITELIST="false"

# Copy Minecraft server jar
COPY ./server.jar /mcserver/server.jar
COPY ./whitelist.json /mcserver/whitelist.json

# Set working directory to Minecraft directory
WORKDIR /mcserver

RUN chmod +x /mcserver/server.jar

# Start Minecraft server and agree to EULA
CMD echo "eula=true" > eula.txt && \
    echo "server-name=${SERVER_NAME}" > server.properties && \
    echo "gamemode=${GAMEMODE}" >> server.properties && \
    echo "difficulty=${DIFFICULTY}" >> server.properties && \
    echo "level-type=${LEVEL_TYPE}" >> server.properties && \
    echo "motd=${MOTD}" >> server.properties && \
    echo "pvp=${PVP}" >> server.properties && \
    echo "max-players=${MAX_PLAYERS}" >> server.properties && \
    echo "view-distance=${VIEW_DISTANCE}" >> server.properties && \
    echo "online-mode=${ONLINE_MODE}" >> server.properties && \
    java -Xmx4096M -Xms4096M -jar server.jar nogui