# How to use the Web3.js interface with Mantis client

## Introduction  
Learn how to use the web3 Javascript interface with the ETC Mantis client for application development.  
Walk through an example program that demonstrates some sample API calls.  
  
The Ethereum web3.js interface provides many documented API calls.  
The interface gives you full access to the local copy of the Ethereum Classic blockchain. You can create a website or client that interacts with the decentralized blockchain ledger.   
The web3.js interface is also used to develop smart contracts in the Solidity language.  
  
In this example, we'll set up a simple Javascript program to demonstrate the concept.  
See the end of this page for more information.  
# Running a sample application
Follow these steps to create and run a web3.js application that checks the synchronization status and displays the contents of the latest block.
## Set up the file structure
1. Make sure [node.js](https://nodejs.org/en/download/) and [Yarn](https://classic.yarnpkg.com/lang/en/) are installed. There are plenty of instructional posts on the internet, so there is no need to repeat all that here.  
2.  Create a new directory (its name does not matter) and initialize it. You can use npm or Yarn. Both npm and Yarn create the file `package.json`. At the same time, Yarn also creates `yarn.lock`, and npm creates `package-lock.json`. From here on, we will demonstrate using Yarn.  
On some systems, you are prompted for information that will be added to `package.json`. This information will be updated later when the web3 libraries are installed.  You can just take the default values.    
On Windows:  
 ```
    c:\>mkdir mantis-web3-example
    c:\>cd mantis-web3-example
    c:\mantis-web3-example>yarn init
    yarn init v1.22.10
    question name (user): mantis-web3-example
    question version (1.0.0):
    question description: Sample web3.js interface to Mantis
    question entry point (index.js):
    question repository url: http://localhost:2000
    question author: mantis.io
    question license (MIT):
    question private: n
    success Saved package.json
    Done in 151.31s.
    c:\mantis-web3-example>   

On Linux:   

```
    user@computername:~$ mkdir mantis-web3-example
    user@computername:~$ cd mantis-web3-example
    user@computername:~/mantis-web3-example$ yarn init
    {
        name: 'user'
    }
    user@computername:~/mantis-web3-example$ 
```
On macOS:   

```
    computerName:~user$ mkdir mantis-web3-example
    computerName:~user$ cd mantis-web3-example
    computerName:~user$ yarn init
    yarn init v1.22.10
    question name (Blockchain): mantis-web3-example
    question version (1.0.0): 1.0.0
    question description: Mantis web3 example
    question entry point (index.js):
    question repository url:
    question author:
    question license (MIT):
    question private:
    success Saved package.json
    :sparkles:  Done in 56.13s.

```
## Install the web3.js libraries
The web3.js libraries are available as an npm package, so you can use npm or Yarn to install them in the directory you just created.  
To install using Yarn:   
```
yarn add web3
```
## Check the contents of package.json
Compare your copy of `package.json` with this example. Make sure all the keys and values are there.

```
    {
        "name": "mantis-web3-example",
        "version": "1.0.0",
        "main": "index.js",
        "license": "MIT",
        "dependencies": {
            "web3": "^1.3.6"
        },
        "scripts": {
            "start": "node index.js"
        }
    }
```
## Write the Javascript
On all systems, create a file called `index.js` in the same directory as `package.json`. Edit it so that it looks like this:  
```
    1 const Web3 = require('web3')
    2 
    3 let web3 = new Web3(new Web3.providers.HttpProvider("http://localhost:8546"))
    4 
    5 web3.eth.isSyncing()
    6   .then((response) => {
    7     console.log('SYNC STATE:')
    8     console.log(response)
    9   })
    10   .catch((error) => console.error(error))
    11
    12
    13
    14 web3.eth.getBlock('latest')
    15   .then((response) => {
    16     console.log('LATEST BLOCK:')
    17    console.log(response)
    18 })
    19   .catch((error) => console.error(error))
    20
```
`Index.js` is the Javascript program.  
Line 1 references the web3.js libraries.    
In line 3, we establish a connection between this program and the Mantis client.  
In the block beginning at line 5, we query the client to discover the state of synchronization of the local client with the shared blockchain ledger.   
In the block beginning at line 14, we retrieve the latest block that the client has downloaded so far.
## Test the program
Go to the Mantis installation folder and start the Mantis client.  
In the example, we are using the Sagano testnet.
For more information on starting the client, see the [Mantis configuration page](/how-tos/how-to-configure-mantis).
```
    mantis-launcher sagano
```
Go to the directory you have created and run the sample program.
```
    npm start
```
The result should be similar to this:  
```
    C:\>
    C:\>cd mantis-web3-example

    C:\mantis-web3-example>npm start

    > mantis-web3-example@1.0.0 start
    > node index.js

    LATEST BLOCK:
    {
    number: 18927,
    hash: '0xc3b738e5230ea385678e798c44bed3a3e180ab77ff9fbba83957d2998dc56ba6',
    parentHash: '0xc7e1b5b5af26534f509fa08a0d689b1d5a42b6623b83527926488d94f820642a',
    nonce: '0xb02bc71c3c8453e5',
    sha3Uncles: '0x1dcc4de8dec75d7aab85b567b6ccd41ad312451b948a7413f0a142fd40d49347',
    logsBloom: '0x00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000',
    transactionsRoot: '0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421',
    stateRoot: '0xf4b402fca95bd9791b2a320c61a70666da9655fb49bb61ddbce8d32165e830ed',
    receiptsRoot: '0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421',
    miner: '0x1Ff7FC39F7F4DC79c5867B9514d0e42607741384',
    difficulty: '1746526',
    totalDifficulty: '29856771326',
    lastCheckpointNumber: '0x0',
    extraData: '0x6d616e74697362713db2265723a81bc76235c7b0dd283f925151025dc87276e4f3d8d9b88a6a3a0bdaafcc872ce2dac7ff5e6ec03fdce58d98f59c08a2e0b545a51a69d6632b1c',
    size: 586,
    gasLimit: 8000000,
    gasUsed: 0,
    timestamp: 1621705043,
    transactions: [],
    uncles: [],
    signature: '62713db2265723a81bc76235c7b0dd283f925151025dc87276e4f3d8d9b88a6a3a0bdaafcc872ce2dac7ff5e6ec03fdce58d98f59c08a2e0b545a51a69d6632b1c',
    signer: 'd8a010f019db37dcaf2e1fb98d4fcbf1f57dbd7e2a7f065e92fbe77dca8b9120d6e79f1617e98fa6134e6af8858ac8f3735b1e70a5708eb14f228080356eb0a7'
    }
    SYNC STATE:
    {
    startingBlock: 0,
    currentBlock: 18900,
    highestBlock: 165279,
    knownStates: 0,
    pulledStates: 0
    }

    C:\mantis-web3-example>
```
We obtained the above results on Windows 10, 64-bit, version 20h2.
## Observe the results
Notice that the web3 calls are asynchronous, so the results do not necessarily appear in the same order as you have written the method calls.  
When we ran our test program, the client had started the synchronization process, but it had a long way to go. Your results will probably differ from these.  
In the test execution, the last block call completes before the sync state call, even though the current block in the sync state result is lower than the block number returned by the latest block call.  
# More information
For more information about the web3.js API, see the [Read The Docs page](https://web3js.readthedocs.io/en/v1.2.4/web3.html).
