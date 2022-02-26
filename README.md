# NFTBrawl
Yet another way for degens to play with NFTs...

## Summary ##

Put random NFTs in the fighting ring.
Choose your fighting style (assasin, bounty hunter, Tank, Support)
Optionally add "treasure" (any erc20) to make yourself more desirable and thus more likely to survive.

There will be a governance token BRWL (or some name to be decided) that will control the treasury (probably have distributions as well).
On each round, there is a chance that a brawler (and/or it's treasure) to be trapped which means this is sent to the treasury.
Note: anyone can create righting rounds using the contract and burning governance tokens but the treasury will do it periodically as well.

For clarity: 

* "Captured" means transferred to another player after the brawl
* "Trapped" means retained by the treasury (or a seperate contract)
* "killed/died" means burned or transferred to null address 0x000..

## Tokenomics ##

Many of the newer projects are focused on creating their own ecosystems (ie chikn, Ufightclub etc) where they have their own NFT's their own token etc etc. It's cool but the fundimental value is encapsulated within the system which limits it and usually gives it a short "pump and dump ponsiesque" lifecycle.

The most long-term successful products are ones that work with a broad number of assets and require ongoing external value input. Eg Aave, Uniswap, Opensea etc. This project would enable that function while bringing a fun game-like interaction that involves real-life value risk, reward and strategy.

The game doesn't need to have it's own tokens or NFTs and existing assets and infrastructure is leveraged which is the true magic of blockchain!!! 

The only token that would be created is a governance token. This would have a fixed cap and emission schedule and would allow votes for what to do with the treasury. 

The treasury gains ERC tokens and NFTs through "trapping" brawlers and their treasure in each round. The governance holders will get ongoing votes as to re-enter these winnings into future games or to sell them on the open market. Any proceeds from sale goes back to the treasury. If significant value is accumulated in the treasury then governance holders can vote to pay some of this out (in eth or whatever). It's a stripped-down DAO structure that is completely decentralized and completely automated with smart contracts. Again, the mechanics of this will need to be fleshed out up front but actual development may not be implemented until after the initial release.

The governance token will be burned (or re-introduced to treasury by vote) when any player enters the game or if a user decides to create their own private round (costs significantly more). Governance tokens will be hard to obtain, designed to start at a high price point and be deflationary through people playing the game, making their own game or submitting proposals to vote on. At any point the collective governance holders can submit a proposal and vote to withdraw all treasury funds to their own wallets so the governance is effectively backed by that value + some notional value that relates to the control that these holders have over generic gameplay. There are higher level strategy opportunities for those that control votes etc (ie like curve-wars).

### Possible proposals, voted by the DAO: ###

* Change base stats of a Brawler type
* Allow/ban new treasure token
* Allow/ban new NFT Brawler
* Sell Brawler/Treasure on a marketplace
* Burn Brawler/Treasure
* Add treasury Brawler/treasure to the Brawl queue (enters them into the feild in an approaching round)
* Request dividend (equal payout of ERC20 to of some amount to all governance holders)
* Change round time (will need to be a hard min for security)
* Enable bribery (Allow people to improve stats by paying the treasury)
* Change BRWL price to create or play the game
* Change whether governance tokens are burned or re-introduced or whether you can win them during gameplay
* Enable staking rewards for governance token
* Add generic functionality (upgrade implementation contract)

Eventually, anyone can spin up proposals using the web UI and it will be easy to vote on. This might be connected to the discord or votes just made through the discord to begin with before the DAO contracts are finalised.

_Note that many of these may require upgrades to the underlying solidity contracts. This will require the main interactive contract to be built using a transparent proxy pattern or similar. These would require generic proposals of the form: `Propose_new_functionality("description", functionABI..etc, new_contract_address)`. Proposals will have timeframes with some hardcap minimum (for security) and require quadratic voting majority to pass. There will also need to be some functionality to self-destruct the contract and return the treasury if a bad-actor accumulates over 50% of the governance tokens._

## Chain ##

The idea would be to build this on a single cheap-gas blockchain such as avalanche, polygon, or possibly even Ronin if it could support generic erc20 and nfts - I think the latter would create a lot of natural marketing as there are a huge number of gamers who use only the Ronin chain and there is already fiat ramps here I think. There are a lot of transactions so gas will need to be cheap and there are some time based functions so transactions would need to be passed ideally in under 1 minute. There are several chains that this works with currently. 

Bridging onto something Ethereum may cause issues because of time delays. Also all transaction information to interact will either need to be packaged into a bridgeable format or be able to somehow be interacted with off-chain. 

It maybe that off-chain NFTs are required to load treasure in the main-chain's base currency. Ie if we build on avax and you want to interact from eth then you _need_ to submit avax treasure and part of this will pay subsequent gas fees on avax (for example).

Longer term, other chains can be supported by way of a generic automated bridge on the endpoints. NFTs would need to be verified on their own chain of course and the bridge(s) would need to be able to handle all types that the game does. Needs to be designed with this in mind but there is complexity that can be added later.

## Gameplay ##

1. Select an NFT you own
1. Choose role type
  - Assassin
  - Bounty Hunter
  - Tank
  - Support
1. If !Tank, choose target
1. Submit to battle
1. Battle starts at some random time -- show brawl animations if possible
1. Collect winnings once battle is finished

## Base Stats ##

Note: Chance of survival, captured, ded or trapped are percentages that add to 100. Capture skill is from 0 to 10 and is seperate.

There may be an option to stat-boost a particular type of NFT for any given round - will need to look into this as far as implementation goes.

### Assassin ###

- Chance of survival = TBD
- Chance of being captured = TBD
- Chance of dying = TBD
- Chance of being trapped = TBD
- Capture skill = TBD

### Bounty Hunter ###

- Chance of survival = TBD
- Chance of being captured = TBD
- Chance of dying = TBD
- Chance of being trapped = TBD
- Capture skill = TBD

### Tank ###

- Chance of survival = TBD
- Chance of being captured = TBD
- Chance of dying = TBD
- Chance of being trapped = TBD
- Capture skill = TBD

### Support ###

- Chance of survival = TBD
- Chance of being captured = TBD
- Chance of dying = TBD
- Chance of being trapped = TBD
- Capture skill = TBD

## Stat Modifications (if you are targeted) ##

_All stat modifications are normalised by the number of people in the brawl. IE if there are 10 people in the brawl and the stat modifier below shows +25% then the actual modification for each person who targets you is actually 25/10 = 2.5%

Targeted by Assassin

* Survival = TBD
* Capture = TBD
* Death = TBD
* Trapped = TBD
* Capture skill = TBD

Targeted by Bounty Hunter

* Survival = TBD
* Capture = TBD
* Death = TBD
* Trapped = TBD
* Capture skill = TBD

Targeted by Support

* Survival = TBD
* Capture = TBD
* Death = TBD
* Trapped = TBD
* Capture skill = TBD

_Tanks cannot target anyone._

## Game Logic ##

A round is started by someone random or by the treasury - this costs some BRWL (or whatever). The constructor asks the total number of players. The treasury will do them at any number between 2 and 50 (could be random or perhaps an adaptive number or set manually at first - or some voting metric or governance tokens). This will be NUM_PLAYERS.
open_brawl(NUM_PLAYERS, [min treasure])

People can add NFTS to the round by calling
`submit_brawler(nft contract, brawler type enum) returns brawler index.`
you can find your brawler indexes by calling:
`get_figher_indexes(your address) returns array of uint16 `
`uint16` is just in case we want to change max game size limit.

note you can see all other brawler in the game (or ready to go to the game) and their treasure but you cannot see what type they are (not sure how possible that is on an open blockchain) this might have to be visible as well.

One wallet can only add up to half of the brawlers (multi wallets can obviously get around this but is a decent decentivizer) `require length(get_brawlerindexes(_message_sender_address) < (NUM_PLAYERS/2)`

Note that not all NFT types will be allowed by default. A contract must be proposed (easy to do on the website) and then voted in with governance tokens to be able to engage in a brawl. Lots will be initially available (like anything currently verified and valuable on opensea/nftrade etc. This will stop people mass-minting heaps of worthless nfts just to participate.

You may wish to equip treasure to your brawler:
`payable add_treasure(brawler index, erc20 treasure type, erc20_treasure amount)` requires you own the brawler, ie 
`require brawler_index IN get_brawler_address(_message_sender)`

Treasure min value per round is either determined by whoever started the game or can be voted on by governance. Perhaps absolute min (and default value) is voted on and optionally this can be raised by someone starting their own game). Similarly to the NFTs treasure cant be any random ERC, it will need to be verified but new ones can be proposed and voted in.

Equipping treasure serves two purposes:

1. Ensures your NFT is more valuable and thus is targeted by more capturers (and hopefully less assassins). 
1. Gives you an extra chance of survival. If you have treasure and you are marked as killed, captured or trapped then that will only apply to the treasure and your same statistics will be run again to determine outcome for your NFT. 

for example if your base statistics are:
S,D,C,T = 40%, 30%, 20%, 10% and you *don't* have treasure, then you have a 40% chance of survival. If you have the same stats and you do have treasure 
then your chance of survival becomes:

40% + 40%*30% + 40%*20% + 40%*10% = 64% 

However you still have a 60% chance of losing your treasure somehow (captured, destroyed or trapped).

Once the final person has submitted their NFT, a timer counts down which gives everyone a chance to pull out at the last minute or equip/unequip treasure. If the timer runs out and no-one has pulled out, the brawl begins.

Ideally there would be some kind of animation that depicts the NFTs going around the screen and bumping into each other etc but I'll leave that out for now. The actual win logic is as follows:

Get verifiable random number (chainlink feed or similar) return `seed`.

Determine who survives/dies/captured/trapped:

```
for each id in brawlerids[]:
  rand = get_random_between1_100(seed+brawlerID)
  rand_second_chance = get_random_between1_100(seed+brawlerID+"T")

  if (survive_range_min < rand < surive_range_max):
    survived_treasure_array.push(brawler.index)
    survived_array.push(brawler.index)
  if (captured_range_min < rand < captured_range_max):
    captured_treasure_array.push(brawler.index)
       if (captured_range_min < rand_second_chance < captured_range_max):
         captured_array.push(brawler.index)
  ...
```
So we now have arrays full of IDs that have survived, been captured, died or trapped.

Some are easy:
The died treasure and brawlers are burned (transferred to 0x000)
The captured treasure and brawlers are sent to treasury contract address

The remaining "captured" treasure and brawlers are distributed to the survivors in the following way.

```
randomise_order(captured_array, seed)

for each id in captured_array: 
  if(captured_array_is_full()):
    add_to_trapped_array(id)
    continue

 while(1): // I know bad practice, there'll be a nicer way IRL
     captured_index = get_rand_of_length(length(captors_array), 
      seed+id+"C"+tries)
    if !captured_mapping[captured_index] then 
        captured_mapping[captured_index] = id
        break
    else
      tries++

```

Repeat same logic for treasure, it does not go with the person who captured the brawler, it is separated as soon as the game begins.

captors_array is a memory array of all the captor ids based on how many capture_skill they have. Eg in a game of 5 brawlers where brawler 0 has 5 capture skill, brawler 1 has 6 capture skill, brawler 2 has been captured (or died ), brawler 3 has 4 capture skill, and brawler 5 has also been captured the array would look like the following:
`[0, 0, 0, 0, 0, 1, 1, 1, 1, 1, 1, 3, 3, 3, 3]`. There are probably more elegant ways to achieve this in python but this is the premise. Note that in the function, one NFT can not occupy more than one slot on the mapping so this reduces the chance of one survivor capturing all the captured ones. If there are more captured ones that capture spots the remaining ones are sent to treasury ;).

After the logic above we should have two more arrays the same length as the above such that the following:

In our game example above, lets say brawler 2 and 5 have been captured and only brawler 5 has treasure. After the allocations, the arrays might look like the following:

(n's are null values)

```
captors_array =              [0, 0, 0, 0, 0, 1, 1, 1, 1, 1, 1, 3, 3, 3, 3]
captured_mapping =           [n, 3, n, n, 5, n, n, n, n, n, n, n, n, n, n]
captured__treasure_mapping = [n, n, n, n, n, n, n, n, n, n, n, n, n, 5, n]

```
With this outcome, brawler with ID 1 has captured both brawler 3 and 5 but has not captured any treasure and brawler 3 has captured brawler 5's treasure.

After that, the brawlers and their winnings are grouped by address, sent back to their owners and the brawl is over.

The treasury will wait for a cooldown period and then start the next brawl!

Trapped brawlers may be added to the subsequent brawls or sold on the marketplace depending on governance votes! Captured treasure will be similarly proposed and voted on.

## Roadmap ##

1. Playable game on single network, no frills no UI
1. UI on website
1. Frills and extra options unlocked in the contracts and on the website
1. DAO proposal and voting functionality - probably separate website
1. DAO stuff integrated into core website
1. Multi-chain deployment (people on different chains can play among themselves)
1. Cross-chain bridging so that people on different chains can play together

