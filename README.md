Open Transactions: Server, Smart, and Currency Contracts
=============================================

The goal is to create a variety of server and currency contracts, along with several different kinds of smart contracts. These contracts can then be used to trade, for example: digital gold grams, digital silver grams, and 
"digital" bitcoin, as well as other valuable currencies and commodities across many different servers—complimented by smart contracts. The vision is for these servers to be low-trust and federated: securing, transferring, and releasing currencies with zero risk.

See: https://github.com/FellowTraveler/Open-Transactions

###What's been done, and what I'm working on

I currently have two basic currency contracts: Digital Gold Grams, and Digital Silver Grams; I would like to develop
these currency contracts—as well as all of this project's future contracts—into proper technical and legal documents 
that can be used on for-profit servers.

###Completed and working on:
* Completed: basic Digital Silver Grams currency contract
* Completed: basic Digital Gold Grams currency contract
* Working on: hosting basic public server
* Working on: publishing basic public server contract

###How to use sample data

Copy the contents of the /sample-data directory into your ~/.ot directory and then launch Open Transactions.

###Smart Contracts

The first smart contract I would like to work on would be used to exchange bitcoins for "digital" bitcoins, or "digiBTC". The smart contract could be used on a webpage, server, or within a mobile app to record the client's 
wallet address and requested amount of digiBTC, the smart contract would then monitor and await a single blockchain 
confirmation (or however many confirmations are set in the contract) of the transfer; once confirmed the smart contract 
would tell the server to issue the digiBTC to the client. The whole operation would be reversed to exchange digiBTC for 
bitcoin.

###How to create a currency contract

Creating a currency contract is simple: first, create or open a sample .xml file, then state your conditions and 
attach your nym's public key (find this by using the "exportcert" command in the opentxs CLI, or in the
~/.ot/client_data/certs/ directory) in the < key name="contract" > area like this:

    <!-- KEYS -->

    <key name="contract">
    - -----BEGIN CERTIFICATE-----
    MIICPzCCAaigAwIBAgIBADANBgkqhkiG9w0BAQQFADAlMQswCQYDVQQGEwJVSzEW
    MBQGA1UEAxMNT3BlblNTTCBHcm91cDAeFw0xMjEyMjgwMDA5MTBaFw0yMjEyMjYw
    MDA5MTBaMCUxCzAJBgNVBAYTAlVLMRYwFAYDVQQDEw1PcGVuU1NMIEdyb3VwMIGf
    MA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDPn/MBn7lt2ZUn160qUPmvPk67yFbz
    iXzZpGmePJCZsounat6XsNl0wJaSvnWiqvTvAIPbIMrkIlUWKpIRKbiFeVwSTPay
    4TA8oSXQkv80lF+X0fsncmv5zkpoa9dntdSm1gTuTAYG/+iZ/VJVXmTrS9OxYucr
    SUTu2A1XldDi7wIDAQABo38wfTAPBgNVHRMBAf8EBTADAQH/MA4GA1UdDwEB/wQE
    AwIBBjAdBgNVHQ4EFgQU54XD2rYY2Kgg9aKsojyxVshIIbowEQYJYIZIAYb4QgEB
    BAQDAgIEMCgGCWCGSAGG+EIBDQQbFhlleGFtcGxlIGNvbW1lbnQgZXh0ZW5zaW9u
    MA0GCSqGSIb3DQEBBAUAA4GBAEZ6lyRvqU9VWzKEDtXodbnP+23vw28NmXxC58b3
    KtRI5AkpMjBEnszLI7fS3GhNF2jFExOLhFtVWA2yfyrwSIxpi8ll3jv9v74qE1LH
    EoSuGSXTQsZ9WGC+hE47I0jkRu6JWpcQIPI2JS+/o8GGLrSqGTGX1LqrZVpNecRr
    QcuY
    - -----END CERTIFICATE----
    </key>
    </digitalAssetContract>

It is crucial that you begin and end the certificate with "- -----", making sure that there is a space after the 
first dash.

Once you've entered the contract's conditions and attached your nym's public key you can run it through the opentxs 
command line.

  	$ opentxs
	$ newasset

<img align="center" src="http://i47.tinypic.com/f2u2w1.png" alt="newasset" />

It will ask you to "Please enter the XML contents for the contract, followed by an EOF or a ~ by itself on a blank 
line:", once you've done that it will return the signed and completed contract and all you need to do is save the 
text to a text file with the .otc extension.

It should now look like this:

    -----BEGIN SIGNED CONTRACT-----
    Hash: SAMY

    <?xml version="1.0"?>
    <digitalAssetContract version="1.0">

    <entity shortname="DigiGold"
    longname="Digital Gold Grams" 
    email="stretchwarren@gmail.com"/>

    <issue company="Stretch's Precious Metals"
    email="stretchwarren@gmail.com"
    contractUrl="coming soon..."
    type="currency"/>

    <currency name="Gold Grams" tla="dGOLD" symbol="dGOLD"
    type="decimal" factor="1" decimal_power="0" fraction=""/>

    <!-- CONDITIONS -->

    <condition name="backing">
    Digital Gold Grams are payable to bearer in physical gold grams, at any exchange provider 
    supporting our contract in any denomination
    they support, or through one of our direct agents in 1 oz bars.
    </condition>

    <condition name="audit">
    Gold Grams are audited monthly by highly trusted people.
    </condition>

    <condition name="purchase">
    In order to obtain Digital Gold Grams you must recieve them in trade, or purchase them, in person, from me.
    </condition>

    <condition name="redemption">
    Digital Gold Grams can be redeemed for real gold, or gold's current exchange 
    value, as determined by the exchange rate of http://www.vbce.ca/ at the time of redemption.
    </condition>

    <condition name="rate">
    Issuance and redemption will be performed at no charge.
    </condition>

    <condition name="buyback">
    The Issuer reserves the right to buy back all outstanding
    currency, thereby terminating the use of this instrument.
    </condition>

    <condition name="liability">
    None, purchase and trade Digital Gold Grams at your own risk.
    </condition>

    <condition name="mint">
    Float - the total quantity of gold is determined by the Law of Identity.
    The quantity of gold that enters the market yearly is strictly
    regulated by the Law of Causality and cannot accurately be predicted.
    
    Any server operator using this contract will not issue any more
    Digital Gold Grams than he actually has in physical gold.
    </condition>

    <condition name="privacy">
    The purchase and trading of Digital Gold Grams are preformed
    on the basis of strong privacy.
    </condition>

    <!-- KEYS -->

    <key name="contract">
    - -----BEGIN CERTIFICATE-----
    MIICPzCCAaigAwIBAgIBADANBgkqhkiG9w0BAQQFADAlMQswCQYDVQQGEwJVSzEW
    MBQGA1UEAxMNT3BlblNTTCBHcm91cDAeFw0xMjEyMjgwMDA5MTBaFw0yMjEyMjYw
    MDA5MTBaMCUxCzAJBgNVBAYTAlVLMRYwFAYDVQQDEw1PcGVuU1NMIEdyb3VwMIGf
    MA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDPn/MBn7lt2ZUn160qUPmvPk67yFbz
    iXzZpGmePJCZsounat6XsNl0wJaSvnWiqvTvAIPbIMrkIlUWKpIRKbiFeVwSTPay
    4TA8oSXQkv80lF+X0fsncmv5zkpoa9dntdSm1gTuTAYG/+iZ/VJVXmTrS9OxYucr
    SUTu2A1XldDi7wIDAQABo38wfTAPBgNVHRMBAf8EBTADAQH/MA4GA1UdDwEB/wQE
    AwIBBjAdBgNVHQ4EFgQU54XD2rYY2Kgg9aKsojyxVshIIbowEQYJYIZIAYb4QgEB
    BAQDAgIEMCgGCWCGSAGG+EIBDQQbFhlleGFtcGxlIGNvbW1lbnQgZXh0ZW5zaW9u
    MA0GCSqGSIb3DQEBBAUAA4GBAEZ6lyRvqU9VWzKEDtXodbnP+23vw28NmXxC58b3
    KtRI5AkpMjBEnszLI7fS3GhNF2jFExOLhFtVWA2yfyrwSIxpi8ll3jv9v74qE1LH
    EoSuGSXTQsZ9WGC+hE47I0jkRu6JWpcQIPI2JS+/o8GGLrSqGTGX1LqrZVpNecRr
    QcuY
    - -----END CERTIFICATE----
    </key>

    </digitalAssetContract>
    -----BEGIN CONTRACT SIGNATURE-----
    Version: Open Transactions 0.87.h
    Comment: http://github.com/FellowTraveler/Open-Transactions/wiki

    CoABl31EZExc03iLp14yAWBJdrqb6O55DCIytvEsAQxgTSMKIe6u30NM/zr3K16J
    DnD/CkOpy+0Csx08NURWAHnCuw+VeqW9x691gxGxKQnajJQ1Ntpq08nyX1yM3+CV
    yII1584ZnCf/mf22GEk7OTxRLqI1oWue/LVbBOPtgTLGGfA=
    -----END CONTRACT SIGNATURE-----"
    
###Screenshots

<br>
<img align="center" src="http://i49.tinypic.com/161fiq9.png" alt="Moneychanger" />
<br>
<br>
<img align="center" src="http://i49.tinypic.com/14vmoee.png" alt="Moneychanger" />


