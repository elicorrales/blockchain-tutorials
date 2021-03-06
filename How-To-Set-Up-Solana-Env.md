# How To Set Up Your Dev Environment To Work With Solana  
<br/>  

### First, [Some General Setup](How-To-Set-Up-Env-Common.md)  
<br/>  

## 5. INSTALL SOLANA TOOLSET
For your edification,
DO:  
```
cargo --list | grep bpf  
```

OUTPUT:  
nothing - you should not see any 'bpf' related commands show up.  
  
DO:  
Chec [this Solana install page](https://docs.solana.com/cli/install-solana-cli-tools) for the latest install version.  
Currently it is version v1.10.31.  
Adjust the install one-line command below accordingly.  
```
sh -c "$(curl -sSfL https://release.solana.com/v1.10.30/install)"
```

OUTPUT:  
```
downloading v1.10.29 installer
  ✨ 1.10.29 initialized
Adding
export PATH="/home/developer/.local/share/solana/install/active_release/bin:$PATH" to /home/developer/.profile

Close and reopen your terminal to apply the PATH changes or run the following in your existing shell:

export PATH="/home/developer/.local/share/solana/install/active_release/bin:$PATH"
```

NOTE: do an 'ls -lta' and you should see that the above installation might have added a '.profile' to your home directory.  
If you cat that file, at bottom you should see that it already added the above 'export PATH..blah...blah.. solana..blah..blah.  

DO:  
```
source ~/.profile #it will also run .bashrc
```
  
DO:  
```
cargo --list | grep bpf
```

OUTPUT:
```
    build-bpf
    test-bpf
```

The installation of solana tools also adds new bpf commands to cargo.  
  
<br/>


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







