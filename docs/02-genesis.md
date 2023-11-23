# Genesis: The LARP Begins

The first phase of the LARP is about unpacking what's in
the bitcoin-core software that your node has downloaded,
inspecting and verifying the genesis block and transaction.

This introduces us to blocks, transactions, coinbases,
validation, and the 'genesis' block.


Estimated time: 15m


## Table of Contents

  * [Materials Used](#materials-used)
  * [Unpacking bitcoin-core](#unpacking-bitcoin-core)
  * [The Genesis Block and Transaction](#the-genesis-block-and-transaction)
  * [Introduction to the UTXO set](#introduction-to-the-utxo-set)
  * [Identifying Our Outputs](#identifying-our-outputs)
  * [Verifying the Genesis Block Header](#verifying-the-genesis-block-header)
    * [The 'tx commitment'](#the-tx-commitment)
    * [Calculating the block hash](#calculating-the-block-hash)
  * [In Sum](#in-sum)


## Materials Used

In this phase of the LARP, we'll use the following items:

	- almost everything, but especially
	- the blockchain
	- the genesis block
	- the genesis transaction
	- the UTXO set basket
	- secret key card
	- the BASIC miner


Things we will *not* use in this phase of the LARP (but may go thru in our
node basket as part of [Unpacking bitcoin-core](#unpacking-bitcoin-core)).

	- the first network transaction
	- the string
	- scissors
	- network cards
	- the dry erase marker
	- network message headers (binder rings)
	- key + lock stickers
	- the self-inking approved stamp
	- pens
	- blank transactions
	- blank block headers
	- blank block templates
	- blank compact block cards
	- node scorecard
	- tx + block verification checklists


## Unpacking bitcoin-core

The first thing we do is take a tour through what's in
everyone's nodes. Typically we do this by unpacking the baskets
until we arrive at the final item at the bottom: the baskets
themselves.

Here's a rough list and explanation of each item. You should
read this out as you go through the items, holding them up one
by one as you take things out and put them on the table.

- *transaction cards*: These are the blank transaction cards
  we'll use to make new bitcoin transactions with.
- *loose leaf binder rings*: These are our network message
  headers. They let us send messages between nodes.
- *envelopes/block templates*: These are block templates.
  We'll use them to build new blocks.
- *blank Block Header cards*: these are blank block headers.
- *key + lock stickers*: These keys and locks  are for
  securing and spending bitcoin in transactions.
- *self-inking approved stamp*: We'll use this to mark
  transactions as validated.
- *pens*: No explanation, just take them out
- *dry erase marker*: This is for writing network messages.
- *miner*: This is our "BASIC" or 'Basic ASIC'. We'll use it
  to validate blocks and to mine new ones.
- *network cards*: These our are network cards, they let
  us send messages to other nodes on the network.
- *compact block txid cards*: Used for sending info about blocks
  to our peers over the network.
- *node scorecard*: For tallying node scores at the end.
- *tx and block verification checklists*: Useful for verifying
  data we receive over the network.
- *mempool + utxo baskets*: These are our baskets for
  transactions we get over the network.
- *secret key card*: This is your node's secret key.
  Don't tell anyone else what it is. It's how you'll
  identify coins that you can spend in the blockchain.
- *blockchain/index card holder*: This is our blockchain.
  Let's see what's inside.

Note: I recommend ending on the blockchain / index card holder as
the final item that you hold up to explain.

## The Genesis Block and Transaction

Instructor script for the genesis block exploration.

	Inside the blockchain you'll find a single
	block. We call this the 'genesis block'. It's included
	in every download of bitcoin-core. It comes with your
	bitcoin node.

	A block has a blockheader on the front and transactions
	inside of it. How many transactions are inside of this
	block?

	A: 1

	What's the transaction id of this transaction?

	A: eagle33

	How many inputs does it have?

	A: 0.

	Does anyone know why this transaction has zero inputs?

	A: It's a coinbase transaction. It's where new
	bitcoin enter the supply. For our game, every coinbase
	is allowed to create 50 new bitcoins.

	Let's look at the outputs on this transaction, the
	genesis transaction. How many outputs are there?

	A: 4 outputs

	Does the value of the outputs add up to 50?

	A: No, we're missing one.

	Where did that extra bitcoin go?

	A: It's just not added to the total bitcoin supply.
	The miner who made the coinbase transaction can add
	up to 50 bitcoins in the coinbase, but they dont' have
	to. There are some blocks in bitcoin where this happened.


## Introduction to the UTXO set

Next, we introduce the concept of keeping transactions that
are inside blocks (but unspent!) in the UTXO set.

Instructor script:

	This transaction is in a block. It's now considered
	'mined' or 'confirmed'. We put mined or confirmed
	transactions into one of the two baskets that we have.

	Which basket do you think a confirmed transaction
	goes in?

	A: the UTXO set

	Right, confirmed transactions go into the UTXO set
	until all their outputs have been spent, at which
	point we can put them back into their block envelopes.

	ACTION: Place the genesis transaction into the UTXO set
	basket. There should now be one transaction in the UTXO set.

	There is one transaction in our UTXO set. How many outputs
	are on that transaction?

	A: 4 outputs


_Protocol Note_: The first ever coinbase transaction in the
genesis block technically *isn't* included in the UTXO set.
Because it's not in the UTXO set, it's considered unspendable.
This was probably a mistake on Satohi's part, but we're keeping
things that way. The LARP game doesn't follow the protocol
exactly: we add our genesis transaction to the UTXO set, which
makes all of the outputs on it eligible to be spent in other
transactions.


## Identifying Our Outputs

Instructor Script:

	Every bitcoin node here should have received a wallet
	with a secret key in it. This is the card with a colored
	key on it.

	ACTION: Give nodes a few seconds to find their secret key
	color.

	We should be able to identify bitcoins which belong to our
	wallet by finding transaction outputs in the UTXO set which
	match your secret key. If you currently have bitcoin locked
	to your key, please raise your hand.

	NOTE: Only 4 of the 6 nodes will have bitcoin locked up in
	the UTXO set at this point.


This is pretty short, but an important way for people to start associating
their bitcoin balance as numbers in outputs in the UTXO set.


## Verifying the Genesis Block Header

We're changing topics here a bit, but this is the last task we have
for the 'genesis' portion of the LARP.

Instructor Script:

	Anytime we get a new block, we should verify that
	the blockheader is valid. We probably should have
	done this before we put any transactions inside it
	into the UTXO set, but that's ok.

	Going forward we'll verify the block header before looking
	at the transactions on it. For the genesis block it's ok
	to do things a bit out of order.

	To verify a block header, we'll need to calculate the
	blockhash. We'll need to use our BASICs for this.

	ACTION: Hold up a BASIC. Give nodes a moment to find theirs.

### The 'tx commitment'

Instructor script:

	Before we can use the BASICs however, we need to verify
	one of the pieces of information on the blockheader
	That's the 'tx commitment' field or transaction commitment.

	The purpose of this field is to make sure that the transactions
	inside the block actually belong to the block that the miner
	intended to build.

	For this LARP, our tx commitment is the sum of all of the numbers
	in the transaction id's from the transactions inside the block.

	What's the number from the txid that was in this block?

	A: 33 (the txid was eagle33)

	Does the tx commitment equal this?

	A: Yes, the tx commitment on the genesis block is 33.

	Now that we're confident the transactions in the block match the
	blockheader, we're ready to calculate the block hash.


_Protocol Note_: The actual 'transaction commitment' is a Merkle root
of all the block's transaction's ids. We don't have a quick and easy
way to build a Merkle root. Instead we just use some basic math.


### Calculating the block hash


Instructor Script

	Turn on your BASIC by sliding the switch on the side to the on
	position.

	Now we just need to type in the information from the blockheader
	and it will give us a blockhash.

	ACTION: Enter in the first field from the blockheader, the
	`prev block hash` into the BASIC. Press the '#' sign to
	advance to the next field to input.

	To enter a field, press the '#' (pound sign). If you make
	a mistake, you can delete digits by pressing the '*' key.

	Let's finish entering all of the information from the
	block header into the blockhash.

	ACTION: the blockhash should be shown on the screen at the end
	of entering all the data in. Write the shown blockhash onto
	the blockheader card, in the space to the  left of the
	"blockheader" title.

	ACTION: Give nodes some time to complete this, and write their
	hash down on the blockheader. Hold up an example card so everyone
	can see. Walk around and make sure everyone is getting the correct
	hash.

	What blockhash did everyone get for the genesis block?

	A: FIXME: find this

	Is this a valid blockhash?

	A: Yes.

	How do we know it's a valid blockhash?

	A: It's a number less than the `target` field on the blockheader.

	Right. The target gets updated every time we have a 'difficulty
	adjustment'. For now it'll stay at 8500.

	Ok. Since the blockhash is less than the target, we have a valid
	block.

	Let's write the hash of the block onto the genesis transaction, so
	we know which block this transaction came from. That'll make it easier
	to put the transaction back into the block envelope after all its
	outputs are spent.

	ACTION: Write the blockhash, FIXME, onto the back of the transaction
	in the UTXO set. Hold it up so other nodes can see what you've done.


## In Sum

In this portion of the LARP we've:

- Unpacked a bitcoin core node
- Found the first coinbase transaction
- Identified the parts of a transaction
- Introduced the UTXO set
- Discovered each node's secret key
- Found UTXOs that belong to our key in the UTXO set
- Verified a block header using the BASIC

We're now ready to move on to validating and writing transactions.
