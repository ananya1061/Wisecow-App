# using ubuntu base image
FROM ubuntu:latest

# installing packages
RUN apt-get update && \
    apt-get install -y \
    bash \
    netcat-openbsd \
    fortune-mod \
    cowsay && \
    rm -rf /var/lib/apt/lists/*

# symbolic links for cowsay and fortune
RUN ln -s /usr/games/cowsay /usr/local/bin/cowsay && \
    ln -s /usr/games/fortune /usr/local/bin/fortune

# moving shell script to root directory and setting permission to execute
COPY wisecow.sh /
RUN chmod +x /wisecow.sh

# exposing port 4499
EXPOSE 4499

# running the shell script
CMD ["/wisecow.sh"]
