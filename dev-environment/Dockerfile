FROM ubuntu:16.04

# Install geth client
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install software-properties-common -y && \
    add-apt-repository -y ppa:ethereum/ethereum -y && \
    apt-get upgrade -y && \
    apt-get update -y && \
    apt-get install ethereum -y
# Install Ethereum Wallet GUI
RUN apt-get install wget && \
    wget https://github.com/ethereum/mist/releases/download/v0.9.3/Ethereum-Wallet-linux64-0-9-3.deb && \ 
    apt-get install gconf2 -y && \
    apt-get install libnotify4 -y && \
    apt-get install libappindicator1 -y && \
    apt-get install libxtst6 -y && \
    apt-get install libnss3 -y && \
    apt-get install libxss1 -y && \
    apt-get install libasound2 -y && \
    dpkg -i Ethereum-Wallet-linux64-0-9-3.deb

WORKDIR /app

COPY . .

ENTRYPOINT [ "tail", "-f", "/dev/null" ]