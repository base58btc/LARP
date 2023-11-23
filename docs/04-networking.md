# Networking - peer to peer

Bitcoin is a distributed peer to peer network.

In this phase of the LARP, we'll build a real peer
to peer network and start exchanging peer messages.

Estimated time: 30m+


## Table of Contents

  * [Materials Used](#materials-used)
  * [Getting Connected](#getting-connected)
  * [Goals For This Phase](#goals-for-this-phase)
  * [Sending Network Messages](#sending-network-messages)
  * [Receiving Network Messages](#receiving-network-messages)
    * [Steps for Validating a Transaction](#steps-for-validating-a-transaction)
  * [Letting the Network Run](#letting-the-network-run)
    * [Common Mistakes and Issues](#common-mistakes-and-issues)
  * [Checking Global Mempool State](#checking-global-mempool-state)
    * [Who Has the Most Txs?](#who-has-the-most-txs)
    * [Who's Transaction Is In The Most Mempools?](#whos-transaction-is-in-the-most-mempools)
  * [In Sum](#in-sum)


## Materials Used

In this phase of the LARP, we'll use the following items:

	- string
	- scissors
	- network cards
	- loose binder rings
	- dry erase marker
	- supplies to copy transactions
		- ballpoint pens
		- blank tx cards
		- lock stickers
		- key stickers

## Getting Connected

Before you begin this phase, find the string and scissors.

Instructor Script:

	So far we've been making transactions for our own local nodes.
	But Bitcoin is a peer to peer network. This means that any
	transactions or blocks are in our node as well as in other
	nodes.

	You'll notice that right now everyone's mempool only has
	a transaction that they wrote themselves. This isn't very
	useful for anyone -- we need other nodes to be able to mine
	and include your transaction.

	To do this we're going to need to get everyone's nodes
	connected. The way bitcoin does this is they talk to
	a preset list of known nodes, who then tells them
	who else to connect to.

	In this example, I'm just going to connect you all.

	ACTION: Using the string and scissors, create connections
	between all of the node tables. Ideally, each node
	will have two strings that come to their table,
	at a maximum any one node will have three.

## Goals For This Phase

Sometimes it's useful for players to have short term goals,
otherwise all the actions that they're taking start losing focus.

In this phase, we make sending + receiving transactions and
adding them to your mempool goal oriented.

Instructor Script:

	We've got transactions in our mempool. We need to get
	the transaction in our mempool into the mempool of
	every other node on the network.

	By the end of this phase, every node should have
	7* transactions in their mempool.

	NOTE: number of transactions in each mempool
	will be equal to the number of nodes playing plus
	one, for the First Network Transaction.

	There are two ways you can 'win' this round of the
	LARP. You can either be the node that has their
	transaction into the mempool of the most other nodes.

	Or you can have all the transactions in your mempool.

	Does everyone understand the goal?

	Let's start sending network messages.


## Sending Network Messages

Let's send some messages around!

Instructor Script:

	Each node has four network messages. They're the
	- I Have Transactions message
	- Send Transactions message
	- I Have Blocks message
	- Send Blocks message

	For moving transactions around we'll only use the Transaction
	messages.

	The network messages work as follows.

	As soon as a new transaction lands into your mempool,
	you should send out a new I Have Transactions message
	to all the nodes you're connected to, letting them
	know *all* of the transactions in your mempool.

	Let's make one for this first node.

	ACTION: Pick a node at random and walk near their table.
	Pick up both transactions from the mempool: the
	First Network Transaction and the transaction that node
	made for themselves.

	This node has two transactions in their mempool.

	ACTION: Read off the two txids of the transactions.

	They need to let their peers know about the transactions
	in their mempool.

	ACTION: Take an I Have Transactions card and write the
	txids for both transactions onto the card, using the
	dry erase marker. Hold this up so everyone can see.

	Ok, now I need to send my I Have Transactions card to
	all my peers.

	ACTION: Take a loose binder ring, attach the Network
	Card to it. Put the binder ring onto any string
	that the node you've chosen has the end of, and
	send it down the wire to the node that's holding the
	other end of the string.


## Receiving Network Messages

Getting a network message often requires a node to do
some work.

Instructor Script:

	ACTION: Walk over to the other node that's received
	the message. One of the players at this table should
	now be holding the message.

	Once you've received a network message, you should
	look to see if you already know about the transactions
	listed.

	Are there any transactions on the list on the network
	message that you're unfamiliar with?

	A: Yes, the <txid of transaction the first peer made>.

	NOTE: They should already have 'cat72' in their mempool.

	Ok. We should ask this peer to send us this transaction.
	We do this by sending them back a network message.
	This time you'll send the Send Transactions message.

	ACTION: Help the receiving peer put the txid for the
	transaction they're missing onto the Send Transaction
	card + send it back over the same wire to the peer that
	they just got the I Have Transaction message from.

	ACTION: Wait for the peer to receive the message and
	get it off the wire.

	When you receive a Send Transaction message, if you
	have this transaction, you should make a copy of it
	and then send it over the wire to the peer to the
	node that requested it.

	ACTION: Have node make a copy of the transaction
	out of their mempool and send it over the wire
	back to the other node.


## Receiving a Transaction From the Network

In the last phase, we learned how to validate transactions
that we received from the network. We'll need to repeat
those steps for every transaction we receive.

### Steps for Validating a Transaction

- Does it have a valid txid? word + two digit number
- For each input:
	- Can you find the corresponding output in the
	  mempool or utxoset?
	- Does the signature match the lock?
- For the outputs:
	- Is each output locked with a colored lock?
	- Is the total amount in the outputs less than
	  the total amount in the inputs.
- Write the total amount of fees on the back of the transaction
- If this transaction passes all the checks, mark it
  Approved + place it into the mempool
- If this transaction DOES NOT pass all the checks, tear
  it up + discard it

Insctructor Script:

	ACTION: Walk back to the node that's received the
	transaction. Have them walk through the validation
	process again. As a reminder, see above for what the
	process should be.

	Note that once you've validated a new transaction and
	put it into your mempool, you should notify all of your
	peers about what your current mempool set is.

	This means sending out a new I Have Transaction message
	for each peer, with a list of all the transactions
	in your mempool.


## Letting the Network Run

It's time to let the other node start repeating the process,
making the network come alive with messages and each of the
nodes getting busy with the work of sending out and responding
to messages.

Everyone has seen an entire cycle of telling about
transactions, asking for transactions, copying a transaction,
and sending it to their peer. It's their turn now.

Instructor Script:

	ACTION: Instruct the nodes to start sending out I Have
	Transaction messages and responding to peer requests.

	ACTION: Give nodes 5-8m to work on sending and receiving transactions.
	Walk around and help nodes that are having trouble.

	ACTION: After 5-8m, pause the game so each node can
	figure out how many transactions they have.


### Commons Mistakes and Issues

This is the first phase where things might start to come unglued.
Decentralized networks are a bit messy. Take this opportunity to
walk around and make sure nodes aren't making some common mistakes
or problems that happen, which are listed here.

#### What to look out for

- A connection drops.
	That's fine, pick it back up. It's sometimes
    fun to comment that "oh it looks like you dropped the connection".
- Nodes forget which incoming connection sent them a message.
	Encourage nodes to come up with a way to remember which connection
	sent what message. Computers have this same problem. A common way
	that they solve it is to give each connection a number and then
	label the incoming messages with that number.
- Nodes don't make a transaction, but rather send their original
	Have them send a Send Transaction message to the peer to get
	them to send a copy of the transaction back. Once they receive
	it they should validate it again before placing it into their
	mempool.
- A node receives a transaction already stamped with Approved.
	They should re-verify the transaction is correct.
- A node receives an invalid transaction (too much money in outputs, missing
  lock or keys)
	Technically they should rip up the transaction AND drop the connection
	to the node that sent them the bad data. It's up to the node how
	lenient they want to be about punishing mistakes. Notably in the
	bitcoin protocol, we don't send back error messages. We just stop
	speaking to that peer.
- Transactions aren't making it all the way across the network.
    Nodes often forget they need to send another round of I Have
	Transaction messages after *every* new transaction that's added
	to the mempool. It might be useful to remind nodes to do this.


## Checking Global Mempool State

Let's get a picture of what the network looks like. It's really
hard to actually do this on the bitcoin network, but we can do it
easily with a group of people.

### Who Has the Most Txs?

Note: See section in [Setup](docs/01-setup#rewards-for-nodes) about what to use as a Reward.

Instructor Script:

	Ok, let's see who's got the most transactions in their mempool.

	ACTION: Point at each node one by one. Have them count and
	tell you the number of transactions in their mempool.

	ACTION: Reward the node with the most transactions in their
	mempool with a Reward. Ideally every node has the same
	number of transactions, so they should all be rewarded.


### Who's Transaction Is In The Most Mempools?

Instructor Script:

	ACTION: Have each node, in turn say what the txid of the
	transaction they wrote is. Have the other nodes
	raise their hands if they have that transaction in their
	mempool.

	ACTION: Keep track of how many nodes raise their hands for
	each transaction. After every node has said their transaction
	id, reward the node (or nodes) that have their transaction
	in the most mempools with a Reward. Ideally, every transaction
	will be in every other node's mempool, so every node should tie.
	This rarely happens.


## In Sum

We've now got some full mempools and have experienced what sending
and receiving network messages is like. We're ready to move on to
building block templates.

In this portion of the LARP we've:

- Gotten connected to a peer to peer network
- Sent and received our first network messages
- Practiced verifying network transactions
- Filled up our mempools with transactions to be mined
