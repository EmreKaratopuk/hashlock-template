# Archetype Hashlock Template

This repository contains an archetype hashlock smart contract template which is transpiled from [LIGO IDE](https://ide.ligolang.org/) jsligo hashlock template.
The archetype smart contract contains two entry points, `commit_hash` and `reveal_hash`.

## commit_hash entry point

The `commit_hash` entry point is used to submit hashed messages to avoid issues such as [transaction ordering](https://ligolang.org/docs/tutorials/security/?lang=jsligo#transaction-ordering). The provided hash
must be created by using the concatenation of the sender's public address (wallet address) and the user's solution with sha256 algorithm. 

## reveal_hash entry point

The `reveal_hash` entry point is used to check if the solution, which is required to be submitted to the smart contract by using `commit_hash` entry point, is correct. A plaintext solution and 
optionally a lambda function is provided to the entry point. Users must wait at least 24 hours to be able to call `reveal_hash` entry point. 
This is an important safety measure to ensure the plaintext submitted by a user is not copied and used by another user.
