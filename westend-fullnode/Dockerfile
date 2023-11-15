FROM ubuntu:latest AS build

# Install necessary dependencies
RUN ["apt-get", "update"]
RUN ["apt-get", "install", "-y", "wget"]

# Download and make the polkadot binary executable
RUN wget https://github.com/paritytech/polkadot/releases/download/v1.0.0/polkadot -o polkadot

# Now create the final image
FROM ubuntu:latest

WORKDIR /data

# Copy the polkadot binary from the build image
COPY --from=build /polkadot .
RUN chmod +x ./polkadot

# Set up the entry point for running the Westend fullnode
ENTRYPOINT [ "polkadot", "--name", "westend-sensei-fullnode", "--chain=westend" ]