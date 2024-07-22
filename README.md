# Cooper Telegram Sniper
The Cooper Telegram Sniper is a bot that snipes tokens in desired telegram channels.

📡 Custom RPC: Our bot allows you to set an RPC of your choosing, or use our default one

⚡ Lightning-Fast Sniping: With our bot, it's possible to snipe coins in lightening-fast speed 

📴 AFK Mode: Our bot can be used while AFK. Whether you're sleeping, eating, out or busy, our bot will snipe coins as long as it's running.

💸 Auto Sell: Our bot allows you to set a specific amount of time that you would like it to hold coins for & will auto sell once that time has ended.

# How to Use the Solana Cooper Bot

This guide walks you through setting up and using the Solana Cooper Bot for Telegram token sniping.

## Configuration Files:

The bot uses several JSON configuration files. You'll need to fill in the details for each file.

### 1. Buy Config (buy_config.json):

This file defines your buying preferences. Open the file with a text editor and replace the placeholders with your values:

```javascript
{
  "BUY_AMOUNT": BUY_AMOUNT_IN_SOL,                            //example 1.0
  "SLIPPAGE": SLIPPAGE_IN_PERCENTAGE,                        //example: 5 (meaning 5%)
  "PRIORITY_FEE": PRIORITY_FEE_IN_SOL,                      //example 0.01
  "MAX_MARKET_CAP": MAX_MARKETCAP_TO_STILL_BUY,            //example 100000
  "WALLET_API_KEY": "YOUR_WALLET_API_KEY",                //allows you to use our default RPC you can get this from here: https://sniperbotwebsite.vercel.app/api/generate-wallet Skip this step if you have your own RPC 
  "PUBLIC_KEY": "YOUR_PUBLIC_KEY",                       // if you want to use the default RPC then fill in the wallet address from the site here, other whise any wallet will work
  "PRIVATE_KEY": "YOUR_PRIVATE_KEY",                    // if you want to use the default RPC then fill in the wallet address from the site here, other whise any wallet will work
  "AUTO_SELL": "False",                                // set to "True" if you want the bot to automatically sell the token after a set period of tim, otherwhise set it to "False"
  "AUTO_SELL_HOLD_TIME": TIME_IN_SECONDS,             //amount of time, in seconds the bot should hold the coin for 
  "AUTOSELL_RETRY_AMOUNT": MAX_RETRIES_AMOUNT,       //Max amount of times the sell txn should attemtp to sell 
  "USE_CUSTOM_RPC": "False", // If set to "True" then you must fill in CUSTOM_RPC_ENDPOINT as well, if set to "False" then fill in the WALLET_API_KEY
  "CUSTOM_RPC_ENDPOINT": "CHANGE TO CUSTOM RPC OR LEAVE EMPTY"// emty as in ""
  "PREFERRED_POOLS": ["pump","raydium"] // pools that you want the bot to buy - pump for pump, raydium for raydium, if you want the bot to buy both then leave them both in
  "USE_WEBHOOK":"True"                  // Allows the bot to send a webhook when a buy or a sell happens, if set to "False" it will not post anything. Anonymous.  
  "CUSTOM_WEBHOOK": "CUSTOM_WEBHOOK"         //leave as is or change with own discord webhook URL 
}
```
You can obtain the wallet credentials [here](https://sniperbotwebsite.vercel.app/api/generate-wallet).
> [!NOTE]
> We do not save any informations about wallets that get generated here.


### 2. Credentials (credentials.json):

This file stores your Telegram API credentials. You can obtain these credentials from the Telegram API (https://my.telegram.org/apps).

```javascript
{
  "API_ID":YOUR_API_ID,             //make sure to leave as a number
  "API_HASH":"YOUR_API_HASH"
}
```
> [!CAUTION]
> Do not share this with anyone! Your telegram account can get compromised by these values getting exposed!

### 3. Monitored Groups (monitoredGroups.json):

This file specifies the Telegram group IDs where the bot will listen for sniping opportunities. Enter the group IDs you want to monitor, each on a separate line:
You can get these ID's by either using a telegram bot like [GetMyIDBot](https://t.me/getmy_idbot) or using the command !getid in the Cooper bot discord.
```javascript
[
  GROUP_ID_1,
  GROUP_ID_2
]
```

### 4. Filter Words (filteredWords.json (Optional))

This file defines keywords the bot will ignore during sniping. The default list includes words like "scam", "rug", and "presale". To add custom words, open the file and add them to the list:
```javascript
["scam", "rug", "honeypot", "presale", "trash", "sniper", "dont", "buy", "snipe"]
```


## Manual Sell Feature

In the `buyconfig.json` file, you can control the autosell behavior:
````json
{
    ...
    "AUTO_SELL":"False"
    ...
}
````
When `AUTO_SELL` is set to `False`, the bot won't automatically sell tokens after a set time period. Instead, you can use the manual sell feature for more control over your trades.


#### View Active Trades
Type `list` in the console to see all current active trades with their index numbers.

#### Sell a Specific Trade
Use the command `sell <trade_number>`. For example:
- To sell the first trade: `sell 1`
- To sell the third trade: `sell 3`

#### Monitor Results
The bot will attempt to sell the specified trade and provide feedback on the sell operation.

#### Trade Removal
Successfully sold trades are automatically removed from the active trades list.

## Running the Bot:

1. Double-click "Cooper Telegram Sniper.exe" to start the bot.
2. Enter the APP Key provided by the Cooper bot team on Discord.
3. Fill in the `buy_config.json` and `credentials.json` files as instructed.
4. Enter the group IDs you want to monitor in `monitoredGroups.json`.
5. When prompted, choose "now" or "later" to add custom filter words in filteredWords.json.

## Aditional features

The bot also automatically generates a `transaction_stats.json` file to track transaction success, failure, and profit/loss of the bot.

# FAQ
> **Can I run the bot on Linux?**
> 
> You should be able to run the bot on linux by using [Wine](https://www.winehq.org/).

> **Can I run the bot on MacOS?**
> 
> You should be able to run the bot on linux by using [WineBottler](https://winebottler.kronenberg.org/)) but we are working on getting an MacOS version out.

> **How can I get the APP key?**
>
> You can get one by applying for beta in the [form](https://docs.google.com/forms/d/e/1FAIpQLSeqrZpPLQ-VkIqqZmx8fzyw4DPdZW02Sqil66P30ad3BEIX-A/viewform) after joining our [discord server](https://dsc.gg/cooperbot).

# Socials
[![](https://img.shields.io/twitter/url/https/twitter.com/CooperBotSOL.svg?style=social&label=@CooperBotSol)](https://x.com/CooperBotSOL)

[![](https://dcbadge.limes.pink/api/server/https://discord.com/invite/EQCbewNZex)]((https://discord.com/invite/EQCbewNZex))



# Team members 
> **MD20M**
> 
> ![](https://dcbadge.limes.pink/api/shield/301340957025107972)
>
> [![](https://img.shields.io/twitter/url/https/twitter.com/TheRealMD20M.svg?style=social&label=@TheRealMD20M)](https://x.com/TheRealMD20M)

> **asaff.sol**
> 
> ![](https://dcbadge.limes.pink/api/shield/829969665035862046)
>
> [![](https://img.shields.io/twitter/url/https/twitter.com/asaf1_2_3.svg?style=social&label=@asaf1_2_3)](https://x.com/asaf1_2_3)

> **Hush**
> 
> ![](https://dcbadge.limes.pink/api/shield/669556108846694432)
>
> [![](https://img.shields.io/twitter/url/https/twitter.com/GRemdarem.svg?style=social&label=@GRemdarem)](https://x.com/GRemdarem)
