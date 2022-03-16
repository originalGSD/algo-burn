# Algorand Burn Address

This is a simple script to illustrate how a "burn address" can be generated for one or more Algorand Standard Assets (ASAs). Since addresses need to be "opted-in" to receive a specific ASA, it is not possible to just send tokens to a random address.

The script uses a similar approach to what the Algorand Foundation used to burn Early Redemption Auction Tokens. All details can be found here: https://algorand.foundation/news/the-algorand-foundation-today-confirm-token-burn

Since we are not burning ALGOs (that would require to only send ALGOs to a random address) we are using a process called 're-keying' so that, once the burn address is configured accordingly, its "authorized account" is set to a random public address.

Process is as follow:
- Fund a "burn" address with the amount of Algo required to opt-into one or more ASAs
- Add a ".env" file with burn address and its mnemonic key
- Pick a list of assets you want to burn and modify the script accordingly
- Pick a date and modify the script accordingly. This is used to generate a random (verifiable) address
- Run the code

If code is successful and you run it twice, it will fail the second time since you don't have the authorization to sign transactions for the burn address anymore.

This has been used to generate a burn address for AlgoScout (ASA ID: 569120128)

Here are the links to the SCOUT opt-in and re-keying transactions:

https://algoexplorer.io/tx/FDSOCKQPB7CM67XJJOT62Y7C3QZXA2BGYIT7JM5FKM7WXAHAGEVA
https://algoexplorer.io/tx/DTLKTFMO4WKYB7LDIDYORA6TFJPD7LZWMDMEYHEIFMOI6PAR3C4A

NOTE: burnt tokens will still be included in the total circulating supply calculation, unless you set the burn address as the "reserve" address.
