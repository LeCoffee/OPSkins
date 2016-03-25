#opskins
### A node module to help automate opskins.com

### Example

```
var opClient = new OPSkins(APIKEY) // API Key see https://opskins.com/?loc=store_account

opClient.on('ready', function() {
	console.log("OPSkins API key works");
});

opClient.on('apikeyError', function(err) {
	console.log("An error occured using API key " + err);
})

```

# Methods


### Constructor([apikey])
- `apikey` - Your OPSkins API key, you can get it from https://opskins.com/?loc=store_account. **You need to sell 10 items on OPSkins to be able to get it.***

### sellItem(assetId, amount, [feature], [callback])
- `assetId` - The assetid of the item you want to sell.
- `amount`  - USD Cents you wish to sell the item for
- `feature` - (optional) if you want to feature this item see https://opskins.com/?loc=api_docs
- `callback` - (optional) a function that will be called on response.
    - `error` - An error if an error was returned.
    - `bot`   - "Bot number sending the trade"
    - `bot_steamid` - The steamid64 of the bot sending you an offer
    - `token` - An OPSkins security token
    - `sale_id` - "ID of the OPSkins sale that was created in response to this request"
    - `tradeoffer_id` - "ID of the trade offer that was sent in response to this request"

# Events

### ready
Emitted when the API key works.

### apikeyError
Emitted when the API key returns a success not equal to 200 or when the response code doesn't give 200. AKA API Key doesn't work. I've never exceeded my API limit so I don't know if it returns rate limit errors.


### Todo:

This isn't going to be a very maintained project unless it gains popularity, this was solely created for me to sell items on OPSkins without having to repeat lots of code.

- GetActiveSales
- GetStaleSales
- ResendTrade
- GetOP
- Cashout
- BumpItem
- EditItem
- ~~SellItem~~
- GetPriceHistory
