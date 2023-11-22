# Transactions: Validating + Writing

We've now had a whirlwind introduction to blocks and transactions.

Let's slow down a bit and spend some time validating and writing
our own transaction from scratch.

Estimated time: 15m


## Table of Contents

  * [Materials Used](#materials-used)
  * [Network Transactions](#network-transactions)
    * [Inputs](#inputs)
	* [Outputs](#outputs)
	* [TXIDs](#txids)
	* [Valid Transactions](#valid-transactions)
  * [The Mempool](#the-mempool)
  * [Wallet Balance Check](#wallet-balance-check)
  * [Writing Transactions](#writing-transactions)
    * [Change Outputs](#change-outputs)
	* [Transaction Fees](#transaction-fees)
  * [Adding Transactions to the Mempool](#adding-transactions-to-the-mempool)
  * [In Sum](#in-sum)


## Materials Used

In this phase of the LARP, we'll use the following items:

	- the first network transaction
	- blank transaction cards
	- the self-inking approved stamp
	- key stickers
	- lock stickers
	- ballpoint pens
	- the mempool basket


## Network Transactions

Instructor Script:

	Now that we've gone through everything in our bitcoin
	core node download, we're ready to start getting network
	traffic. Let's say that all of our nodes are now ready and
	online and they've gotten their first incoming transaction
	from a 'ghost' node (me, the facilitator).

	ACTION: Walk around to every node and hand them the
	[First Network Transaction](01-setup.md/#first-network-transaction).

	When you get data in from over the network, you need to verify
	it. This is because you don't know what you've been sent.

	Don't trust, verify.

	There's a few steps to verifying a node. Let's go through them
	together.


### Inputs

A bitcoin input points to a bitcoin output. Here we'll learn how to
find outputs that an input is spending.

Here we run into our second [intentional mistake](#purposeful-mistakes): the first
network transaction is missing its signature.


Instructor Script:

	For a bitcoin transaction, we need to know how much bitcoin
	we have available to spend in its outputs. To do this,
	we look at the 'inputs' of a transaction.

	How do we know how much a bitcoin input is worth?

	A: ... (let nodes guess)

	Is it written on the transaction input field?

	A: No, it is not.

	Ok, where can we go to find out how much an input is worth?

	A: the output that it 'points' to.

	We can find the output that this input is spending by using
	the transaction id and output number listed in the input.

	For this first network transaction, it says that we're spending
	from transaction 'eagle33' and output number zero.

	Where can we see how much output zero on the 'eagle33' transaction
	is worth?

	A: Find the output in the UTXO set.

	How much is the eagle33, zero'th output worth?

	A: 25 bitcoin

	Ok, so we have 25 bitcoin to spend in this transaction's outputs.

	There's one more thing to verify before we move onto outputs:
	is the signature on this transaction valid?

	It looks like I made a mistake on this transaction: I left the signature
	off. Typically when we get transactions with errors or problems from
	the network, we just throw them away. But for this one, let's make an
	exception and go ahead and sign for this input. We'll use the key
	stickers to stand for a signature, since it's unlocking the lock
	we put on the output we're spending.

	Which color key sticker should I use for this input's signature?

	A: the green key

	ACTION: Have nodes put green key sticker on the signature field for
	the first input on transaction 'cat72'.


### Outputs

Instructor Script:

	We have 25 bitcoin to spend in the outputs of this transaction.
	How many bitcoin are we locking up in the outputs of this transaction?

	A:  24

	We had 25 to lock up, and we're locking up 24. Where does that extra 1 bitcoin
	go to?

	A: It's available for the miner to take as fees.

	Let's write this fee amount on the back of transaction. It'll be useful
	later when we start building our own blocks.


### TXIDs

Instructor Script:

	The last thing to check on a transaction is that it has a good
	transaction id. For this game, the transaction id, or txid, must be a
	word plus a two digit number.

	Is the txid on this transaction ok?


_Protocol Note_: Transaction ids are calculated from the transaction data
itself and uniquely identify that transaction. This is done using a SHA256
hash of a transaction's contents. We don't have an easy way to hash transaction
data so instead we just pick a random one. If students pick the same txid,
you will run into problems. This may be fine, or not, depending. Generally
I let chaos + problems run for a bit, so partcipants can experience the
downsides of certain protocol choices (like allowing there to be duplicate txids).

There have been two cases of duplicate transaction ids in the protocol. This
happens when the coinbase transactions are identical. The protocol was changed
so that this is no longer possible. See [BIP30](https://github.com/bitcoin/bips/blob/master/bip-0030.mediawiki) for more details.


### Valid Transactions

Instructor Script:

	If this transaction is valid we should mark it as such. Let's do
	that.

	ACTION: Take the self-inking Approved stamp and mark this network
	transaction Approved


## The Mempool

Instructor Script:

	Now that the transaction is marked as Approved, and only once
	a transaction is marked as approved, we're ready to put into
	the Mempool.

	The mempool is a holding pen for transactions that are waiting
	to go into a block. It's the set of transactions that are valid
	but unconfirmed.

	Mempools have a strict size, if you get too many transactions
	you can start throwing some of them away.

	When a block gets mined transactions get promoted from the
	mempool to the UTXO set. This opens up space for new transactions
	in the mempool (if it was full).

	ACTION: Place first network transaction into the mempool


## Wallet Balance Check

Instructor Script:

	We've now got one confired transaction in the UTXO set and one
	transaction waiting to be confirmed in the mempool.

	Looking across both the confirmed and unconfirmed transactions,
	raise your hand if you've got bitcoin locked up to your
	secret key.

	NOTE: Every node should raise their hand at this point.

	Great. We're ready to write our own first transaction.


## Writing Transactions

Each node will write a single transaction for their whole group.
As a gameplay note, at this point members of nodes should start
to take different roles in doing tasks etc. It's useful for successful
node operation that this happens (everyone does different work
to help the node run).


Instructor Script:

	Now that we've validated our first transaction, we're ready
	to write a new one.

	We'll need a blank transaction card for this. We'll also
	need to have an output that we can spend with our private
	key.

	ACTION: Pick up a blank transaction card and hold it up,
	also pick up the genesis transaction out of the UTXO set
	and hold it up so everyone can see.

	Let's write our first transaction.

	First we'll need a txid. Pick a random txid for this transaction.

	ACTION: Nodes write down a txid.

	After you've chosen a txid, you'll need to fill in information
	for the output that you're spending. It's fine to spend unconfirmed
	outputs (from transactions in the mempool).

	ACTION: Nodes add txid and output number of output they're spending.
	Walk around and make sure they're doing the right thing.

	Finally, you'll need to make some outputs. For this transaction,
	you're all paying me one bitcoin, as payment for this LARP.

	To send me bitcoin, you'll need to know my bitcoin address.

	ACTION: Walk around and hand every node a black lock sticker.
	(Your private key is the black key sticker.)

	ACTION: Nodes should add an output of amount 1 and
	with the black lock sticker as the pubkey.


### Change Outputs

In bitcoin, if there's bitcoin left over after you've sent money
to the lock that you wanted to, you need to create a change output.

It's sometimes amusing if nodes forget to add a change output, as they
discover very quickly that that money ends up going to the miner.

If you want to cause some chaos, you can omit this section in your
instructions.

Instructor Script:

	We had how many bitcoin that we were originally spending?

	A: 8 bitcoin

	And now you're sending 1 bitcoin to me. Where are the rest
	of the bitcoin going?

	A: To the miner, currently.

	If we wanted to not send all of that 7 bitcoin to the miner,
	how should we prevent that?

	A: by making another output

	Where should we send the bitcoin in that other output?

	A: Anywhere you want! But most likely back into your own wallet

	Note that for the LARP, we're only going to use whole number,
	no decimals.

	ACTION: Nodes add a change output to their transaction and lock
	it to the lock sticker that matches their secret key card.


### Transaction Fees

It's also sometimes amusing if nodes forget to include a miner fee,
but only if some of the nodes remembered. This makes it easier for
nodes that are building blocks to make decisions about what transactions
to include in their block (hint: usually the low fee ones)

I wouldn't force this situation to occur, but it is nice when it happens
naturally.

Instructor Script:

	Remember that you're probably going to want to leave out some bitcoin
	for the miner, otherwise they might not include your transaction in a block.


## Adding Transctions to the Mempool

Instructor Script:

	Now that we've gotten our transaction written, we need to add it
	to our mempool. That will kick off the process of sending it out
	across the network.

	Before we can put *any* transaction, our own included, into the mempool
	we have to verify it first.

	Let's verify this transaction.

	Does it have a valid txid?

	ACTION: Nodes check if transaction they just wrote has a valid txid (must
	be a word then a two digit number, such as 'hello11' or 'jet89')

	Does it have a valid input. That's one that's listed in either the
	mempool or the UTXo set. It also needs to be signed.

	ACTION: Nodes check that their input is ok.

	Finally we can't lockup more bitcoin in the outputs than we had
	available to spend in the inputs.

	ACTION: Nodes double check their amounts.

	If all of those checks pass, mark your transaction as valid and put it
	into the mempool.

	ACTION: Use self-inking Approved stamp to mark transaction we just
	wrote as approved, and place it in the mempool. Everyone's mempool
	should now have two transactions into it.


## In Sum

In this portion of the LARP we've:

- Received our first 'untrusted' transaction
- Validated the transaction
- Observed how inputs value comes from a different transaction's output
- Learned what the mempool is for
- Written our first transaction
- Made a change output
