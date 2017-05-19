##

https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-16-04


node_modules/.bin/testrpc -h 0.0.0.0

node

Web3 = require('web3')

web3 = new Web3(new Web3.providers.HttpProvider("http://localhost:8545"));

web3.eth.accounts

code = fs.readFileSync('Voting.sol').toString()

contract = web3.eth.compile.solidity(code)

VotingContract = web3.eth.contract(contract.info.abiDefinition)

deployedContract = VotingContract.new(['Rama','Nick','Jose'],{data: contract.code, from: web3.eth.accounts[0], gas: 4700000})

contractInstance = VotingContract.at(deployedContract.address)

contractInstance.totalVotesFor.call('Rama')

contractInstance.voteForCandidate('Rama', {from: web3.eth.accounts[0]})

contractInstance.voteForCandidate('Rama', {from: web3.eth.accounts[0]})

contractInstance.voteForCandidate('Rama', {from: web3.eth.accounts[0]})

contractInstance.totalVotesFor.call('Rama').toLocaleString()