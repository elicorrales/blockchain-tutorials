# Decentralized Application (dApp) Blockchain Tutorials  
These video-based(youtube) tutorials attempt to choose something somewhat challenging but at the same time go at a slow pace and try to go over basics.  
<br/>
The approach is to:
- constantly ask "what, why, how"
- try the most minimalist code unless it doesn't make sense to
- use the "onion" - sometimes we go deep into one topic, and at other times it's very shallow but we cover various topics

## Series I - NEAR Blockchain Tutorial (Deploying WASM)

Between Part 1 and 2, we arrive at the conclusion to focus on Rust, and start with WASM blockchains.  

[The Re-make Of An Old Programmer - Part 1](https://www.youtube.com/watch?v=EVEuPNYoaD4&list=PLNKa8O7lX-w5Myr19mn-dxtSphB5X1jUW&index=1)  
This video delves into why I chose to learn decentralized blockchain programming (dApps)

[Remaking An Old Programmer - Part 2: Why I chose Rust](https://www.youtube.com/watch?v=o0gSufEy35o&list=PLNKa8O7lX-w5Myr19mn-dxtSphB5X1jUW&index=2)

[Remake Old Programmer - Part 3: First Rust WASM Tutorial - Setup](https://www.youtube.com/watch?v=8gPVbUc5Zos&list=PLNKa8O7lX-w5Myr19mn-dxtSphB5X1jUW&index=3)  
We come across an online tutorial from [NEAR](https://near.org/) and use that as our jumping-off point.  

Once we'v gotten our local development environment set up, we work on our "smart contract" program that we will deploy and run on a NEAR testnet blockchain.  
<br/>
<br/>
[Remake Old Programmer - Part 4: Rust Basics - 1](https://www.youtube.com/watch?v=XU-CxEBY7Ak&list=PLNKa8O7lX-w5Myr19mn-dxtSphB5X1jUW&index=4)

[Remake Old Programmer - Part 5: Rust Basics - 2: Struct, Mut](https://www.youtube.com/watch?v=b2iRUA1RcOI&list=PLNKa8O7lX-w5Myr19mn-dxtSphB5X1jUW&index=5)

[Remake Old Programmer - Part 6: Rust: Build WASM Smart Contract - Deploy To Blockchain](https://www.youtube.com/watch?v=EvK7UDt8lao&list=PLNKa8O7lX-w5Myr19mn-dxtSphB5X1jUW&index=6)

[Remake Old Programmer-Part 7: Rust Crates,Import,Use Macros,Deploy Bin Vs Lib, WASI, Be Careful](https://www.youtube.com/watch?v=6rRMuU36YOk&list=PLNKa8O7lX-w5Myr19mn-dxtSphB5X1jUW&index=7)
<br/>
<br/>
[Here](https://github.com/elicorrales/rust-near-blockchain) is the code as we conclude this series.  
<br/>
Note that in this first series, we use only the "near-cli" tool to deploy and interact with our on-chain(deployed) smart-contract program.  
We don't worry or are aware of what "magic" takes place that helps us interact with our deployed program.  
<br/>
In the next series we delve into the what/how of command-line client required to interact with a blockchain program.
<br/>
<br/>
<br/>
## Series II - Solana Blockchain Tutorial (Deploying eBPF)
<br/>

This series differs from the NEAR blockchain series in several ways:
- We are deploying eBPF programs, not WASM
- We deploy to a local test blockchain
- We also delve into writing a command-line Node.js Javascript client
- We use VSCode to debug

<br/>
Hopefully most of the youtube titles are self-explanatory.  
<br/>
<br/>

#### Working on a ["How-To Set Up Your Dev Environment"](How-To-Set-Up-Env.md)  
<br/>

[Blockchain Programmer - Part 1: Intro To Solana, Account, Keypair, Test Validator](https://www.youtube.com/watch?v=HiTJwCKzuD8&list=PLNKa8O7lX-w5nEQjNbFRQV7e3Sd4qLi44&index=1)  

[Blockchain Programmer - Part 2: How To Set Up Multiple Solana Test Validators](https://www.youtube.com/watch?v=phdmzafMvYc&list=PLNKa8O7lX-w5nEQjNbFRQV7e3Sd4qLi44&index=2)  

[Blockchain Programmer - Part 3: How to Set Up Multiple WSL Ubuntu Environments](https://www.youtube.com/watch?v=9hssNB5LiVE&list=PLNKa8O7lX-w5nEQjNbFRQV7e3Sd4qLi44&index=3)  

[Blockchain Programmer - Part 4: We Start Composing A Solana Node.js Cmd-Line Client](https://www.youtube.com/watch?v=wJIHjfpT82o&list=PLNKa8O7lX-w5nEQjNbFRQV7e3Sd4qLi44&index=4)  

[Blockchain Programmer - Part 5: Solana Node.js Client Interaction With Blockchain (Local Test Validator)](https://www.youtube.com/watch?v=XKvoilqT4Ps&list=PLNKa8O7lX-w5nEQjNbFRQV7e3Sd4qLi44&index=5)  

[Blockchain Programmer - Part 6: Initial Build Of A Solana Rust On-Chain Program](https://www.youtube.com/watch?v=JEZm4F1VLbk&list=PLNKa8O7lX-w5nEQjNbFRQV7e3Sd4qLi44&index=6)  

[Blockchain Programmer - Part 7: Deploy The Solana Rust On Chain Program](https://www.youtube.com/watch?v=rgJtW_FTXg8&list=PLNKa8O7lX-w5nEQjNbFRQV7e3Sd4qLi44&index=7)  

[Blockchain Programmer-Part 8: Setup VSCode With Windows and WSL](https://www.youtube.com/watch?v=rFqQJL8quTc&list=PLNKa8O7lX-w5nEQjNbFRQV7e3Sd4qLi44&index=8) 

[Blockchain Programmer-Part 9: How To Find Example Code Snippets To Learn Solana, Web3.js](https://www.youtube.com/watch?v=Dnc5qnZ0dMM&list=PLNKa8O7lX-w5nEQjNbFRQV7e3Sd4qLi44&index=9)  


[Blockchain Programmer-Part 10: Node.js Javascript Cmd-line Client Talks to Rust On-Chain Program](https://www.youtube.com/watch?v=jDOIdC58puE&list=PLNKa8O7lX-w5nEQjNbFRQV7e3Sd4qLi44&index=10)  
We finally have an initial success at getting our command-line client app to "tickle"(invoke) the "entry point" of our Rust on-chain program.  

[Here](https://github.com/elicorrales/my-first-solana-project-after-series-II-part-10) is the code as a result of arriving to Part 10.
<br/>
<br/>

[Blockchain Programmer-Part 11: Pass Data Client To On-Chain Rust Prog | Multi-Version Deployments](https://www.youtube.com/watch?v=wL6b4w-LNmA&list=PLNKa8O7lX-w5nEQjNbFRQV7e3Sd4qLi44&index=11)  

In this video we learn how to  
- display any data that is passed in from the client to the on-chain program
- control which program id (keypair) we wish to use when deploying an on-chain program
- deploy and run multiple versions of the program by which program id we use to invoke it  

[Here](https://github.com/elicorrales/my-first-solana-project-series-II-part-11) is the code from this part 11.  

Useful commands:
```
solana config get
```
The above line shows you what your local config has.  Two important values would be the URL (for this series -we are using ```localhost```) and the ```Keypair Path```.
  
<br/>

```
solana-test-validator  # keep this running in a terminal
```
I mostly run the above local validator in the current project directory.  It creates a directory ```test-validator```.  Make sure that your local config ```solana config get``` is pointing to the correct ```wallet```.  
I mostly run the local validator with the ```--reset``` flag - starts fresh every time. Means you'll have to re-deploy  your on-chain program AND you'll lose any accounts your client created.  
<br/>
```
solana logs # keep this running in another terminal
```
The above will display any output related to your on-chain deployed program, or certain command-line solana commands, such as ```deploy```.  
<br/>
```
solana program show --programs
```
The above line will let you know if your program(s) are currently deployed.  
<br/>

[Blockchain Programmer-Part 12: Rust: Init Arrays | Conv To String | Cmd-Line Args | If-Else | Match](https://www.youtube.com/watch?v=Vyqpr1WFs_0)  
[Here](https://github.com/elicorrales/my-first-solana-project-series-II-part-12) is the code from this part 12.  
<br/>  
  
[Blockchain Programmer-Part 13: Node.js Client Cmdline-Args to Solana On-Chain Program](https://www.youtube.com/watch?v=ZatpilAexak)  
[Here](https://github.com/elicorrales/my-first-solana-project-series-II-part-13) is the code from this part 13.  
<br/>
[Blockchain Programmer-Part 14: Node.js Client Cmd-line Args Keypair to Solana On-Chain Program](https://www.youtube.com/watch?v=PYulPZ1ngPA)  
[Here](https://github.com/elicorrales/my-first-solana-project-series-II-part-14) is the code from this part 14.  
<br/>  
[Blockchain Programmer-Part 15: Create Solana Account With Space For Persistent Custom Data](https://www.youtube.com/watch?v=CWO3BewK7MI)  
[Here](https://github.com/elicorrales/my-first-solana-project-series-II-part-15) is the code from this part 15.  
```
solana account <your account public key string here>
```
The above shows you information about a single account.  
<br/>
This one (below) might even be a better command. You get a list of accounts.  
```
solana largest-accounts
```
<br/>  
  
  
  
### Up next... Part 16... stay tuned.  

[]()  

[]()  

[]()  





