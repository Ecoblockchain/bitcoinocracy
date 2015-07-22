README
======

[Bitcoinocracy](http://bitcoinocracy.com) is a project that aims to determine the truth backed by real monetary value and to facilitate decentralized decision making in the Bitcoin eco-system.

It is absolutely transparent, free and doesn't require user registration.

Just sign the statements with non-empty bitcoin addresses to express your opinion.

Data structure
--------------

```
Argument
	statement
	validity
	
Signature
	argument_id
	bitcoin_address_id
	is_negation?
	signature

BitcoinAddress
	bitcoin_address
	balance
```

Algorithm
---------

For each argument calculate validity: `validity = sum(pro bitcoin balances) - sum(con bitcoin balances)`

Todo
----

* Background job to update bitcoin balances (e. g. `BitcoinAddress.all.each{|a|a.update_balance};Argument.all.each{|a|a.update_validity}`)
* Decide how to handle multiple signatures from the same bitcoin address for/against the same argument
* Pagination, search, compare arguments, social buttons, etc...
* Optional user accounts? Compound arguments? Logical inference?
