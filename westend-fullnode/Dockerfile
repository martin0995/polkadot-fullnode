# syntax=docker/dockerfile:1
FROM ubuntu:22.04 AS build

# Install necessary dependencies
RUN ["apt-get", "update"]
RUN ["apt-get", "upgrade", "-y"]
RUN ["apt-get", "install", "--fix-missing"]
RUN ["apt-get", "install", "-y", "wget" ]

# Install necessary dependencies, including updating package lists
# RUN apt-get update && apt-get upgrade -y && apt-get install --fix-missing -y wget

# Download and make the polkadot binary executable
RUN wget https://github.com/paritytech/polkadot/releases/download/v1.0.0/polkadot -o polkadot

# Now create the final image
FROM ubuntu:22.04

WORKDIR /data

# Copy the polkadot binary from the build image
COPY --from=build /polkadot .
RUN chmod +x ./polkadot

# Set up the entry point for running the Westend fullnode
CMD [ "polkadot", "--name", "westend-sensei-fullnode", "--chain=westend" ]