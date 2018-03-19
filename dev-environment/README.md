# Setup a Basic Ethereum Development Environment

I am experimenting with a various ways to setup an ethereum development environment.

## Start Docker Container MacOSX
1. Install XQuartz 
2. Launch XQuartz. Under XQuartz menu, select Preferences
3. Go to the security tab and ensure "Allow connections from network clients" is checked
4. Run xhost + ${hostname}
5. Run bash commands
```bash
export HOSTNAME=`hostname`
docker-compose up -d
```  

## Enter Docker Container
```bash
docker-compose exec ethereum-dev /bin/bash
xhost + ${hostname}
```

## Destroy Container and Images
```bash
docker-compose down --rmi all
```

## Run a Local Node
```bash
geth --datadir ./TestData \
    --identity "HelloWorld" \
    --rpc \
    --rpcport "8080" \
    --rpccorsdomain "*" \
    --port "30303" \
    --nodiscover \
    --rpcapi "db,eth,net,web3" \
    --maxpeers 0 \
    --network 24 \
    console
```

## Create an account
```bash
personal.newAccount()
```

## Mine Ethereum
```bash
geth attach ./TestData/geth.ipc
```

```bash
miner.setEtherbase("")
miner.start()
miner.stop()
```  