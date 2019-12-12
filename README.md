# creating-a-blockchain-network

About my Network: The network name is norolemodelz and the chain ID is 6969, blocktime is deafult setting.

In order to connect to my network you must open up your wallet in my crypto then type in norolemodelz for network name, enter the chain ID: 6969, Make sure to connect to the ETH network. For URL enter http://127.0.0.1:8545/ . Make sure you use http and not https and put the slash at the end.





## How to create a testnet blockchain for yourself

## Step 1 - Create a wallet on MyCrypto

## Step 2 - go to https://geth.ethereum.org/downloads/ and download geth&tools

## Step 3 - Rename geth&tools folder to blockchain-tools

## Step 4 - Through your terminal within blockchain-tools folder run puppeth like so: ./puppeth

## Step 5 - Create your network name

## Step 6 - Type 2 to pick the Configure new genesis option, then 1 to Create new genesis from scratch

## Step 7 - Type 1 to choose Proof of Work and continue

## Step 8 - Copy and paste an address from your Ethereum wallet in MyCrypto, without the 0x prefix.

## Step 9 - Once you paste an address and hit enter, hit enter again on the blank 0x address to continue the prompt.

## Step 10 - Continue with the default option for the prompt that asks Should the precompile-addresses (0x1 .. 0xff) be pre-funded with 1 wei? by hitting enter again, until you reach the Chain ID prompt.

## Step 11 - Come up with a number to use as a chain ID (e.g. 333) type it, then hit enter.

## Awesome! Your genesis configuration is stored in your local home directory.


## Step 12 - First, export your genesis configuration into a yournetworkname.json file as follows:

## Step 13 - In the puppeth prompt, navigate to the Manage existing genesis by typing 2 and hitting enter.

## You may have to type your network name again first if you're launching puppeth fresh.

## Step 13 - Then, type 2 again to choose the Export genesis configurations option, and continue with the default (current) directory by hitting enter:

## Exit puppeth by using the Ctrl+C keys combination.



## Step 14 - Create the first node's data directory using the geth command and a couple of command line flags by running the following line in your terminal window (Git Bash in Windows):

## ./geth account new --datadir node1

## Step 15 - Repeat the same process for the second node by replacing the datadir parameter with the node2 folder.

## ./geth account new --datadir node2


## Step 16 - Initialize the first node, replacing yournetworkname.json with your own:

## ./geth init yournetworkname.json --datadir node1

## Step 17 - Run the same command for node2.

## ./geth init yournetworkname.json --datadir node2


## Time to start your blockchain network! Open a terminal window (Git Bash in Windows) navigate to your blockchain-tools folder and follow the next steps.

## Step 1 - Launch the first node into mining mode with the following command:

## ./geth --datadir node1 --mine --minerthreads 1

## Step 2 - Now you will launch the second node and configure it to let us talk to the chain via RPC.

## Scroll up in the terminal window where node1 is running, and copy the entire enode:// address (including the last @address:port segment) of the first node located in the Started P2P Networking line:

## Running in OS X 
## ./geth --datadir node2 --port 30304 --rpc --bootnodes "enode://<replace with node1 enode address>"

## Running in Windows
## ./geth --datadir node2 --port 30304 --rpc --bootnodes "enode://<replace with node1 enode address>" --ipcdisable

### Congrats! you have started yur chain.