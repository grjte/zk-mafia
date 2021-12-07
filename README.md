# ZK Mafia: Hackers vs. Devs
A Zero Knowledge game of Mafia pitting anonymous hackers against a heroic band of developers battling for the future of Web3

## About
### What?
We're bringing the classic social deduction party game of [Mafia](https://en.wikipedia.org/wiki/Mafia_(party_game)) to life in zero knowledge. See story and gameplay details below.

### Why? 
ZK Mafia provides a case study of the power of zero knowledge technology, while making it fun and accessible to a wider and less technical audience.

Can you do it without ZK? Yes. 
Can you do it better with ZK? Yes.
Do those 2 lines foreshadow our collective future? I believe so.

### How?
This is a completely new project, so some things are still being hashed out, but ZK Mafia will be on Layer 2, on either StarkNet or Aztec.

Aztec's L2 offers privacy by default, which simplifies the implementation, but they're still on testnet. StarkNet, on the other hand, just launched their shiny new Alpha version! However, because StarkNet doesn't support privacy out of the box, we'd have to use their ZK-STARK prover&verifier [Ziggy](https://github.com/starkware-libs/ethSTARK/tree/ziggy).

We'll play with both and see which one we like more for this project.

The game design is described below, and the more granular implementation details will be decided as we build!

## ZK Mafia - Game Story
An anonymous cabal of hackers have been exploiting Web3 projects and draining them of funds. To save the Web3 ecosystem, a heroic group of top developers has joined forces to fight back. They've formed HackNone, an organization dedicated to hunting down Web3 hackers.

But HackNone has just received a tip! There are hackers masquerading amongst their members.

The honest devs must catch the hackers amongst them and vote to expel them. Unfortunately, because only the best devs are allowed as members, if a dev's project is exploited, that dev will be kicked out first.

Will the devs catch the hackers in time before their own projects are exploited? Or will the hackers take over HackNone and rule the new Web3 world?

## Gameplay

The game plays out much like the original game of Mafia, with Devs instead of Villagers, Hackers instead of the Mafia, and an Auditor instead of a Detective.

### Roles
**Devs:** 
As the uninformed majority, Devs know only their own role and the number of Hackers.

**Auditor**
The auditor is a Dev with a special detective role which allows them to help catch the Hackers. The Auditor knows only their own role and the number of Hackers. No one else knows who the Auditor is.

**Hackers:**
Hackers are the informed minority. They know the identity of all other Hackers. The hackers have a leader known as the L33T H4X0R who always performs the phase action for the Hackers. If caught, the leadership passes randomly to another Hacker.

### Phases

**Night**

*Hackers:*
At night, the Hackers coordinate and unanimously choose a developer whose project they'll attack. The selection is submitted by the L33T H4X0R, and that developer is removed from gameplay thereafter. All other hackers submit an empty action.

*Auditor:*
Each night, the Auditor can choose one person to investigate. The Auditor learns whether the individual is a Hacker or an honest Dev.

*Devs:*
All honest devs submit an empty action.

Once everyone has submitted an action (some of them empty), the Night Phase ends and the Day Phase begins.


**Day**
During the day, a public vote is taken to select a member to be removed from the organization, as the Devs attempt to catch a Hacker.

A simple majority is all that's required to expel someone. Once voted on, that individual is removed from gameplay

### Win Conditions
* The Devs win when all of the Hackers have been eliminated.
* Hackers win when they reach numerical parity with the honest Devs.
