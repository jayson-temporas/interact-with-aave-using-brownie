# Borrow crypto token using Aave protocol

Programmatically interact with a Aave protocol using brownie. We use [chainlink price feed](https://docs.chain.link/docs/ethereum-addresses/) to get eth/dai price. 

Summary of what **aave_borrow.py** do:

- Get WETH by depositing 0.1 ETH. WETH is an ERC20 token we can use to interact with Aave.
- Get the lending pool address base on the current network  
- Approve and deposit our WETH token
- Get borrowable data in ETH base on our current deposited amount
- Get the current price of DAI, the token we'll borrow.
- Borrow 95% of our borrowable eth.
- Repay our debts

We can easily update this depending on our needs. Visit [Aave](https://docs.aave.com/portal/) for more info.

## Setup

Add private key to our env variables

```
cp .env-local .env
```

Run the scripts

Mainnet Fork
```
brownie run scripts/aave_borrow.py --network kovan
```

Our in Kovan testnet
```
brownie run scripts/get_weth.py --network kovan
```

```
brownie run scripts/aave_borrow.py --network kovan
```
