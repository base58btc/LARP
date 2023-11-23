# Mining - building the chain

This is the final phase of the LARP, and can last
as long as participants remain interested. It's also
the most chaotic and difficult to manage, as the power
of decentralization really starts showing up.

We'll be learning how to mine for blocks, send blocks
around the network, and validate them when you receive
them.

Estimated Time: 30 to 40m


## Table of Contents

	* [Materials Used](#materials-used)
	* [Goals for This Phase](#goals-for-this-phase)
	* [Mining for Nonces](#mining-for-nonces)
	* [Broadcasting a Valid Block](#broadcasting-a-valid-block)
	* [Requesting a Block From a Peer](#requesting-a-block-from-a-peer)
	* [Validating a Block](#validating-a-block)
      * [Validating Block Transactions](#validating-block-transactions)
	  * [Marking Outputs as Spent](#marking-outputs-as-spent)
    * [Building a Chain](#building-a-chain)
	* [In Sum](#in-sum)

## Materials Used

In this phase of the LARP, we'll use the following items:

	- the BASICs
	- block templates
	- ballpoint pens
	- compact block txid cards
	- all the network cards
	- dry erase marker
	- block validation checklist
	- supplies to copy transactions
		- ballpoint pens
		- blank tx cards
		- lock stickers
		- key stickers


## Goals For This Phase

In this phase, we make two goals. The first is who
finds the most blocks, which is mostly a matter of luck.

The second is who has their blocks in the most blockchains,
which depends on how well connected a node is and how
active everyone else is about sending out new blocks
as they're found.

Instructor Script:

	We're ready to start mining, but before we do I want to
	give everyone a few goals. The first is that you want
	to be the node to find the block, but that block isn't
	worth very much if the network doesn't agree on what the
	blockchain looks like.

	Once you find a winning block hash, you'll want to quickly
	start sending it out over the network.

	The node that has the most blocks in other peer's blockchains
	will be the winner for this phase of the LARP.


## Mining for Nonces

A nonce is the data you change in a blockheader that changes the
hash result you get. The BASICs will auto-hunt for a winning nonce
for you.

Instructor Script:

	We're ready to use our BASICs to look for a winning block
	hash. To do this, we need to find a nonce that, along
	with the other information on the block header gives us
	a block hash that is underneath the target.

	What is the number that a winning blockhash must be under
	for this block?

	A: 8500 (hint: it's written on the blockheader already, as the target)

	Let's type our blockheader information into the BASIC and let
	it find a winning nonce for us. This might take a few minutes.

	ACTION: Walk through typing in the numbers for one of the
	nearest nodes. When you get to the nonce screen, say the following:

	For the nonce, since we don't know it, just leave it blank and
	advance to the next screen.

	ACTION: Have nodes type in the data from the blockheader on
	their block template into their BASIC. The '#' key will advance
	to the next screen. The '*' key will delete characters.

	When your BASIC finds a winning nonce it will stop looking and
	show it to you on the screen. Write this down on your block template
	before advancing to the next screen on the BASIC, which should show
	the block hash. Write this down as well onto the blockheader, above
	the word "blockheader".

	How will you know that a blockhash is a valid one?

	A: It will be a number less than the block target.

	When your block finds a valid nonce, please raise your hand
	and we'll all walk through how to broadcast a block.

	ACTION: Wait until a node raises their hand. Walk around and
	help nodes get their BASICs running.


## Broadcasting a Valid Block

Depending on the nonce-gods, within a few minutes to seconds you should have
a winning blockhash found.

For this section, we're going to let the first, winning block propagate
across the entire network before we resume looking for the next block.

Instructor Script:

	Ok, we've found our first winning block. Let's pause for a moment
	and go through how to broadcast a block across the network.

	Make sure you've filled in the blocktemplate with the information
	from the BASIC, particularly your nonce. You'll need the blockhash
	to tell your peers about your block.

	The first thing a node with a new block should do is notify all
	of its peers that it has a winning block. To do this, we'll need
	the I Have Blocks network message.

	Put the blockhash onto this message and send one to each of your peers.

	ACTION: wait for peers to receive the I Have Block message. This should
	be two to three of the other nodes; so two or three nodes depending on your
	network should have received nothing.


## Requesting a Block From a Peer

Learning how to broadcast blocks can be a bit tedious, and will use all
of the skills that we've learned so far in the LARP.

If any other node finds a winning blockhash while we're doing this, tell
them that it's invalid and they'll have to wait to build on top of this
current block.

Everyone should be working to get this first block broadcast across the
network before building the next block.

Instructor Script:

	I Have Block messages work almost identically to I Have Transction
	messages. If you don't have the blocks listed on the message,
	you should request them.

	Fill in a Send Blocks message and send it back to the peer that
	sent you the I Have Blocks card.

	ACTION: wait for messages to start arriving back at the node that
	found the first block.

	To send a peer a copy of a block, you'll need to make a copy of your
	winning block.

	How this works is you'll want a new block envelope and block header
	card. Fill in the block header card with all the data from your block.
	Leave off the block hash that you calculated though. Put this into
	the pocket on the block you'll be sending to your peer.

	ACTION: Help winning node fill in new blockheader for the block
	copy.

	First you'll make a copy of the coinbase transaction, and put
	this inside the block copy.

	ACTION: Wait for winning node to make a copy of the coinbase
	transaction.

	We're going to use the Compact Block protocol to send blocks across
	the network. This saves us a lot of work of having to also send
	copies of transactions.

	To do this, we'll use the Compact Block cards. We'll put the txids
	from all of the transactions in the block onto the card, and
	then place that inside the block copy.

	ACTION: Help winning node fill in the Compact Block card and place
	in block copy.

	Ok we've made our first block copy. We're ready to send it to a peer
	that requested it.

	ACTION: Send the block copy over the wire to one of the nodes that asked
	for it.

	ACTION: Have winning node make copies for ALL of the rest of the nodes.
	This will let everyone validate the block at the same time.

	ACTION: Distribute the block copies to all the nodes, even the
	ones that didn't hear about it originally.


## Validating a Block

Let's make sure our block is valid!

Have nodes use the Block Validation checklist card to follow along,
checking off items with their dry erase marker.

Instructor Script:

	Once your node receives a new block from over the network we'll
	need to validate that it's got the right information inside of it.

	We've speeded things up a lot so that we can all walk through
	validating a new block together. Normally you'd have to wait for
	your peer to tell you about a block before you got a copy of it.

	Let's go through the process of block validation together.

	First, we'll want to check that the block has a valid blockhash.

	We'll use our BASICs to do this.

	ACTION: Punch in data from the blockheader into the BASIC.

	My BASIC says that the blockhash for this block is <read out blockhash>.

	Is this a valid blockhash?

	A: Yes

	How do you know?

	A: Is less than the target.

	OK let's check that the transactions in this block are valid.

	ACTION: Have nodes pull out the coinbase transaction and Compact
	Block from inside the block.

	In this block, we got a coinbase and a Compact Block. We'll need
	to make sure we have all the transaction info before we can
	finish verifying this block.

	Let's finish verifying the blockheader. We need to check that the
	tx commitment is correct. Let's add up all the numbers from the
	txids in the Compact Block card and the coinbase. Do they equal
	the tx commitment?

	ACTION: Wait for nodes to calculate, should say yes.


### Validating Block Transactions

Making sure the block has valid transactions is probably the most
labor intensive part of this. If a node is missing a transaction
they'll have to use network messages to ask for it from their peers.

Instructor Script:

	Next we need to make sure the block has valid transactions.

	To do this we'll need an actual copy of each of the transactions in
	the block. Using the list of transactions on the Compact Block,
	look through your mempool for each of the listed transactions.

	If you don't have a transaction listed, you'll need to request it
	from your peers using the Send Transaction message.

	ACTION: Help nodes find/get the copies of the transactions that they
	need.

	Ok everyone has the transactions they need to validate this block.

	If you aren't able to find the transactions or if one of the transactions
	is already in the UTXO set, this block is valid and you can discard it.

	This is a valid block though, and everyone has the transactions they need.

	Let's first check the coinbase transaction. It should have no inputs,
	a valid txid, and the output value should be less than or equal to
	50 plus whatever fees the tranactions pay.

	How many fees do the other trasaction in the block pay?

	A: <varies, depending on game>

	How much bitcoin is in the outputs of the coinbase transaction?

	A: <varies, should be equal to 50 + fees from previous question>

	Great. This is a valid coinbase transaction.

	If the transactions are ones you've already approved you don't have to
	reverify them. This is one nice thing about having transactions
	in your mempool -- they're already validated!

	One last thing to check for the transactions in a block is
	that they all spend from either UTXOs or from other transactions
	in the same block.

	If any transaction in the block lists as an input a txid that isn't
	also in that block or in the UTXO set, that *entire* block is invalid.


### Marking Outputs as Spent

Instructor Script:

	Now that we know this block is valid, we have one final task
	to do before we're able to consider this block part of our blockchain.

	We need to promote all of the transactions that were inside the block
	from the mempool into the UTXO set.

	We also need to cross out any inputs that got spent in this block.

	Find the output that every input in this block spends, and mark it out.

	Once an output is spent, it is removed from the UTXO set and
	cannot be spent again.

	Any new outputs that were created in this block get added to
	the UTXO set.

	ACTION: Have nodes mark out spent outputs and place new transactions
	into the UTXO set basket. This includes the coinbase transaction.

	Ok finally, we can add this block to our blockchain.

	ACTION: Place new block into blockchain (Index Card Case) along
	with the Genesis Transaction.


## Building a Chain

Alright. We're finally ready to build a blockchain.

Instructor Script:

	We've finally completed the entire lifecycle of a transaction and
	adding new blocks to the bitcoin chain. We're only one block
	in though.

	Let's try to find the next block.

	For everyone who *didn't* win this block, you'll need to update
	your block template.

	Throw away the blockheader and start over, this time using the
	blockhash from the most recent block you received, and update
	the time to now.

	You'll also need to pull out any transactions that got mined
	in the last block. You may have new space, so you should find
	some new transactions from the mempool to add to it.

	Don't forget to update the coinbase transaction if the fees
	change and recalculate the tx commitment on the blockheader.

	Once you have an updated block template, punch the blockheader
	data into the BASIC and cross your fingers.

	May the luckiest miner win!

	ACTION: Turn gameplay over to the nodes. They should now know
	how to mine for blocks, build headers etc.

	ACTION: End gameplay after a few blocks or when node participants
	start losing interest.

## In Sum

In this portion of the LARP we've:

- Used the BASICs to find a winning nonce
- Broadcast a transaction to peers
- Validated a new block
- Learned how the Compact Block protocol works
- Promoted transactions from the mempool to the UTXO set
- Built a blockchain

Congrats, you did it! You made the Bitcoin blockchain come to life.
