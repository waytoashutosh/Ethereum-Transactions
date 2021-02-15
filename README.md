# Ethereum-Transactions


We are going to implement this using command line interface. For making
it more user friendly we could have created an HTML page that runs on a
local host.

**TLDR:**

We will create a private blockchain network of two accounts and carry
out mining and do some transactions between them for ethers.

**Steps to check transaction:**
0\. Change directory to FirstEthereum and follow the procedure.
1\. Launch a geth console.
2\. To check balance.
3\. Now we’ve got some ether in the first account, let’s send it to the
2nd account we created. The source account has to be unlocked before it
can send a transaction.
**Password for both account:** ***node1***
4\. Now transferring some ethers to account 2.
5\. The ethers wont be sent until a miners validates the transaction.
Since there are no other nodes on the network so we need to mine for it.
6\. Finally Stop the mining and check balance of account 2.

**Pre Requisite:**
1. c compiler
2. Install Go Ethereum (geth)

    sudo apt-get install software-properties-common
    sudo add-apt-repository -y ppa:ethereum/ethereum
    sudo apt-get update
    sudo apt-get install ethereum

**Full Steps:**

1. Create a directory for Ethereum Implementation

    mkdir FirstEthereum

2. Create a genesis.json file and place it in the directory.

Content -

    {
	     "config": {
	     "chainId": 1907,
	     "homesteadBlock": 0,    
	     "eip155Block": 0,    
	     "eip158Block": 0    
	     },    
	     "difficulty": "10",    
	     "gasLimit": "2100000",    
	     "alloc": {}    
    }

If there is an error for not enabled eip block, add it to the
genesis.json file.

*Ex: *Failed to write genesis block: unsupported fork ordering:
eip150Block not enabled, but eip155Block enabled at 0.**

Sol: Add this code block in genesis.jason

     "eip150Block": 0,

3. Create an account in node1.
 Execute the same command again to create another account in node1.

4. Choose a network id of your private network and initialize the first
node.

5. Now launching a geth console

6. The first account you created is set as *eth.coinbase* or
*eth.accounts\[0\]* and second account is *eth.accounts\[1\]*. This will
earn ether through mining. It does not have any ether yet, so we need to
mine some blocks.


	First time you run this it will create the DAG. This will take some
time. Once the DAG is completed, leave the miner running for a while
until it mines a few blocks. When you are ready to stop it, stop it
with **miner.stop()**

7. To check balance.

8. Now we’ve got some ether in the first account, let’s send it to the
2nd account we created. The source account has to be unlocked before it
can send a transaction.

9. Now transferring some ethers to account 2.

10. The ethers wont be sent until a miners validates the transaction.
Since there are no other nodes on the network so we need to mine for it.

11. Finally Stop the mining and check balance of account 2.

Hence we were able to create a private block chain and go through some
transactions and mining.
