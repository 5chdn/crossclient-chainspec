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

# See also

- Translate Geth to Parity Ethereum chain spec: https://github.com/keorn/parity-spec

# Credits

Thanks to all the users who kept asking how to do this.
