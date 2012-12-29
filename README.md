Open Transactions: Server, Smart, and Currency Contracts
=============================================

The goal is to create a variety of server contracts, along with several different kinds of smart contracts, and 
currency contracts—these contracts can then be used to trade, for example: digital gold, digital silver, 
"digital" bitcoin, as well as other valuable currencies and commodities, across many different servers, complimented by 
smart contracts. The vision is for these servers to be low-trust and federated, securing and releasing currency 
and commodities with zero risk.

See: https://github.com/FellowTraveler/Open-Transactions

###What's been done, and what I'd like to do

I currently have two basic currency contracts: Digital Gold Grams, and Digital Silver Grams; I would like to develop
these currency contracts—as well as all of this project's future contracts—into proper technical and legal documents 
that can be used on plug and play for-profit servers.

###Completed and working on:
* Completed: basic Digital Silver Grams currency contract
* Completed: basic Digital Gold Grams currency contract
* Working on: hosting basic public server
* Working on: publishing basic public server contract

###How to use sample data

Copy the contents of the /sample-data directory into your ~/.ot directory.

###Smart Contracts

The first smart contract I would like to work on would be used to exchange bitcoins for "digital" bitcoins, or 
"digiBTC". The smart contract could be used on a webpage, server, or within a mobile app to record the client's 
wallet address and requested amount of digiBTC, the smart contract would then monitor and await a single blockchain 
confirmation (or however many confirmations are set in the contract) of the transfer; once confirmed the smart 
contract would tell the server to issue the digiBTC to the client. The whole operation would be reversed to exchange 
the digiBTC for bitcoin.

<br>
<img align="center" src="http://i49.tinypic.com/161fiq9.png" alt="Moneychanger" />
<br>
<br>
<img align="center" src="http://i49.tinypic.com/14vmoee.png" alt="Moneychanger" />


