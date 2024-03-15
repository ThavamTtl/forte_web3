// index.js

const Web3 = require('web3');

class Web3Tools {
    constructor(providerUrl, timeout = 10000) {
        this._web3 = new Web3(providerUrl, { timeout });
    }

    async fetchTransactionReceipt(txHash) {
        try {
            const receipt = await this._web3.eth.getTransactionReceipt(txHash);
            return receipt;
        } catch (error) {
            console.error('Error fetching transaction receipt:', error);
            throw error;
        }
    }

    async fetchBlockDetails(blockNumber) {
        try {
            const block = await this._web3.eth.getBlock(blockNumber);
            return block;
        } catch (error) {
            console.error('Error fetching block details:', error);
            throw error;
        }
    }

    async calculateGasEstimation(txObject) {
        try {
            const gas = await this._web3.eth.estimateGas(txObject);
            return gas;
        } catch (error) {
            console.error('Error estimating gas usage:', error);
            throw error;
        }
    }

    async fetchGasPrice() {
        try {
            const gasPrice = await this._web3.eth.getGasPrice();
            return gasPrice;
        } catch (error) {
            console.error('Error fetching gas price:', error);
            throw error;
        }
    }

    async fetchUserAccounts() {
        try {
            const accounts = await this._web3.eth.getAccounts();
            return accounts;
        } catch (error) {
            console.error('Error fetching user accounts:', error);
            throw error;
        }
    }

    async initiateContractDeployment(abi, bytecode, from, gas) {
        try {
            const contract = new this._web3.eth.Contract(abi);
            const deployment = contract.deploy({ data: bytecode });
            const deployedContract = await deployment.send({ from, gas });
            return deployedContract;
        } catch (error) {
            console.error('Error initiating contract deployment:', error);
            throw error;
        }
    }

    async fetchNetworkId() {
        try {
            const networkId = await this._web3.eth.net.getId();
            return networkId;
        } catch (error) {
            console.error('Error fetching network ID:', error);
            throw error;
        }
    }

    async fetchLatestBlockNumber() {
        try {
            const latestBlock = await this._web3.eth.getBlockNumber();
            return latestBlock;
        } catch (error) {
            console.error('Error fetching latest block number:', error);
            throw error;
        }
    }

    async fetchBlockTransactionCount(blockNumber) {
        try {
            const transactionCount = await this._web3.eth.getBlockTransactionCount(blockNumber);
            return transactionCount;
        } catch (error) {
            console.error('Error fetching transaction count for block:', error);
            throw error;
        }
    }
}

module.exports = Web3Tools;
