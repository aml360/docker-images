FROM ubuntu
RUN apt-get update && apt-get -y install curl gcc-aarch64-linux-gnu wget
RUN bash -c "$(curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs)" --  -y
ENV PATH="${PATH}:/root/.cargo/bin"

# RUN node --version

ENV NODE_VERSION=16.13.0
RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
ENV NVM_DIR=/root/.nvm
RUN . "$NVM_DIR/nvm.sh" && nvm install ${NODE_VERSION}
RUN . "$NVM_DIR/nvm.sh" && nvm use v${NODE_VERSION}
RUN . "$NVM_DIR/nvm.sh" && nvm alias default v${NODE_VERSION}
ENV PATH="/root/.nvm/versions/node/v${NODE_VERSION}/bin/:${PATH}"

RUN npm i -g pnpm
