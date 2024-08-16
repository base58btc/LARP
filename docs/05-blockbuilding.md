# Block Building - making block templates

We're getting close to a final working version of
the bitcoin network. We've got transactions. Let's
tackle the last piece of the puzzle: blocks.

Estimated Time: 10m


## Table of Contents

	* [Materials Used](#material-used)
	* [Building Your First Block Template](#building-your-first-block-template)
	* [Picking Transactions for a Block](#picking-transactions-for-a-block)
	* [Writing A Coinbase Transaction](#writing-a-coinbase-transaction)
	* [Filling in the Block Header](#filling-in-the-block-header)
	* [Calculating the 'tx commitment'](#calculating-the-tx-commitment)
	* [Ready to Mine for the Nonce](#ready-to-mine-for-the-nonce)
	* [In Sum](#in-sum)


## Materials Used

In this phase of the LARP, we'll use the following items:

	- block template envelopes
	- blank blockheader cards
	- one blank transaction card
	- ballpoint pens


## Building Your First Block Template

Instructor Script:

	Now that we've got transactions, let's build our
	first block template.

	ACTION: Hold up an empty block template envelope,
	so participants know what you're talking about.

	First we'll need to fill the block with transactions.
	There's limited space in each block, so we'll have
	to make some decisions about what gets included.

	Next, we'll want to make a coinbase transaction
	that will pay any miner fees from the transactions
	we've chosen plus the block reward to our own pubkey.

	Finally, we'll want to fill in the block header.


## Picking Transactions for a Block

Instructor Script:

	For our LARP, each block can fit a total of *four*
	transactions. This means we can pick *three* network
	transactions from our mempool to include in a block.

	Whoever builds the block will get to decide which
	transactions they should include.

	Let's pick out three transactions to put into our block
	template now.

	One thing to pay attention to is how much each transaction
	is paying you in fees. You get to keep those fees for yourself
	if your block gets mined.

	Another thing to pay attention to is the inputs to a transaction.
	If you include a transaction in a block but don't include the
	transaction that its inputs name, then your block won't be valid.

	ACTION: Allow nodes a few minutes to find three transactions
	and put them into their block template. Walk around and help
	nodes check that they know how much they're making in fees and
	that they're not forgetting to include a transaction.


## Writing A Coinbase Transaction

Instructor Script:

	Now that we've identified the transactions that go into
	our block, we're ready to make our coinbase transaction.

	You might remember from the Genesis Transaction how this
	works.

	Find a blank transaction card, and place a big X over
	the inputs section. Coinbase transactions don't have inputs.

	Also add a new transaction id onto this new transaction.

	ACTION: Pick up a blank transaction card from the nearest
	node, and draw a big X over the input section. Write
	a new transaction id onto it. Hold your coinbase transaction up
	so nodes can see what you've done.  If you have assistants,
	have them help the other nodes do this.

	Now we just need to figure out how much we can send ourselves
	in the coinbase. Find the lock that corresponds to your
	node's secret key and place this on the first output.

	ACTION: Place your own black lock on the output and hold it
	up so nodes can see + copy what you've done.

	Each block is worth 50 new bitcoin. So we'll at a minimum get
	50 new bitcoins in this output.

	If the transactions that you're including paid any fees to the
	miner, you should add this number to 50 to get the total amount.

	For example, if you have 3 transactions in the block and they each
	pay 1 bitcoin each in fees, the total amount that I can claim in
	the coinbase output is 53 bitcoin.

	ACTION: Write down 53 bitcoin onto the coinbase transaction example
	you're holding and hold it up for the nodes to see.

	Ok, everyone take a few minutes to finish filling in your coinbase.

	ACTION: Walk around and help each node fill in the coinbase transaction.


## Filling in the Block Header

A complete block header is what makes a valid block! In this
phase we'll have everything except one missing piece: the nonce
which will lock in the other data in the block header and make
turn our 'block template' into a valid and winning 'block'.

Instructor Script:

	Now that we've got a full block, we're ready to fill in
	the block header. This is the last step for building a block.

	ACTION: Hold up a Block Header card so nodes know what we're
	working on. Give them a moment to find one for themselves.

	The first field on the block header is the previous transaction
	hash. This creates a chain from one block to the next, and lets
	anyone who receives this block know what chain we're building on.

	We'll be building the first block in our blockchain off of the
	Genesis block. Let's see what the blockhash was for that block.

	ACTION: Pull out a Genesis Block, which you should have written
	the blockhash that you calculated in the very first phase onto.
	Read it off so everyone can write it onto their blockheader.

	The tx commitment we'll have to calculate. Let's come back to that.

	The time is currently <read time off phone/watch>. Let's put this
	down for the time.

	The current difficulty target is the same as the Genesis Block,
	or 8500*. Let's write 8500 into the target field.

	The last field is a nonce field. Finding a valid value for this field
	is difficult. We'll use our BASICS here shortly to try to calculate
	it for us.


## Calculating the tx commitment

Instructor Script:

	To figure out the tx commitment field, we're going to need a
	calculator and the transactions that you're including in the block.
	You might want to use the calculator on your phone.

	The tx commitment makes it such that a malicious node can't take a
	valid block and swap in new transactions. It commits to the transactions
	we've picked out for this block. That's why we call it a tx commitment.

	Our tx commitment is the sum of all of the numbers on the txids of
	the transactions inside our blocks.

	ACTION: Read off the transaction ids inside one node's block template.
	Have them use their calculator to add these up. Tell the class what
	the tx commitment is + have the node team put that number onto their
	tx commitment.

	ACTION: Have all nodes calculate and fill in the tx commitment on
	their block header. Some nodes may have the same tx commitment, but
	they should all be different, depending on what nodes chose for their
	coinbase txid.


_Protocol Note_: Astute participants and facilitators may realize that it's
quite easy to make a new transaction that reuses the same number from the
transaction id of the transaction you want to replace in a block. In the
bitcoin protocol, they use something called a Merkle Root, which is practically
impossible to swap a transaction out and get the same root.

We can't calculate a Merkle Root for the LARP, as it's a bit too complex. Instead
we use much simpler math.


## Ready to Mine for the Nonce

At this point, every node should have an almost complete block header.
They'll just be missing the nonce field.

This is the field that we'll need our BASICS for. We're ready for the mining
phase of the LARP!


## In Sum

In this portion of the LARP we've:

- Picked out transactions from the mempool
- Calculated the coinbase output value
- Written our own coinbase transaction
- Filled in almost all the fields on our block header
- Learned how to make a transaction commitment

We're now ready to start mining for blocks.
