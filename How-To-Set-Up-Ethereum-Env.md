
# How To Set Up Your Dev Environment To Work With Solana  
<br/>  

### First, [Some General Setup](How-To-Set-Up-Env-Common.md)  
<br/>  
  
NOTE: We are going to attempt to try/use several different local Ethereum blockchain networks.  
<br/>  
  
## 5a. (ATTEMPT) INSTALL GANACHE - A LOCAL DEV BLOCKCHAIN  

Ganache is an Ethereum simulator that makes developing Ethereum applications faster, easier, and safer.  
  
DO:  
```
npm install ganache --global  
```
  
OUTPUT:  
The installation seems to fail....but perhaps not.
```
IamDeveloper@SoftwareDevelopUbuntu2004
~
$ npm install -g ganache
npm ERR! code ELOOP
npm ERR! syscall spawn
npm ERR! errno -40
npm ERR! spawn ELOOP
npm ERR! code ELOOP
npm ERR! syscall spawn
npm ERR! errno -40
npm ERR! spawn ELOOP
npm ERR! code ELOOP
npm ERR! syscall spawn
npm ERR! errno -40
(etc....)
```

It could be that ```ganache``` is the UI which would probably cause problems installing it in WSL Ubuntu.  
  
DO:
```
npm install ganache-cli --global (and optionally --force if you previously tried to install the above ganache).  
```

OUTPUT:
```
IamDeveloper@SoftwareDevelopUbuntu2004
~
$ npm install -g ganache-cli --force
npm WARN using --force Recommended protections disabled.
npm WARN deprecated ganache-cli@6.12.2: ganache-cli is now ganache; visit https://trfl.io/g7 for details
npm ERR! code ELOOP
npm ERR! syscall spawn
npm ERR! errno -40
npm ERR! spawn ELOOP
npm ERR! code ELOOP
npm ERR! syscall spawn
npm ERR! errno -40
npm ERR! spawn ELOOP

npm ERR! A complete log of this run can be found in:
npm ERR!     /home/IamDeveloper/.npm/_logs/2022-07-22T02_00_11_652Z-debug-0.log
IamDeveloper@SoftwareDevelopUbuntu2004
$
```

It would seem that it failed but perhaps not.  
  
DO:  
```
ganache-cli --version
```
OR:
```
ganache-cli --help
```
  
<br/>
More testing; try the following:  
  
DO:  
```
ganache
```

OUTPUT:  
```
ganache v7.3.2 (@ganache/cli: 0.4.2, @ganache/core: 0.4.2)
Starting RPC server

Available Accounts
==================
(0) 0x98aA537d117Aa50612BDE29deE3461987a91E4E0 (1000 ETH)
(1) 0xd1886628b691C37b5b1178146cd224Bdcb233D66 (1000 ETH)
(2) 0x0FeA422e54940b95CD7647d598Fd591723ba4896 (1000 ETH)
(3) 0x259A72faa93d018d6CaCdEc08D5fD84f5206Fc36 (1000 ETH)
(4) 0x1065bab6bac3105ea60D9B03B1B0541040Ee8C68 (1000 ETH)
(5) 0x0156b4c8629b9A730AFF4Bdf283d14E192C2f50e (1000 ETH)
(6) 0x3219E207d4C3a048ae32f8d7A22b2790f1A736b9 (1000 ETH)
(7) 0xF311106F14D5AC029d1399ba45352919DD422b04 (1000 ETH)
(8) 0x68f25b97C27416Bc28734FdD16630aA5edECf5fA (1000 ETH)
(9) 0x6169A172175dBFbb76C3c2564edaE185c9b58b20 (1000 ETH)

Private Keys
==================
(0) 0x8398e6572238c1653c79b25ec89b75a0e5e6402bc410a3cf1e28a922c214a877
(1) 0xcd9abe12b600173d02a228954722f785a504c9ec653c02825be2b6dc194557c5
(2) 0xea35950af5c2a725ea3544db3f7788d81864bf94fa85dfc78c90e044120a82d2
(3) 0xd8bf9e53d008a0ea628e033961fd109697ad104488b1b758458de00979c5ae79
(4) 0xc5b01d9d01586c6abc702a311b42ddc9806890c3e8285bca37d27ec53239b4fb
(5) 0xe78e7ff77b19a48568aed27cad572f00ae3a2a451af55aed05a1f9a0e23e405f
(6) 0x2ad6d267c7655da0f636aa06fc4d84285c36905391902d5b6ecf51673991bb8b
(7) 0xd2f35e521273322e8d02d2fb77eab34c34906552f5b204679fcf79ca683f46c8
(8) 0x68df86f811c3f76b4e001b7b62135029cada53f0b37f9e3c83b0540a2b303908
(9) 0xcc1fc5cc2fc3be231dc92af0821c6f7ae983fea1c1b33832d07a9ffbbde57ee6

HD Wallet
==================
Mnemonic:      carbon top address spot bright supply typical display grass next eyebrow siege
Base HD Path:  m/44'/60'/0'/0/{account_index}

Default Gas Price
==================
2000000000

BlockGas Limit
==================
30000000

Call Gas Limit
==================
50000000

Chain Id
==================
1337

RPC Listening on 127.0.0.1:8545
```


That seems ok.  
  
Now try the ```-cli```.  
DO:  
```
ganache-cli
```

OUTPUT:  
```
Error: error:0308010C:digital envelope routines::unsupported
    at new Hash (node:internal/crypto/hash:67:19)
    at Object.createHash (node:crypto:133:10)
    at p (/home/IamDeveloper/.nvm/versions/node/v18.4.0/lib/node_modules/ganache-cli/build/ganache-core.node.cli.js:55:527949)
    at b.set (/home/IamDeveloper/.nvm/versions/node/v18.4.0/lib/node_modules/ganache-cli/build/ganache-core.node.cli.js:55:528548)
    at Function.b.fromMasterSeed (/home/IamDeveloper/.nvm/versions/node/v18.4.0/lib/node_modules/ganache-cli/build/ganache-core.node.cli.js:55:530917)
    at F
    (etc)
```
<br/>
<br/>
  
## 5b. (ATTEMPT) INSTALL HARDHAT - A LOCAL DEV BLOCKCHAIN  

Hardhat is an Ethereum development environment for professionals. It facilitates performing frequent tasks, such as running tests, automatically checking code for mistakes or interacting with a smart contract.   
  
DO:  
```
npm install hardhat --global  
```
  
OUTPUT:  
The installation seems to fail....but perhaps not.
```
npm ERR! code ELOOP
npm ERR! syscall spawn
npm ERR! errno -40
npm ERR! spawn ELOOP
npm ERR! code ELOOP
npm ERR! syscall spawn
npm ERR! errno -40
npm ERR! spawn ELOOP
(etc)
```
  
DO:  
```
IamDeveloper@SoftwareDevelopUbuntu2004
~
$ hardhat
888    888                      888 888               888
888    888                      888 888               888
888    888                      888 888               888
8888888888  8888b.  888d888 .d88888 88888b.   8888b.  888888
888    888     "88b 888P"  d88" 888 888 "88b     "88b 888
888    888 .d888888 888    888  888 888  888 .d888888 888
888    888 888  888 888    Y88b 888 888  888 888  888 Y88b.
888    888 "Y888888 888     "Y88888 888  888 "Y888888  "Y888

Welcome to Hardhat v2.10.1

? What do you want to do? …
▸ Create a JavaScript project
  Create a TypeScript project
  Create an empty hardhat.config.js
  Quit 
```
  
  

















## 6. CREATE A SOFTWARE PROJECT DIRECTORY  
### These are just suggested, not required to do exactly like this below.
DO:  
```
mkdir -p MySoftwareProjects/blockchain/rust/rust-solana-blockchain-projects
```
```
cd MySoftwareProjects/blockchain/rust/rust-solana-blockchain-projects
```
<br/>  


## 7. CREATE A TOP-LEVEL PROJECT && CLIENT DIR
### THIS WILL BE FOR CLIENT, FOR RUST ON-CHAIN PROGRAM, FOR WALLET, AND MORE
#### While in the "rust-solana-blockchain-projects" directory, do...  

DO:  
```
mkdir -p my-first-solana-project/my-first-client  
mkdir -p my-first-solana-project/my-first-wallet  
```
<br/>

## 8. CREATE A FILE SYSTEM WALLET
### While at top-level project dir: my-first-solana-project, do...  
DO:  
```
solana-keygen new --outfile my-first-wallet/my-keypair.json
```

OUTPUT:  
```
Generating a new keypair

For added security, enter a BIP39 passphrase

NOTE! This passphrase improves security of the recovery seed phrase NOT the
keypair file itself, which is stored as insecure plain text

BIP39 Passphrase (empty for none):

Wrote new keypair to my-first-wallet/my-keypair.json
================================================================================
pubkey: 2tJTBeAGw982yew93Dd6ewNmr2tvbvRF6VTfHk8XtERV
================================================================================
Save this seed phrase and your BIP39 passphrase to recover your new keypair:
crystal couple nominee ski below bracket adult gesture arrange cousin wheat this
================================================================================
```
<br/>

TO VIEW PUBKEY, DO:  
```
solana-keygen pubkey my-first-wallet/my-keypair.json
```

OUTPUT: (just an example; yours will differ)
```
2tJTBeAGw982yew93Dd6ewNmr2tvbvRF6VTfHk8XtERV
```


## 9. SETUP CONFIG FOR SOLANA
DO: (let's see what config says it has)
solana config get
OUTPUT:
Config File: /home/IamDeveloper/.config/solana/cli/config.yml
RPC URL: https://api.mainnet-beta.solana.com
WebSocket URL: wss://api.mainnet-beta.solana.com/ (computed)
Keypair Path: /home/IamDeveloper/.config/solana/id.json
Commitment: confirmed


Let's change URL.

DO:
solana config set --url localhost

OUTPUT:
Config File: /home/IamDeveloper/.config/solana/cli/config.yml
RPC URL: http://localhost:8899
WebSocket URL: ws://localhost:8900/ (computed)
Keypair Path: /home/IamDeveloper/.config/solana/id.json
Commitment: confirmed


Let's point to our new wallet.

DO:
solana config set --keypair ~/MySoftwareProjects/blockchain/rust/rust-solana-blockchain-projects/my-first-solana-project/my-first-wallet/my-keypair.json

OUTPUT:
Config File: /home/IamDeveloper/.config/solana/cli/config.yml
RPC URL: http://localhost:8899
WebSocket URL: ws://localhost:8900/ (computed)
Keypair Path: /home/IamDeveloper/MySoftwareProjects/blockchain/rust/rust-solana-blockchain-projects/my-first-solana-project/my-first-wallet/my-keypair.json
Commitment: confirmed












## 10. START UP SINGLE-NODE CLUSTER (TEST OUT CONFIG, WALLET, etc)
### in another terminal, not in the one where we are at our
top-level project dir... we are going to leave this running(mostly)

DO:
solana-test-validator
OUTPUT:
Ledger location: test-ledger
Log: test-ledger/validator.log
⠓ Initializing...
⠈ Initializing...
Identity: 5tskYxsQw3NxEqRc6mNQU58EMv8b3RES24GZbgkdD7kv
Genesis Hash: FyCy8ZcGtazj9FS6gutqXACCvSpSSCSceUXjLBqEGnWW
Version: 1.10.29
Shred Version: 20316
Gossip Address: 127.0.0.1:1024
TPU Address: 127.0.0.1:1027
JSON RPC URL: http://127.0.0.1:8899
⠖ 00:00:53 | Processed Slot: 125 | Confirmed Slot: 125 | Finalized Slot: 93 | Full Snapshot Slot: - | Incremental Snapshot

(if you do not see any message that 'No wallet available.' then we are ok.)




## 11. MONITOR LOG(OUTPUT) OF TEST VALIDATOR
(open yet a 3rd terminal window)
DO:
solana logs
(leave running)




## 12. TEST ACCOUNT - WE ARE AGAIN AT OUR TOP-LEVEL PROJECT DIRECTORY
(find the public key string that you saw when you generated the new wallet - scroll up til you find it - copy it)  

DO:
```
solana account <pubkey here>
```

OUTPUT:
```
Public Key: 2tJTBeAGw982yew93Dd6ewNmr2tvbvRF6VTfHk8XtERV
Balance: 500000000 SOL
Owner: 11111111111111111111111111111111
Executable: false
Rent Epoch: 0
```

## 13. CREATE NEW CLIENT JS
(in our client project dir: my-first-client)

DO:  
```
touch client.js
```


## 14. INSTALL/CONFIG WEB3.JS
We depend on @solana/web3.js  to be able to interact with Solana on-chain programs.

```
npm search <term> (example: web3  or @solana)
npm search @solana
npm search web3

npm install -g @solana/web3.js
```
```  
###################################################################
#this is so that global npm packages are also available to projects
###################################################################
export NODE_PATH=$(npm root -g)
```



```
netstat -a

sudo apt install -y net-tools

npm search <term> (example: web3  or @solana)


export NODE_PATH=$(npm root -g)

npm: npm install @solana/web3.js
```





## 16. 
DO:
cd my-first-on-chain-program-bin-plus-lib/





8. CREATE A RUST PROJECT (ON-CHAIN PROGRAM)(SMART CONTRACT)
=================================================================
DO:
cargo new my-first-on-chain-program-bin-lib --bin --vcs none
DO:
tree
OUTPUT:
$ tree
.
├── Cargo.toml
└── src
    └── main.rs

1 directory, 2 files

DO:
touch src/lib.rs.

DO:
tree
OUTPUT:
$ tree
.
├── Cargo.toml
└── src
    ├── lib.rs
    └── main.rs

1 directory, 3 files


DO:
 cargo build-bpf
OUTPUT:
Note: bpf-program crate does not contain a cdylib target
BPF SDK: /home/EliezerC/.local/share/solana/install/releases/1.10.29/solana-release/bin/sdk/bpf
cargo-build-bpf child: rustup toolchain list -v
cargo-build-bpf child: cargo +bpf build --target bpfel-unknown-unknown --release
   Compiling bpf-program v0.1.0 (/home/EliezerC/MySoftwareProjects/blockchain/rust/solana/bpf-program)
    Finished release [optimized] target(s) in 0.13s

DO:
file target/bpfel-unknown-unknown/release/bpf-program
OUTPUT:
target/bpfel-unknown-unknown/release/bpf-program: ELF 64-bit LSB pie executable, eBPF, version 1 (SYSV), dynamically linked, not stripped

DO:(attempt run)
 ./target/bpfel-unknown-unknown/release/bpf-program
OUTPUT:
-bash: ./target/bpfel-unknown-unknown/release/bpf-program: cannot execute binary file: Exec format error







