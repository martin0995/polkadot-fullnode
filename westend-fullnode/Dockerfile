# syntax=docker/dockerfile:1
FROM ubuntu:22.04 AS build

# Define the name of the node
ARG NODE_NAME=your-node-name

# Install necessary dependencies
RUN apt update && \
    apt install -y curl

# Download and make the polkadot binary executable
RUN curl -sL https://github.com/paritytech/polkadot/releases/download/v1.0.0/polkadot -o polkadot

# Now create the final image
FROM ubuntu:22.04

WORKDIR /data

# Copy the polkadot binary from the build image
COPY --from=build /polkadot /usr/local/bin/
RUN chmod +x /usr/local/bin/polkadot

# Set up the entry point for running the Westend fullnode
CMD [ "polkadot", "--name", "${NODE_NAME}", "--chain=westend" ]