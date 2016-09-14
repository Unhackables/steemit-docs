---
title: Steemit API Reference

language_tabs:
  - Steemd
  - Javascript

toc_footers:

includes:

search: true
---

# Introduction

Welcome to the [steemit](https://steemit.com) API and developer wiki portal! Steemit is the social media platform where everyone gets paid for creating and curating content.

The following API documents provide details on how to interact with the Steem blockchain database API which can get information on accounts, content, blocks and much more!

The developer portal will also serve as a toolbox for steem clients, libraries, and language wrappers.

The developer portal is currently in early release. Our developer portal docs are open source and
steem developers are encouraged to contribute as this becomes the ultimate developer resource for steemit.

Please visit [https://github.com/steemit/steemit-docs](https://github.com/steemit/steemit-docs)

# Accounts

### Account Endpoints


```javascript
Example responses

get_account_count
{
"id": 2,
"result": 91171
}

get_account_history
{
"id": 3,
"result": [
  [10, {
    "id": "2.17.929",
    "trx_id": "cd7913782657e609167f62194eea36375defbdeb",
    "block": 18717,
    "trx_in_block": 0,
    "op_in_trx": 0,
    "virtual_op": 929,
    "timestamp": "2016-03-25T08:02:33",
    "op": ["pow", {
      "worker_account": "steemit",
      "block_id": "0000491c7e73f1dddcf8f8f93f128f96930370b8",
      "nonce": "3572148442797474411",
      "work": {
        "worker": "STM65wH1LZ7BfSHcK69SShnqCAH5xdoSZpGkUjmzHJ5GCuxEK9V5G",
        "input": "81df53d541cc33591e73d626beb298951eaa58d39b5838b07bafe538ba5aa505",
        "signature": "200467a1e98e79de953dfeb767d9f193eccf3aeb197754c57c9620d8571c0cafe018caaa3186740ab987d16247318bb51239df7dfa0ad60085c023a8edabc00acf",
        "work": "0000000bb8deb767063d26a186d77c60280ce203c3fb84f59aa3627d7e95cb4a"
      },
      "props": {
        "account_creation_fee": "100.000 STEEM",
        "maximum_block_size": 131072,
        "sbd_interest_rate": 1000
      }
    }]
  }]]
}

```

`get_account_count`

`get_account_history`

*params: account(string), from(uint32_t), limit(uint32_t)*

`get_account_references`

*params: account(string)*

`get_account_votes`

*params: account(string)*

`get_accounts`

*params: accounts(strings) in nested array*


# Blocks

### Block Endpoints

```javascript
Example responses

get_block
{
"id": 2,
"result": {
  "previous": "003d08ff118b27e093103b580daca817342f9596",
  "timestamp": "2016-08-11T22:00:06",
  "witness": "silversteem",
  "transaction_merkle_root": "a4ed1b655c56040fd77857c2983f390fa30852cd",
  "extensions": [],
  "witness_signature": "206e7847032dd57c821fb45f880123c57a88fef17e11e4da218b7ece631d4c8338124ad02bca19710fa2376672dc2c531469f3499a208c4bf01bb990cde4ec03f0",
  "transactions": [{
    "ref_block_num": 2303,
    "ref_block_prefix": 3760687889,
    "expiration": "2016-08-11T22:00:33",
    "operations": [
      ["witness_update", {
        "owner": "supercomputing05",
        "url": "http://fxxk.com",
        "block_signing_key": "STM5b3wkzd5cPuW8tYbHpsM6qo26R5eympAQsBaoEfeMDxxUCLvsY",
        "props": {
          "account_creation_fee": "1.000 STEEM",
          "maximum_block_size": 65536,
          "sbd_interest_rate": 1000
        },
        "fee": "0.000 STEEM"
      }]
    ],
    "extensions": [],
    "signatures": []
  }

get_block_header
{
  "id": 4,
  "result": {
    "previous": "0001d4bf70af1312e019091fcd82261870744146",
    "timestamp": "2016-03-28T20:53:33",
    "witness": "steemit45",
    "transaction_merkle_root": "0000000000000000000000000000000000000000",
    "extensions": []
  }
}
```

`get_block`

*params: block number(uint32_t)*

`get_block_header`

*params: block number(uint32_t)*

# Content

### Content Endpoints

```javascript
Example responses

get_content
{
  "id": 6,
  "result": {
    "id": "0.0.0",
    "author": "",
    "permlink": "",
    "category": "",
    "parent_author": "",
    "parent_permlink": "",
    "title": "",
    "body": "",
    "json_metadata": "",
    "last_update": "1970-01-01T00:00:00",
    "created": "1970-01-01T00:00:00",
    "active": "1970-01-01T00:00:00",
    "last_payout": "1970-01-01T00:00:00",
    "depth": 0,
    "children": 0,
    "children_rshares2": "0",
    "net_rshares": 0,
    "abs_rshares": 0,
    "vote_rshares": 0,
    "children_abs_rshares": 0,
    "cashout_time": "1970-01-01T00:00:00",
    "max_cashout_time": "1970-01-01T00:00:00",
    "total_vote_weight": 0,
    "reward_weight": 23228,
    "total_payout_value": "0.000 SBD",
    "curator_payout_value": "0.000 SBD",
    "author_rewards": 0,
    "net_votes": 0,
    "root_comment": "2.8.0",
    "mode": "first_payout",
    "max_accepted_payout": "1000000.000 SBD",
    "percent_steem_dollars": 10000,
    "allow_replies": true,
    "allow_votes": true,
    "allow_curation_rewards": true,
    "url": "",
    "root_title": "",
    "pending_payout_value": "0.000 STEEM",
    "total_pending_payout_value": "0.000 STEEM",
    "active_votes": [],
    "replies": [],
    "author_reputation": 0
  }
}
```

`get_content`

*params: account(string)*

`get_content_replies`

*params: account(string)*

# Discussions

### Discussion Endpoints

`get_discussions_by_active`

*params: tag(string), limit(integer)*

`get_discussions_by_author_before_date`

*params: tag(string), start_permalink(string), before_date(integer), limit(integer)*

`get_discussions_by_cashout`

*params: tag(string), limit(integer)*

`get_discussions_by_children`

*params: tag(string), limit(integer)*

`get_discussions_by_created`

*params: tag(string), limit(integer)*

`get_discussions_by_feed`

*params: tag(string), limit(integer)*

`get_discussions_by_hot`

*params: tag(string), limit(integer)*

`get_discussions_by_payout`

*params: tag(string), limit(integer)*

`get_discussions_by_trending`

*params: tag(string), limit(integer)*

`get_discussions_by_votes`

*params: tag(string), limit(integer)*

# Categories

### Category Details

`get_trending_categories`

*params: tag(string), limit(integer)*

`get_best_categories`

*params: tag(string), limit(integer)*

`get_active_categories`


*params: tag(string), limit(integer)*


# Feed

### Feed Endpoints

```javascript
Example responses

get_feed_history
{
  "id": 5,
  "result": {
    "id": "2.14.0",
    "current_median_history": {
      "base": "0.713 SBD",
      "quote": "1.000 STEEM"
    },
    "price_history": [{
      "base": "0.797 SBD",
      "quote": "1.000 STEEM"
    }, {
      "base": "0.801 SBD",
      "quote": "1.000 STEEM"
    }, {
      "base": "0.800 SBD",
      "quote": "1.000 STEEM"
    }
  }
 }
```

`get_feed_history`

# Witness

### Witness Endpoints

```javascript
Example responses

get_active_witnesses
{
  "id": 14,
  "result": ["xeldal", "bitcube", "joseph", "roadscape", "clayop"]
}
```

`get_active_witnesses`

`get_witness_by_account`

*params: account(string)*

`get_witness_count`

`get_witness_schedule`

`get_witnesses_by_vote`

# Escrow

### Witness Endpoints

`escrow_transfer_operation`

`escrow_approve_operation`

`escrow_dispute_operation`

`escrow_release_operation`

# Savings

### Witness Endpoints


`transfer_to_savings_operation`

`transfer_from_savings_operation`

`cancel_transfer_from_savings_operation`


