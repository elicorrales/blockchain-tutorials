# How To Set Up Your Dev Environment To Work Various Blockchains

## 1. (OPTIONAL) CHANGE YOUR PROMPT '$' TO BE NEXT LINE AT START SO YOU CAN SEE MORE CMDLINE  
DO:  
#edit .bashrc  
#find 'PS1'  
#go to end of line(s) and add '\n' to just before the '\$'  
#save/close .bashrc  
```
source ~/.bashrc
```

OUTPUT:
your '$' prompt should now be on 2nd line, at leftmost.  
```
YourUserName@YourHostName
$
```



## 1b. (OPTIONAL) INSTALL 'tree' # allows you to view dirs/files in tree format  
DO:
```
sudo apt install -y tree
```


## 2. RUST ASSUMES YOU HAVE COMPILER DEPENDENCIES. MAKE SURE YOU HAV GCC TOOLCHAIN  
DO:  
```
sudo apt install -y build-essential
```

You may need to also get ```cmake``` , ```clang``` (I forget exactly what you get with ```build-essential```.
```
sudo apt install -y cmake clang
```

## 3. INSTALL (OR MAYBE UPDATE?)  RUST  
### (WE ARE LEARNING RUST - AND IT BUILDS THE ON-CHAIN PROGRAMS - SMART CONTRACTS)  
DO:  
```
rustup
```

if not found then...

DO:  
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
```
rustup --version
```

OUTPUT:  
```
rustup 1.24.3 (ce5817a94 2021-05-31)
info: This is the version for the rustup toolchain manager, not the rustc compiler.
info: The currently active `rustc` version is `rustc 1.62.0 (a8314ef7d 2022-06-27)`
```  
  
OR:  
  
DO:  
```
rustup update
```

OUTPUT:  
```
info: syncing channel updates for 'stable-x86_64-unknown-linux-gnu'
info: checking for self-updates

  stable-x86_64-unknown-linux-gnu unchanged - rustc 1.62.0 (a8314ef7d 2022-06-27)

info: cleaning up downloads & tmp directories
```

## 4. INSTALL(UPDATE) NPM, NODEJS (NVM?)  
### THIS WILL BE USED FOR CLIENT-SIDE  
#### This way uses only NVM and assumes there is no global system-wide npm/node. 

These two scripts seem to be the same except that the 'creationix' script seems to have extra checks.  

DO:  
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash  
```
OR:  
```
curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash  
```

The https://github.com/creationix is from "Tim Caswell". He has pinned repository "nvm-sh/nvm" in the README of that repo, it refers to using the 1st one (above) or the "nvm-sh/nvm/" script.  

I think either one should work.  

OUTPUT: (lots of output, but it adds to your .bashrc):
```
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
```

DO:
```
source ~/.bashrc
```

DO:
```
nvm list-remote
```

OUTPUT: a long list of node versions. as of this date (2022-07-01) the latest is v18.4.0, and the LTS is v16.15.1.  


DO:
```
nvm install node
```

OUTPUT: (takes a bit)
```
Downloading and installing node v18.4.0...
Downloading https://nodejs.org/dist/v18.4.0/node-v18.4.0-linux-x64.tar.xz...
########################################################################################################################### 100.0%
Computing checksum with sha256sum
Checksums matched!
Now using node v18.4.0 (npm v8.12.1)
Creating default alias: default -> node (-> v18.4.0)
```
It installs latest node AND npm.  
<br/>

DO:  
```
node --version  
```

DO:  
```
npm --version  
```
<br/>
