## Import - Auto-Completion by Contract  Name

Add auto-completion for import statement. Whenever you write the name of the contract, language server shall go and check what are the contracts that are currently deployed to accounts and propose where you want to import it from (similar to what we have with npm modules in **Javascript**)

**Implementation Challenges**

Possibly will require some integration between `flow emulator`, `language server` and additional tooling.  https://github.com/onflow/flow-js-testing is implementing a way to track all the deployed contracts and created accounts, which probably could be brought into emulator.