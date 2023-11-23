# Setup

Before you start the LARP you'll need to do some prep work.

Estimated time:

- To build/put together node materials: 20m
- To assemble materials for each node: 10m

If it's your first time playing, you'll need more time to do initial setup.
A lot of the parts can be re-used thereafter.

You'll probably want to re-create the Genesis + First Network Transactions
every game though. This is the most time consuming part of the game.


## Table of Contents

  * [To Start](#to-start)
  * [Room Configuration](#room-configuration)
  * [Other Facilitators](#other-facilitators)
  * [Rewards for Nodes](#rewards-for-nodes)
  * [Materials for Each Node](#materials-for-each-node)
  * [Purposeful Mistakes](#purposeful-mistakes)
  * [Things to Build / Put Together](#things-to-build-put-together)
    * [Mempool + UTXO Baskets](#mempool-utxo-baskets)
    * [Block Templates](#block-templates)
    * [Genesis Transaction](#genesis-transaction)
    * [Genesis Blocks](#genesis-blocks)
    * [First Network Transaction](#first-network-transaction)
    * [Blockchain](#blockchain)
    * [Secret Key Cards](#secret-key-cards)

## To Start

To get started you'll need to put together the materials that
go in each original "bitcoin-core" download. Here's the materials
to put together for each node.


## Room Configuration

You'll need 6 tables that are approximately arm's length
(6' ft) apart from each other. Each table should have
enough chairs for 2-6 players.

A cafe table or banquet setup often works quite well.

## Other Facilitators

Running a LARP is a lot of new information and steps. We
highly recommend having assistants or experienced LARPers
(or Bitcoiners) at each table or so in order to help participants
not fall behind.

You can run it with a single facilitator, however we'd recommend
extending the amount of time allotted for each phase for additional
time to help each node complete the steps.


## Rewards for Nodes

There's two phases which are competitive in the game: [getting transactions
into mempools](docs/04-networking.md#goals-for-this-phase) and the final gameplay of [mining blocks](#docs/07-wrapup.md#achieving-our-goals).

You don't have to hand out Rewards but it definitely makes participating
more rewarding.


Here's some ideas of what to hand out:

- An additional miner for your node (mempool only phase)
- Candy or individually wrapped chocolates
- Stickers
- Satoshis over Lightning
- [Conference ticket](https://btcpp.dev) discount codes
- Vouchers for upcoming [Base58](https://base58.school) classes


## Materials for Each Node

Each node needs to receive the following materials.

I'd recommend placing all items inside one of the Plastic Baskets.

See the [Bill of Materials](../BOM.md) for what to get
and how to make each of the required parts.

	- 1 Plastic Basket labeled Mempool
	- 1 Plastic Basket labeled UTXO set
	- 5 Loose leaf binder rings
	- 1 Blockchain (Index Card Case w/ Genesis Block)
	- 10 Block Templates
	- 10 blank Block Header cards
	- 10 blank Compact Block cards
	- 30 blank Transaction cards
	FIXME: sticker page format?
	- 7 Key sticker pages (1 of each secret key color, plus black)
	- 7 Lock sticker pages (1 of each secret key color, plus black)
	- 1 Self-inking approved stamp
	- 1 Secret Key Card
	- 3 Ballpoint pents
	- 1 Dry erase marker
	- 1 Miner
	- 5 I Have Transactions network cards
	- 5 Send Transactions network cards
	- 5 I Have Blocks network cards
	- 5 Send Blocks network cards
	- 1 Transaction + Block Validation Checklist
	- 1 Node Scorecard

## Purposeful Mistakes

In the setup we create a number of errors. This allows for users to
learn how to spot mistakes and correct them.

List of given mistakes:

- the initial genesis coinbase transaction only spends 49, not 50 bitcoin
- the first network transaction is missing a signature


## Things to Build / Put Together

Using the materials from the [BOM](../BOM.md), you'll need to assemble the following items.

Note that both the [First Network Transactions](#first-network-transactions) and the
[Genesis Transactions](#genesis-transaction) get marked up and written on during
the LARP. It's recommended that you recreate a fresh set before every LARP.


### Mempool + UTXO Baskets

These are for transactions that your node has received, either from
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
	- pubkey: place a pink  lock sticker
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


### First Network Transaction

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
	- signature: leave blank
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

