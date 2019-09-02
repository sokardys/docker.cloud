ARG tag
FROM ghost:${tag}

WORKDIR /var/lib/ghost

RUN mkdir -p ./content.orig/adapters/storage/s3 && \
    npm install ghost-storage-adapter-s3 && \
    cp -r ./node_modules/ghost-storage-adapter-s3/* ./content.orig/adapters/storage/s3
