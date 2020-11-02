# Cadence Ideas

This document outlines different ideas, that might improve `Developer Experience` (DX)

## CLIP - "Cadence Language Improvement Protocol"

Create a process for creating, discussing and implementing Cadence Language Improvement Protocol (`CLIP`).

**Necessity**

There are multiple ideas how we can improve Cadence and tooling around it. Some of the them can be formed as issues and resolved right away. Another require discussion and evaluation, before being implemented.



## Import - Auto-Completion by Contract  Name

Add auto-completion for import statement. Whenever you write the name of the contract, language server shall go and check what are the contracts that are currently deployed to accounts and propose where you want to import it from (similar to what we have with npm modules in **Javascript**)

**Implementation Challenges**

Possibly will require some integration between `flow emulator`, `language server` and additional tooling.  https://github.com/onflow/flow-js-testing is implementing a way to track all the deployed contracts and created accounts, which probably could be brought into emulator. 



## Import - Pragma Lines for Network

> This might sounds like a really far fetched idea and have potential pitfalls and incompatibility with current implementation.

Allow loading contracts from outside of the emulator network,  redeploying them to emulator

**Implementation Challenges**

- contract might have more imports, that need to be pulled  from outside and resolved. The whole process might introduce naming collisions 🤔
- contracts might be initialized with specific set of arguments, which won't be possible to resolve in emulator environment. *Though we can allow this for contracts, with no arguments in **init** call, since language server can get us this information.*

**DX Improvements and Use Cases**

- speed up development of new contracts, which want to utilize currently deployed contracts from other parties
- uniform experience using `standart` contracts - i.e. `FungibleToken`, `NonFungibleToken`, etc. so you don't need to redeploy them locally and at the same time have actual code, which would work in the "field" as expected