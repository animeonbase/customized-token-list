# LI.FI custom tokens

LI.FI supports any token passed to the API as long as we can validate it and find a USD price for it.

The API exposes a list of tokens that UIs can use as default to give their users tokens to choose from. e.g. our widget uses that list: https://li.quest/v1/tokens

We automatically include tokens in that token list if they are listed in one of the token list we support:
- lists of assets the bridges suppoert
- offical lists of exchanges we support
- in own custom token list (this repository)

And if we can validate the token:
- we can find usd prices via debank or zerion APIs
- the token is not a spam/fee taking token

## How to add your token

To add your token find the file representing the chain your token is in in the **tokens** folder. 

Add your token as the last element in the list (don't forget the `,` after the previous token):
```json
  },  <== Add the comma
  {
    "address": "0x155f0DD04424939368972f4e1838687d6a831151",
    "chainId": 42161,
    "logoURI": "https://yoursite.com/token.svg", <= permanent link to an image of your token
    "decimals": 18,
    "name": "nice Name",
    "symbol": "SYMBOL"
  }
]
```

Create a PR with the change describing why we should add that token. Link your project, coingecko and profiles so we can validate the token.
