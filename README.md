
# Speakez  
  
  Examples at the bottom!
  
## Definition:  

Strategies is an array of array of strategy. First order array can be understood as a **OR** and second order array as and **AND**.

Pseudo code example:
```
[
	[
	"user should have 10 Aria", 
	// AND
	"user should have 15 Matic"
	],
	// OR
	[
	"user should have 10 eth"
	]
]
```

A strategy is item is:

```
{
	      "chainId":"137", // gateway provider
	      "name":"erc-20-balance-of", // name of strategy
	      "address":"caller",
	      "params":{ // required depends on strategy
	         "minBalance":"100000000000000000000", // min balance of this erc20 to own to be authorized
	         "address":"0x46F48FbdedAa6F5500993BEDE9539ef85F4BeE8e"
	      }
	   }
```

## Examples:  
  
### Simple strategy: user has Aria20  on Polygon
  
```javascript  
  [
	  [
	   {
	      "chainId":"137", // gateway provider
	      "name":"erc-20-balance-of", // name of strategy
	      "address":"caller",
	      "params":{
	         "minBalance":"100000000000000000000",
	         "address":"0x46F48FbdedAa6F5500993BEDE9539ef85F4BeE8e"
	      }
	   }
	]
]
```

### OR strategy: user has Aria20  on Polygon **OR** on Mainnet
 
```javascript  
 [
   [
      {
         "chainId":"137",
         "name":"erc-20-balance-of",
         "address":"caller",
         "params":{
            "minBalance":"100000000000000000000",
            "address":"0x46F48FbdedAa6F5500993BEDE9539ef85F4BeE8e"
         }
      }
   ], // Each array is a OR strategy
   [
      {
         "chainId":"1",
         "name":"erc-20-balance-of",
         "address":"caller",
         "params":{
            "minBalance":"100000000000000000000",
            "address":"0x46F48FbdedAa6F5500993BEDE9539ef85F4BeE8e"
         }
      }
   ]
]
```


### AND strategy: user has Aria20  on Polygon **AND** on Mainnet
 
```javascript  
[
   [
      {
         "chainId":"137",
         "name":"erc-20-balance-of",
         "address":"caller",
         "params":{
            "minBalance":"100000000000000000000",
            "address":"0x46F48FbdedAa6F5500993BEDE9539ef85F4BeE8e"
         }
      },// Each strategy item has to be validated
      {
         "chainId":"1",
         "name":"erc-20-balance-of",
         "address":"caller",
         "params":{
            "minBalance":"100000000000000000000",
            "address":"0x46F48FbdedAa6F5500993BEDE9539ef85F4BeE8e"
         }
      }
   ]
]
```
