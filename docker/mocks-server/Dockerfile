FROM node:14

WORKDIR /input

RUN apt-get update && apt-get install -y \
    git \
    vim \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN npm install -g @mocks-server/main
EXPOSE 3100

# CMD ["mocks", "start"]
CMD ["/bin/bash"]
