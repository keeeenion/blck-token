# BLACK PLATFROM TOKEN

## Deployed values

1. Token name: "Black Platform Token"
1. Token symbol: "BLCK"
1. Token decimals: "18" (standard)
1. Token amount: "575000000000000000000000000" (575 million in Wei)

Token deployment hash: https://etherscan.io/tx/0x12cb3f72f33b2d906a321ded4d54ac91f6eb68fbf60aa66a2e0faa41304b40ea

## Token information
"BLCK" token is an ERC20 token that is deployed to the Ethereum Main Network.

The token is both burnable and mintable by the owner wallet (Ask Peep for the private key, it's in 1pass). Minting can be disabled, but that can not be undone.

Interacting with the token is eased by "Remix" - and online tool for interacting with Ethereum networks. It can be accessed [here][remix]. [Metamask][metamask] (or any web3 injected) can be used to broadcast the transactions.

## Remix instructions
First copy the source code (blck.sol) into the editor on the left. Should compile okey (few warning may pop up).

Open the "run" tab on the right top corner.

Environment:
  1. JS VM: Creates a new local blockchain, blocks are mined almost instantly. Only for testing locally.
  2. Injected VM: Actions are ran in the network active in metamask (or any web3 instance active in the browser)
  3. WEB3 Provider: Can be used on browsers that do not have web3 capabilities. URL has to be provided, for example [infura][infura]

Account: The account/address that signs the actions.

Gas limit: Max gas that the transaction gas use. Metamask may overwrite it sometimes.

Value: Amount of selected currency (eth, gwei...) that will be sent to contract functions. Another [online tool] is great for converting the them.

All compiled tokens are shown in the select input. Select "Token".

Red(ish) buttons are for writing functions, that require signing and mining.
Blue(ish) functions are for read functions, that run much quicker and near instant

To interact with deployed contract paste the address into "Load the contract from Address" and press "Ad Addess".

To deploy a new one, if needed fill in all the inputs and press "transact". One can either expand the "Deploy" window or write all the fields inline.

Inline example: "Black Platform Token", "BLCK", "18", "575000000000000000000000000"

**Note! all values have to be surrounded by quotemarks (")**.

## Token functions

Deployed and imported contracts are listed under "Deployed Contracts"

**All currency amounts are handeled in "Wei". 1 ETH = 1,000,000,000 WEI. Same goes to tokens. 1 TOKEN = 1,000,000,000**

**Won't be the same case if the decimals value changes**

> Write functons:

approve (\<spender address>, \<how many tokens in wei>): Allow another address to transfer money from your account.

burn(\<tokens to burn in wei>): Burns tokens from the address calling the function. Limited the the owner address.

decreaseApproval (\<spender address>, \<how many tokens in wei>): Decrease the amount of tokens another user can spend from your address

destroy: Destroys the contract, all following transactions and function calls are invalidated. ETH on contract is moved to caller address

destroyAndSend(\<address to get all the ETH>): Same as destroy, but allows chaning the address that get the ETH

finishMinting(): Disables functionality to mint any more tokens. Limited to the owner account

increaseApproval(\<address to be allowed to spend toksn>, \<tokens in wei>): Increases the amount an address can spend from another address

mint(\<address getting the tokens>, \<tokens in wei>): Contract owner can generate new tokens

transfer(\<to address>, \<tokens in wei>): Send tokens to another address

transferFrom(\<from address>, \<to address>, \<tokens in wei>): Sends tokens from another address that has allowed the caller to send

transferOwnership(\<new owner address>): Transfers owner permissions to another address

> Read functions:

allowance(\<address holding tokens>, \<address wanting to send tokens>): See how many tokens another address is allowed to send

balanceOf(\<address to check>): View balance of an address

decimals(): View how many decimals this token has

mintingFinished(): Boolean whether more tokens can be generated

name(): Get the name of the token

owner(): Get the owner address of the token

symbol(): Get the symbol of the token

totalSupply(): Get current supply in circulation

[remix]: https://remix.ethereum.org/
[metamask]: http://metamask.io/
[infura]: https://infura.io/
[online tool]: https://etherconverter.online/
