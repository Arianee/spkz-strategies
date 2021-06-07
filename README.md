
# Speakez  
  
## Strategies examples:  
  
### User has Aria20  on Polygon
  
```javascript  
   [
   {
      "provider":"https://rpc-mainnet.maticvigil.com", // rpc provider
      :"erc-20-balance-of", // strategy name
      "address":"caller",
      "params":{
         "minBalance":"100000000000000000000", // min balance of ERC20
         :"0x46F48FbdedAa6F5500993BEDE9539ef85F4BeE8e"// address of erc20 Aria20
      }
   },
  
```
### User has Aria20 and Matic  
```javascript  
[
   {
      "provider":"https://rpc-mainnet.maticvigil.com",
      :"erc-20-balance-of",
      "address":"caller",
      "params":{
         "minBalance":"100000000000000000000",
         :"0x46F48FbdedAa6F5500993BEDE9539ef85F4BeE8e"// address of erc20 Aria20
      }
   },
   {
      "provider":"https://rpc-mainnet.maticvigil.com",
      :"erc-20-balance-of",
      "address":"caller",
      "params":{
         "minBalance":"100000000000000000000",
         :"0x0d500B1d8E8eF31E21C99d1Db9A6444d3ADf1270"// address of erc20 Wrapped Matic
      }
   }
]
