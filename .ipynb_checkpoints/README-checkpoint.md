# ERC20 Token Crowdsale 

This homework will create a crowdsale of PupperCoin (PUPC) token in order to help fund the network development. This network will be used to track the dog breeding activity across the globe in a decentralized way, and allow humans to track the genetic trail of their pets. The crowdsale is enabled for refunds if the crowdsale is successful and the goal is met, and the cap is to raise a maximum of 300 Ether. The crowdsale will run for 24 weeks.

---

## Files

### ERC20 PupperCoin

* [`PupperCoin.sol`](Code/PupperCoin.sol)

Using Remix, I created a file called `PupperCoin.sol` and created a standard `ERC20Mintable` token using a standard `ERC20Mintable` and `ERC20Detailed` contract, hardcoding `18` as the `decimals` parameter, and leaving the `initial_supply` parameter alone

### PupperCoinCrowdsale

* [`Crowdsale.sol`](Code/CrowdSale.sol)

The PupperCoin (PUPC) will be minted through a `Crowdsale` contract that is leveraged from the OpenZeppelin Solidity library. This crowdsale contract will manage the entire process, allowing users to send ETH and get back PUPC. It inherits `Crowdsale`, `CappedCrowdsale`, `TimedCrowdsale`, `RefundablePostDeliveryCrowdsale`, and `MintedCrowdsale`.

---

## Deploy the Crowdsale

For the purpose of testing, I have set the `close` time to be `now + 5 minutes`, as well as the `goal` to be `1 ether`, in order to have a successful crowdsale and finalize the sale.

### PupperCoin

Open Metamask, change the network to Kovan. Pre-fund the address to ensure successful deployment of the contract as it would require some Gas. Deploy the first contract `Puppercoin`. Paramaters required for deployment: `name`, `symbol`, `initial_supply`.

![`deploy_PupperCoin`](Images/deploy_PupperCoin.PNG)

### PupperCoinSaleDeployer

Next, deploy `PupperCoinSaleDeployer`, parameters required: `name`, `symbol`, `wallet`, `goal`

![`deploy_PupperCoinSaleDeployer`](Images/deploy_PupperCoinSaleDeployer.PNG)

### PupperCoinSale

Deploy `PupperCoinSale` Contract with `token_sale_address` in the `At_Address` section. You should have found the `token_sale_address` under `PupperCoinSaleDeployer` deployed contract

![`deploy_PupperCoinSale`](Images/deploy_PupperCoinSale.PNG)

### PupperCoin

Deploy `upperCoin`Contract with `token_address` in the `At_Address` section. You should have found the `token_address` under `PupperCoinSaleDeployer` deployed contract

![`PUPC_token_address`](Images/PUPC_token_address.PNG)

---

## Purchase Tokens

Open the deployed `PupperCoinSale` contract, put in your `beneficiary` address under `buyTokens`

![`buy_token`](Images/buy_token.PNG)

Once the goal is reached and crowsale is closed, you can finalize the crowdsale

![`finalized`](Images/finalzed.PNG)

You can then withdraw your token PUPC to your own wallet

On Metamask, you cann add Tokens by adding the `token_address`, the `name` and `decimal` should auto-populate

![`PUPC_balance`](Images/PUPC_balance.PNG)

---

## Etherscan

You can find the PUPC token on Etherscan by inputting the `token_address`

![`PUPC_etherscan`](Images/PUPC_etherscan.PNG)

You can also see the wallet that owns the tokens, i.e. the wallet that participates in the crowdsale

![`PUPC_holder`](Images/PUPC_holder.PNG)

---

## MyCrypto

Unfortunately, I had problem connecting to Kovan network on MyCrypto, so I couldn't access my wallet to view the token balance. But you should be able to do that by loading your wallet and add PUPC as custom token. 