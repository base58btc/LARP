# Extensions - things to try

Here's a few ideas of things to try differently when
you run the next LARP. I'd recommend not trying variations
with a crowd that's new to the bitcoin protocol, but these
are great things to add once the participants in the game
feel comfortable with the gameplay.

## Table of Contents

  * [Bitcoin Shops](#bitcoin-shops)
  * [BASIC Boost](#basic-boost)
  * [Difficulty Retargeting](#difficulty-retargeting)
  * [Replaceable Mempool Transactions](#replaceable-mempool-transactions)

## Bitcoin Shops

Have participants bring items to sell for bitcoin to their peers.

Make every node have to create one transaction buying and one
transaction selling something every time that they win a block.


## BASIC Boost

Buy or build more BASICs. As the facilitator, offer them for sale
to nodes for bitcoin.

Let them know how many confirmations their transaction needs before
you'll consider the sale to be final.


## Difficulty Retargeting

In the regular bitcoin blockchain, the difficulty changes every
2016 blocks. In the LARP, we can update the difficulty every 5 blocks.

After the 5th block has been mined, have nodes recalculate the target
that goes onto each blockheader.

Use the included Difficulty Calculation cards to help figure this out.

The 6th block in the network must have the correct target value. If the
target is wrong, the block is considered invalid.


## Replaceable Mempool Transactions

This modification has to do with what transactions are allowed
into the mempool.

If a node decides that they want to spend an output that already
has a transaction spending it in the mempool, it's generally considered
invalid.

With this rule, any new transaction that wants to spend an output
that another transaction is already spending is now *allowed* to,
but they must pay twice the fee of the transaction they're kicking
out of the mempool.

