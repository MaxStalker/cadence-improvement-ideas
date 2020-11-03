## Import - Pragma Lines for Network

> This might sounds like a really far fetched idea and have potential pitfalls and incompatibility with current implementation.

Allow loading contracts from outside of the emulator network,  redeploying them to emulator

**Implementation Challenges**

- contract might have more imports, that need to be pulled  from outside and resolved. The whole process might introduce naming collisions 🤔
- contracts might be initialized with specific set of arguments, which won't be possible to resolve in emulator environment. *Though we can allow this for contracts, with no arguments in **init** call, since language server can get us this information.*

**DX Improvements and Use Cases**

- speed up development of new contracts, which want to utilize currently deployed contracts from other parties
- uniform experience using `standart` contracts - i.e. `FungibleToken`, `NonFungibleToken`, etc. so you don't need to redeploy them locally and at the same time have actual code, which would work in the "field" as expected