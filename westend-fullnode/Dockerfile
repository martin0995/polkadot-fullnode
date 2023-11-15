FROM ubuntu:latest AS build

# Install necessary dependencies
RUN apt-get update \
    && apt-get install -y curl \
    && rm -rf /var/lib/apt/lists/*

# Download and make the polkadot binary executable
RUN curl -sL https://github.com/paritytech/polkadot/releases/download/v1.0.0/polkadot -o polkadot \
    && chmod +x polkadot

# Now create the final image
FROM ubuntu:latest

# Copy the polkadot binary from the build image
COPY --from=build /polkadot .

# Set up the entry point for running the Westend fullnode
ENTRYPOINT [ "polkadot", "--name", "westend-sensei-fullnode", "--chain=westend" ]