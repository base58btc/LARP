# Bill of Materials

These are the materials needed to build a LARP gameset.

All counts are for a 6-node LARP gameset. 


## Raw Materials

Here's all the things you'll need to buy to build a LARP gameset.

| Item                           | Used For               | Count     | Source                                                               | Source (Europe)                                      |
|--------------------------------|------------------------|-----------|----------------------------------------------------------------------|------------------------------------------------------|
| Plastic Baskets                | mempool + utxo set     | 12        | https://www.amazon.com/gp/B08DN975X2                                 | https://www.amazon.de/-/en/dp/B087CGN9VM/            |
| Loose leaf binder rings        | wire messages          | 30        | https://www.amazon.com/gp/B08FHJP4S8                                 | https://www.amazon.de/-/en/dp/B01B7O6JH0             |
| 3 x 5” Index Card Case         | blockchain + wallet    |  6        | https://www.amazon.com/gp/B07W14RLQV/                                | https://www.amazon.de/-/en/dp/B09C8628ZP             |
| Ballpoint pens                 | writing                | 18        | https://www.amazon.com/gp/B00006IE78/                                | https://www.amazon.de/-/en/dp/B002TVXOQA/            |
| Dry erase markers              | writing (network msgs) | 6         | https://www.amazon.com/dp/B09NXDCCTZ/                                | https://www.amazon.de/-/en/dp/B08ZJ12PVL/            |
| Self-inking approved stamp     | approving txs          | 6         | https://www.amazon.com/dp/B08W3M9MTK                                 | https://www.amazon.de/-/en/dp/B0738LVR6T/            |
| String                         | network                | 1         | https://www.amazon.com/dp/B0BJ6R38851                                | https://www.amazon.de/-/en/dp/B08NJV3LH1             | 
| A1 Envelopes                   | blocks                 | 60        | https://www.amazon.com/dp/B01N019WJY                                 | https://www.amazon.de/-/en/dp/B09686DPGK             |
| Plastic card holders           | blocks                 | 60        | https://www.amazon.com/gp/B0B8S74R5M                                 | https://www.amazon.de/-/en/dp/B0BNGTLMPG             |
| Block Header Cards             | blocks                 | 120       | https://www.canva.com/design/DAFzVGRJh-s/4WPC0fIUWMn50sJQNgXg2w/edit |                                                      |
| Key + Lock Stickers            | txs                    | 72        | TBD                                                                  |                                                      |
| Glossy Cards (need hole punch) | network mesg           | 30 each   | https://www.canva.com/design/DAFzQuQt36E/i4_smxo7mxfpyMrcoXhmwQ/edit |                                                      |
| Miners (order with shell!)     | mining                 | 6         | https://www.aliexpress.us/item/3256803403391540.html                 | https://shop.lnbits.com/product/bitcoin-lnpos-device |
| Scissors                       | network                | 1         | https://www.amazon.com/dp/B00D05BJDE                                 | https://www.amazon.de/-/en/dp/B0B1HC9KJC             |
| Transaction Cards              | transactions           | 600       | https://www.canva.com/design/DAFzVIzt80M/MC3A4psOfR4z52KZIruZTg/edit |                                                      |
| Labels for Mempool + UTXO set  | mempool                | 6 each    | https://www.canva.com/design/DAFzVBZtcYw/cQMC9BBufOjgU2rveR22Tg/edit |                                                      |


You can optionally get a private key set made, or make one using the backs of transaction cards and key stickers.

### Optional Items

| Item             | Used For               | Count      | Source                                                               |
|------------------|------------------------|------------|----------------------------------------------------------------------|
| Secret Key Cards | wallet                 | 12         | https://www.canva.com/design/DAFzVaFo2sE/2PbUFUmpkVw2wzx7ZLMgfQ/edit |


## Things to Build / Put Together

Using the above, you'll need to assemble the following items.

### Mempool + UTXO Baskets

These are for transactions that your node has recieved, either from
the network or inside a block.

They need to be labeled before playing.

FIXME: Photo of baskets!

#### Materials Required

You should have the following

- 12 Plastic Baskets
- 6 Mempool Stickers
- 6 UTXO set Stickers


#### Steps

For each basket:

1. Place 1 Sticker in the middle bottom of the basket


### Block Templates

Every block will be constructed with a block template and a block header.

You'll need to put the block templates together. 

FIXME: picture of an empty block template

#### Materials Required

You should have 60 of the following

- Plastic Card Holders
- A1 Envelopes

#### Steps

For each block (60):

1. Remove the plastic card holder from the paper backing
2. Place the plastic card holder onto the front of an envelope,
   opening pointing up towards the top of the envelope


### Genesis Transaction

The Genesis transaction goes inside of the Genesis Blocks. It's the
first ever bitcoin transaction. It's also a coinbase transaction.

FIXME: picture of a genesis transaction.

#### Materials Required

- 6 blank transaction cards

#### Steps 

For each node (6), do the following.

1. Take a blank transaction card
2. Write "eagle33" as the txid
3. Write a large X over the inputs section.
4. Fill in the outputs with the following
	#0
	- amount: 25
	- pubkey: place a green lock sticker
   #1
    - amount: 8
	- pubkey: place a blue lock sticker
   #2
	- amount: 8
	- pubkey: place a pink  ock sticker
   #3
	- amount: 8
	- pubkey: place a yellow lock sticker


### Genesis Blocks

Each node starts with a blockchain with one block in it. This is
the first block in the blockchain. It's also known as the genesis block.
Satoshi Nakamoto mined it and then put it inside bitcoin-core. (Hardcoded it).

FIXME: photo of a completed genesis block

#### Materials Required

We'll need the following materials to build genesis blocks for each of the nodes.

- 6 Genesis Transactions
- 6 Block Templates
- 6 Block Header Cards


#### Steps

For each node (6), do the following:

1. Place the Genesis Transaction inside the 
   Block Template envelope.
2. On the Block Header Card, write the following:
	- prev block hash: 000000
	- tx commitment:   33
	- time:            12:34
	- target:          8500
	- nonce:           FIXME ???
3. Place the filled in Block Header Card inside the
   Plastic Card Holder on the front of the block template.


### First Transaction

After we've introduced the node components, we'll pass out a 'first network transaction'.

Here's generally how it's constructed. Feel free to use different amounts, but make
sure the transaction is still valid.

FIXME: picture of a first transaction.

#### Materials Required

- 6 blank transaction cards

#### Steps

For each node (6), do the following.

1. Take a blank transaction card
2. Write "cat72" as the txid
3. Fill in the input with the following:
    - transaction id: "eagle33" 
	- #: "0"
	- signature: place a green key sticker
4. Fill in the outputs with the following
	#0
	- amount: 8
	- pubkey: place a green lock sticker
   #1
    - amount: 8
	- pubkey: place a purple lock sticker
   #2
	- amount: 8
	- pubkey: place a red lock sticker


### Blockchain

A blockchain is a file folder full of blocks.

#### Materials Required

- 6 Genesis Blocks
- 6 3 x 5" Index Card Case

#### Steps

For each Index Card Case

1. Place a Genesis Block inside


### Secret Key Cards

If you didn't get the pre-printed ones, you can make secret key cards.

FIXME: photos of secret key cards!

#### Steps

1. Take 6 transaction cards
2. Turn them over to the blank back side
3. Put one key sticker on each card. You should end up with the following.
	- 1 Blue secret key card
	- 1 Green secret key card
	- 1 Yellow secret key card
	- 1 Pink secret key card
	- 1 Purple secret key card
	- 1 Red secret key card

