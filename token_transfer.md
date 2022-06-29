<p style="font-size:14px" align="right">
<a href="https://discord.gg/hcbT5ryUdF" target="_blank">Join NodeRobin discord <img src="https://camo.githubusercontent.com/0ef309f7e0b554033dd25b3ce83015db2f0f8952fb4c31318af095369d3d4453/68747470733a2f2f7669676e657474652e77696b69612e6e6f636f6f6b69652e6e65742f7468652d6d696e6572732d686176656e2d70726f6a6563742f696d616765732f642f64642f446973636f72642e706e672f7265766973696f6e2f6c61746573743f63623d3230313730333038303333353436" width="30"/></a>
</p>

<p align="center">
  <img height="100" height="auto" src="https://user-images.githubusercontent.com/50621007/176226900-aae9149d-a186-4fd5-a9aa-fc3ce8b082b3.png">
</p>

# How to transfer tokens between Ethereum and Substrate wallets

## Creating an Agung Wallet
1. Download and install [Browser Extension](https://polkadot.js.org/extension/)
2. Navigate to [Peaq Explorer](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fwss.agung.peaq.network#/accounts) and press `Add account` button

<p align="center">
<img src="https://user-images.githubusercontent.com/50621007/176287432-b36e3e0a-62ef-42e1-9eb8-14dfb1343e30.png" />
</p>

3. Save `mnemonic` and create wallet

<p align="center">
<img src="https://user-images.githubusercontent.com/50621007/176287079-b24b7859-9857-41e2-9ec9-ea9c68f67163.png" />
</p>

4. This will generate wallet address that you will have to use later. Example of wallet address: `5HVZ1wAh3wTejYXUyhhzXvDRStas1fnC3DhnFmcwBaewdDRt`

<p align="center">
<img src="https://user-images.githubusercontent.com/50621007/176312664-5c127b11-c94d-49ea-bb75-4173962adc15.png" />
</p>

## Create an Ethereum wallet on Agung (peaq Testnet)
1. Download and install [Metamask Browser Extension](https://chrome.google.com/webstore/detail/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn?hl=en)
2. After adding the MetaMask plugin, connectivity needs to established with Agung network by adding:
- Network Name: `PEAQ`
- RPC endpoint: `​https://erpc.agung.peaq.network/`
- Chain ID: `9999`
- Currency Symbol: `AGNG`

<p align="center">
<img src="https://user-images.githubusercontent.com/50621007/176288147-c7b708ef-68fa-43ce-9408-f16c2c6e0c0c.png" />
</p>

3. Once connected with Agung network, the details of the wallet address are seen.

<p align="center">
<img src="https://user-images.githubusercontent.com/50621007/176288328-33ab0dbb-1416-47de-8443-98cf93eef978.png" />
</p>

## Fund your polkadot wallet
To top up your wallet join [peaq discord server](https://discord.gg/6tTJH7QT) and navigate to:
- **#agung-faucet** for AGNG tokens

To request a faucet grant:
```
!send <YOUR_WALLET_ADDRESS>
```

<p align="center">
<img src="https://user-images.githubusercontent.com/108177837/176342388-2d303bfe-833d-4253-8ce6-665e7d7ee540.png" />
</p>

## Deposit tokens from a Substrate Wallet to an ETH wallet on Agung (peaq Testnet)
### Generate your deposit address
1. Copy your ETH address (Public Key)
2. Use [this website](https://hoonsubin.github.io/evm-substrate-address-converter/index.html) to calculate your deposit address for Substrate.
3. Change the address scheme to "H160".
4. Leave the "Change address prefix" at "5".
5. Enter your ETH address (Public Key) into the "Input address" field.

<p align="center">
<img src="https://user-images.githubusercontent.com/50621007/176289096-379bccd1-819b-4f15-8e13-0e9f92abb914.png" />
</p>

6. Copy the lower address which represents your deposit address.  

<p align="center">
<img src="https://user-images.githubusercontent.com/50621007/176289291-19bc4d17-7352-418b-bdb9-4461b53bd655.png" />
</p>

### Transfer Tokens 
1. Go to [polkadot.js](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fwss.agung.peaq.network#/accounts)
2. Select the account you want to transfer funds from and click "send":

<p align="center">
<img src="https://user-images.githubusercontent.com/50621007/176292506-9e83208b-060b-4167-b0d7-287f5bab6de7.png" />
</p>

3. Enter your generated deposit address in the "send to address" field:

<p align="center">
<img src="https://user-images.githubusercontent.com/50621007/176297566-b34d54be-ebcb-4fdd-9115-a6bb0d17b566.png" />
</p>

4. Enter the amount you want to transfer. 
5. Click the "Make transfer" button.
6. Click the "Sign and Submit" button.
7. Check the balance on your Ethereum (Metamask) Wallet.

<p align="center">
<img src="https://user-images.githubusercontent.com/50621007/176299868-1d9b1e10-2f1d-4bfd-bb7a-00993a864a01.png" />
</p>

You have successfully transferred Tokens from your Substarte Wallet to your Ethereum Wallet. 

## Withdraw tokens from an ETH Wallet to a Substrate wallet on Agung (peaq Testnet)
### Generate your deposit address
1. Copy your Substrate address (Public Key)

<p align="center">
<img src="https://user-images.githubusercontent.com/108177837/176342588-42098abf-82ff-4aaa-863d-bfca54d25d15.png" />
</p>

2. Use [this website](https://www.shawntabrizi.com/substrate-js-utilities/) to calculate your withdrawal address for Substrate.
- Paste your (1) Substrate address under the `AccountId to Hex` text input.
- Copy the `first 42 characters` from the converted result, or `40 characters` with exception of the "0x"

<p align="center">
<img src="https://user-images.githubusercontent.com/108177837/176342726-ee182df4-d176-4e5b-854e-5f3ca3e297d2.png" />
</p>

3. Send AGNG from your ETH wallet to this recent copied ETH address

<p align="center">
<img src="https://user-images.githubusercontent.com/50621007/176303176-93aa2094-46b3-4a41-b4f1-3dc85c56d226.png" />
</p>

4. Approve and sign the transaction. Pay the calculated gas for this transaction.
Your transaction is on its way. After a few seconds you should have it completed.
5. Go to the [Polkadot js Extrinsicts page](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fwss.agung.peaq.network#/extrinsics)
6. Complete the form to call an Extrinsics, like the following example:
- Using the selected account: Who is paying fees for the transaction? in this case could be your own Substrate address (if you have balance)
- submit the following extrinsic: select `evm (withdrawal(adress, value)`
- address: H160: the ETH address which we recently send AGNG (`0x6803066634c5964f3dfd33a7a5c746d717471258`)
- value (BalanceOF): how many AGNG will I retrieve from the Extrinsic. In this case .3 AGNG = `3 + 17` zeros or 1 AGNG = 1000000000000000000 (+ 18 zeros)

<p align="center">
<img src="https://user-images.githubusercontent.com/108177837/176352083-16b99fbb-c186-45bc-b01a-32f90dd04290.png" />
</p>

7. Sing the transaction. Wait a few seconds for a confirmation. Your AGNG should arrive to your account.

<p align="center">
<img src="https://user-images.githubusercontent.com/50621007/176307637-c281ccee-b060-4101-945c-15d1ce708714.png" />
</p>

You have successfully transferred Tokens from your ETH Wallet to your Substrate Wallet. 

<p align="center">
<img src="https://user-images.githubusercontent.com/108177837/176351920-d1df2a29-a986-4d0a-a993-99d250f99b59.png" />
</p>
