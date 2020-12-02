FROM node:10-alpine
ARG tag

RUN apk update && apk add openssh-client git

ADD ssh_keys /root/.ssh
RUN chmod 600 /root/.ssh
RUN ssh-keyscan -p 22 github.com >> /root/.ssh/known_hosts

RUN git clone --branch $tag \
    --depth 1 \
    ssh://git@github.com/whiteyhat/lightnite-store.git \
    /app

WORKDIR /app

RUN rm -rf /root/.ssh

RUN yarn

CMD yarn start
