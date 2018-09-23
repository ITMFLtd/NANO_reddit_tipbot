# ITCO Reddit TipBot

## About
This project implements a reddit tip bot which provides users an abstraction for a ITCO wallet. Users are given their own unique deposit address, and can send ITCO to other Reddit users by commenting on posts. The receiving user can then register with the tipbot via Reddit private message, and redeem their funds.
The goal of this is to foster the exchange of the ITCO cryptocurrency all throughout reddit.

## Installation
Edit settings.py.example with your own details for accessing the Reddit API and also the wallet ID for your ITCO node then rename the file to settings.py

## Running
Use the `launchScanners.sh` script to kill existing python processes, and start the two bots in the background.
`inbox_scanner.py` reads all incoming reddit mail to the bot to answer queries, and `comments_scanner.py` scans the entire NANO subreddit for mentions using `!tipitco`.

## Using
#### Tipping with the Bot in Comments
The TipBot currently scans for comments with the !tipitco syntax in r/itmf.

- !tipitco <username> <amount> will send a tip to the user in ITCO
- !tipitco <username> $<amount> will send a tip to the user in ITCO of the equivalent value in USD

- !tipitco <amount> will send a tip to the author of the parent comment/submission. If the tip is a top-level comment, the post submitter will receive the tip. If the tip is a reply to a comment, the parent comment will receive the tip.
- !tipitco /u/valentulus_menskr 0.01 will send 0.01 ITCO to /u/valentulus_menskr.
- !tipitco /u/valentulus_menskr $0.01 will send the equivalent of $0.01 USD in ITCO to /u/valentulus_menskr. The exchange rate is based on our ICO rates until they are available on exchanges and coinmarketcap.

The TipBot now accepts mentions as a valid method of tipping reddit-wide in any subreddit. Replace !tipitco with a mention of the bot to tip. To ease this process, an additional bot account with a very short name has been created. /u/itco4u is an alias for /u/itco_tipbot for tipping via mention. Example valid tipping formats:

- /u/itco_tipbot <username> <amount>
- /u/itco_tipbot <amount>
- u/itco_tipbot <username> <amount>
- u/itco_tipbot <amount>
- /u/itco4u <username> <amount>
- /u/itco4u <amount>
- u/itco4u <username> <amount>
- u/itco4u <amount>

#### Interacting with the Bot via Private Message
There are various commands accepted through private messaging the bot. In each message please include the command text in the body of message, otherwise the bot cannot parse your request.

- register will set up your account with the bot.
- help will respond with a list of commands available.
- balance will return your current account balance.
- address will return your current wallet address.
- send <amount> <ITCO address> will send the amount specified from your account to the specified address.

Deprecated commands are grandfathered in and able to be parsed. (i.e !balance or !address is still a valid command in a private message)

Depositing ITCO to Your TipBot Account
Use the address command in a private message to the bot to retrieve your deposit address. Send ITCO to this address and it will be available for tipping.

Retrieving Your ITCO Balance
In the commands section above, the send command was covered. Use that command to retrieve your ITCO balance by sending it to an external ITCO account address that you hold. For example:

- send 0.01 itco_3zhgmaoxc4gdypafmcqa5tuf3ad9w3d8g9mjutfcxbo8s1e78bu3qm6qjyqz will send 0.01 ITCO from your TipBot account to the specified address.
