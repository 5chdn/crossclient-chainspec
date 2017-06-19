# CrossClient chainspec and genesis

Templates for Parity chainspec and Geth genesis - both compatible for a cross-client development network.

- Engine: Ethash PoW
- Network ID: 0x539 (1337)

Templated and stripped from the inital ropsten chain spec for both clients.

# Usage

Geth:

    $ geth init --datadir ~/.ethereum/crossclient geth.json
    $ geth --datadir ~/.ethereum/crossclient --networkid 1337 --port 31333 --rpcport 8538

Parity:

    $ parity --chain parity.json --port 31337 --jsonrpc-port 8539
     
# Hints

You might want to enable a miner thread on geth to keep blocks rolling in.

    $ geth --datadir ~/.ethereum/crossclient --networkid 1337 --port 31333 --rpcport 8538 --mine --minerthreads 1 --etherbase 0x976d35d3e3a338ceef3f25a9af8ada2f0a72c178

You can simply glue them together by handing over their respective enode.

    $ parity --chain parity.json --port 31337 --jsonrpc-port 8539 --bootnodes enode://f0e38f26f95c722b4ab27ac8dfbd214280220e1768a19027309f6d12af749cca02fcbbf859dc84b3af05f98de433f78684d4d308c2d52aa357d5f4e0ae08cb4f@127.0.0.1:31333
    
Or

    $ geth --datadir ~/.ethereum/crossclient --networkid 1337 --port 31333 --rpcport 8538 --mine --minerthreads 1 --etherbase 0x976d35d3e3a338ceef3f25a9af8ada2f0a72c178 --bootnodes enode://43ad28a7bfe232a4aa56624659db9aca9fb5167cad04ec56b489cadb9eff39ef241be526dacfc7951f252adbfb99b3eb864c3743a576bc1d59b0101994fa08d6@127.0.0.1:31337

Or using parity's `--reserved-peers peers.txt` option.

# See also

- Translate Geth to Parity Ethereum chain spec: https://github.com/keorn/parity-spec

# Credits

Thanks to all the users who kept asking how to do this.
