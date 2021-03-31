# walletlib
![PyPI - Python Version](https://img.shields.io/badge/python-3.6%20%7C%203.7%20%7C%203.8-blue)



Unified interface to programmatically open and extract data from cryptocurrency wallet backup files

## Quick Start
This module requires Python 3.6+

```bash
$ pip install walletlib
```
A convenient cli script is available after installation.
```bash
$ python -m dumpwallet wallet.dat -o output.txt
```
or
```bash
$ dumpwallet wallet.dat -o output.txt
$ dumpwallet wallet-protobuf -o output.txt --keys
```


## Features
- Automatic reading of version byte and WIF prefix from default keys
- Dumping just keys or all data
- Read only access of wallet files

## Installation
The simplest way to install walletlib is using pip.
```bash
$ pip install walletlib
```
You can also clone this repo and then run
```bash
$ python setup.py install
```
## Usage
```python
import walletlib

wallet = walletlib.Walletdat.load("wallet.dat")
wallet.parse(passphrase="password")
wallet.dump_all(filepath="output.txt")
wallet.dump_keys(filepath="output_keys.txt")

```
Bitcoinj wallets:

```python
import walletlib

wallet = walletlib.ProtobufWallet.load("wallet-protobuf")
wallet.parse()
wallet.dump_all(filepath="output.txt")
wallet.dump_keys(filepath="output_keys.txt")
```

## Roadmap
- [x] wallet.dat
  - [x] Encrypted keys
  - [x] p2pkh Wallets
  - [ ] Bech32 wallets
- [x] Bitcoinj/Dogecoinj/Altcoinj wallets
  - [x] Open unencrypted wallet-protobuf/multibit .wallet files
  - [ ] Decrypt encrypted wallets
- [ ] Coinomi protobuf wallets
- [ ] Blockchain.com wallet.aes.json
