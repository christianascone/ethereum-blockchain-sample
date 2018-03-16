# ethereum-blockchain-sample

## Requirements
- [go-ethereum](https://github.com/ethereum/go-ethereum/wiki/Building-Ethereum)

## Gettings started

Instantiate data directory with:
```bash
geth --datadir ./myDataDir init ./myGenesis.json
```
and start your node using:
```bash
geth --datadir ./myDataDir --networkid 1114 --ipcpath "~/Library/Ethereum/geth.ipc" console 2>> myEth.log
```

In case of problems with IPC (https://github.com/ethereum/go-ethereum/issues/13861#issuecomment-291791077), start it with:
```bash
geth --datadir ./myDataDir --networkid 1114 --ipcdisable console 2>> myEth.log
```

## Account creation

In geth Javascript console of started node, type:
```bash
personal.newAccount("<YOUR_PASSPHRASE>")
```

## References
- https://medium.com/mercuryprotocol/how-to-create-your-own-private-ethereum-blockchain-dad6af82fc9f
- https://medium.com/@mvmurthy/full-stack-hello-world-voting-ethereum-dapp-tutorial-part-1-40d2d0d807c2
- https://blockgeeks.com/guides/ethereum/
- https://myetherwallet.github.io/knowledge-base/networks/run-your-own-node-with-myetherwallet.html