# ethereum-blockchain-sample

## Requirements
- [go-ethereum](https://github.com/ethereum/go-ethereum/wiki/Building-Ethereum)

## Gettings started

Go inside `my-eth-chain`
```bash
cd my-eth-chain
```

This step can be repeated for every node you want to start.
You must assure to use a different `datadir` for every node.

Instantiate data directory with:
```bash
geth --datadir datadir/myDataDir init ./myGenesis.json
```
and start your node using:
```bash
geth --datadir datadir/myDataDir --networkid 1114 --port 0 --ipcpath "~/Library/Ethereum/geth.ipc" console 2>> logs/myDataDir.log
```

In case of problems with IPC (https://github.com/ethereum/go-ethereum/issues/13861#issuecomment-291791077), start it with:
```bash
geth --datadir datadir/myDataDir --networkid 1114 --ipcdisable console 2>> logs/myDataDir.log
```

## Account

### Creation

In geth Javascript console of started node, type:
```bash
personal.newAccount("<YOUR_PASSPHRASE>")
```

### Set default

You can check default account typing:
```bash
eth.coinbase
```

It should show the same address obtained during account creation.
Otherwise, you can set it with:
```bash
miner.setEtherbase(web3.eth.accounts[0])
```

### Mining

Check your current user's balance
```bash
eth.getBalance(eth.coinbase)
```

In order to start mining
```bash
miner.start()
```
Note that this will throw an exception if no account is set.

Mining will log in your node's log file, and after a while you can check how your balance grows.

Finally you can stop it
```bash
miner.start()
```

## References
- https://medium.com/mercuryprotocol/how-to-create-your-own-private-ethereum-blockchain-dad6af82fc9f
- https://medium.com/@mvmurthy/full-stack-hello-world-voting-ethereum-dapp-tutorial-part-1-40d2d0d807c2
- https://blockgeeks.com/guides/ethereum/
- https://myetherwallet.github.io/knowledge-base/networks/run-your-own-node-with-myetherwallet.html