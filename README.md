# ʻOumuamua

**A blockchain-based persistent virtual world in a MMRPG (massively multiplayer role-playing game)**

This is an open source project for story writers, graphic artists, musicians, voice over talent, and software programmers to contribute to an amazing new online game named **ʻOumuamua**.

The URL of the Oumuamua project on GitHub is
[https://github.com/peterthorsteinson/Oumuamua](https://github.com/peterthorsteinson/Oumuamua)

The URL of the Oumuamua Viewport project on GitHub is
[https://github.com/peterthorsteinson/OumuamuaViewport](https://github.com/peterthorsteinson/OumuamuaViewport)

### Tumbling Oumuamua Asteroid in Unity3D WebGL
[Live Demo](https://peterthorsteinson.github.io/index.html)

### URL of the ASP NET Core Blazor WASM SignalR Demo project on GitHub is
[https://github.com/peterthorsteinson/AspNetCoreBlazorWasmSignalRDemo](https://github.com/peterthorsteinson/AspNetCoreBlazorWasmSignalRDemo)

### Artist Impressions (attribution: wikipedia)
![Oumuamua Trajectory](https://github.com/peterthorsteinson/Oumuamua/blob/master/img/OumuamuaTrajectory.png?raw=true)
![Viewed From Earth](https://github.com/peterthorsteinson/Oumuamua/blob/master/img/ViewedFromEarth.png?raw=true) ![Artist Impression](https://github.com/peterthorsteinson/Oumuamua/blob/master/img/ArtistImpression.jpg?raw=true)

## Software Stack

![Oumuamua Architecture](https://github.com/peterthorsteinson/Oumuamua/blob/master/img/OumuamuaArchitecture.PNG?raw=true)

### Main Technologies

* Cosmos DB stores player command histories and a Graph database for player game state in each theater of engagement
* Ethereum stores immutable hash values of game play histories and crypto token assets
* Blazor implements the player UI on client devices using WebAssembly, as well as the local Causality Engine
* Notification Hubs alert users in real time regarding impending threats and opportunities, etc.
* Nethereum is a library that enables API access to the Ethereum blockchain from within the user device
* WebRTC enables fast and direct communications between users for socializing and collaborating
* REST APIs and Serverless Functions provide access to global cognitive services and AI capabilities
* Cognitive services provide human language translation for players around the world to communicate
* Cognitive services provide machine learning support for non-human actors such as oracles and bots
* ION provides a recently developed decentralized authentication service for all users
* Odin is a set of smart contracts that ensure game stability and fairness
* The Althing is a virtual parliament smart contract used to execute referendums such as Big Bang Banishment

## Client-Server Interaction

On the server side, ASP.NET Core and Blazor Server are in many cases off-loaded by client-side code running Blazor WebAssembly, Cuasality Engine, Unity3D, and SignalR. The server is only responsible for feeding new game state data fragments to clients on a need-only basis. Client-side Blazor WebAssembly deals with local interactions within their own immediate game environment (theater of engagement). Players currently within a common theater of engagement are connected via SignalR and they interact synchronously in terms of cause and effect. Players in different theaters of engagement are isolated and asynchronous with respect to other players in other theaters of engagement. This makes the server load light-weight and saves costs on server-side compute. Clients update the server game state as needed, probably optimized using a predictive prefetch algorithm based on a trained Machine Learning model to reduce delays for players when entering or leaving a theater of engagement.

The server also issues heartbeat notifications (probably around 1 Hz) for global entropy and timestamp information to be used in stochastic and synchronization scenarios. Notification event messages are also provided from the server to the player devices to signal when important game state change events take place. The server also provides database service based on Cosmos DB, and identity services based on ION. The database is a best-effort eventually-consistent NoSQL database (Cosmos DB). From the player's perspective, current game state is not guaranteed to be consistent or finalized at all times. In the backstory, this is attributed to the activities of the deity known as "Loki", who is basically a "chaos monkey doing chaos monkey shenanigans". Loki saves us from having to admit that this decentralized synchronization issue is a feature rather than a bug (expected to be a rare occurrence). Finally, client-side Blazor WebAssembly code updates the Ethereum blockchain, and it provides the server with game state updates as well.

## User Experience

ʻOumuamua is a methodical cerebral strategic game. It is not a spinal-twitch reflex game. Player experience is more like that of a military strategist in the Churchill War Room, rather than that of the infantry soldier in hand-to-hand battlefield combat. ʻOumuamua is played in a dashboard console UI. It uses keyboard, mouse, and headset with microphone, to communicate with game components and with other players and AI bots. It makes no use of a traditional gaming controller pad. Most of the UI is focused on communications with other players as well as current game state data. It feels more like you are a day trader sitting at a Bloomberg Trading Terminal, rather than a first-person shooter such as Half-Life. Multiple screens are recommended. Unity3D is used to provide a 3D graphic animations viewport, but it is used typically as view-only eye-candy. For example, if you see an enemy in this Unity3D viewport, you do not interact with it directly. Instead you would issue an executive command to attack, negotiate, or run away. The action you take updates the game state according to the result of the Causality Engine component, and hopefully you gain some token value in the process.

## Ethereum Blockchain

The Ethereum blockchain is used to provide a trustless and immutable record of in-game currency token transfers and a history of all game play state transition hash histories. Initially, during development, the Ropsten public test network will be used to avoid real-world gas costs. During that phase, all gas is obtained from the Ropsten Ethereum Faucet. When it is ready to deploy live, it will switch to a private Ethereum network, which would involve PoS participation from all participating players. Eventually, after sufficient interest in the game is reached, the game would switch to the Ethereum Mainnet network (which would need external investor Eth funding). The ultimate goal is to bootstrap a new crypto asset token that is of real-world value on a significant and trusted blockchain.

Smart contracts must be developed and deployed to support all player-player interactions (Player contracts), as well as primeval contracts that insure economic stability and fairness within the overall game (Odin contracts). Each player has their own private key that represents an account on the blockchain. Each player can invoke a contract using digitally signed client-side WASM code (provided by any compliant web server). However, each player contract execution must be verified by other players in the same theater of engagement to be accepted by that contract (to prevent out-of-game hacking). Odin contracts can only be invoked by valid player contracts. Migrations to new Odin contracts are contractually governed in a decentralized and democratic manner by way of a universal player referendum Odin contract.

Some thought has to go into how to identify players in a pseudonymous manner that allows the game to verify that each user is a unique individual human being, and not a cloned bot or an AI. One physical human must have no more than one account, and each player must be a real human being rather than a bot. These rules are necessary to avoid Cybil attacks and unfair token wealth accumulation. Also, super-human AI is just around the corner, so it is important to be able to prevent such unfair competition. These requirements may seem impossible to achieve, but that is what they thought about Byzantine Fault Tolerance (BFT) until Bitcoin came along. Perhaps machine learning heuristics can be used to perform Turing tests on players that seem to be more mutually coordinated than normal, or who are more skilled than normal. If no automated solution can be found, we may have to discard the lofty goal of pseudonymity, and use some sort of biometric challenge may become necessary. BTW, this problem is one of my concerns with PoS in general, which Ethereum is now transitioning to. 

## Decentralized Computing

To make the game scale to a massive number of simultaneous players, most computing executes on a peer-to-peer bases. To a great extent, this makes a central game server mostly unnecessary, and any compliant web server that provides the properly digitally signed client-side WASM code will suffice as a means to bootstrap the game into the client device.

Game player devices each handle all game-play processing within isolated groups of players currently involved within an isolated theater of engagement. They interact with each other in real-time by way of SignalR WebSockets. Each player device also invokes Ethereum contracts directly on the Ethereum blockchain without going through a central server.

Each player device also interacts with a distributed Cosmos DB database (at least during development) where all details of game play history for all players are stored. This may be replaced using a combination of Swarm, Whisper, and IPFS (Inter-Planetary File System), but further research needs to be done in this area. 

## Economic Forces

### Pandemic Economics

The Covid-19 pandemic will continue to hammer the real-world economy for at least the remainder of 2020. Human activity and assembly will continue to be severely restricted with the result that unemployment will remain at catastrophic record levels. This situation may remain the new normal for an extended time period. Financial austerity, and ultimately, the specter of literal extinction, will force many people to consider any and every possible solution to their own crises. Any skepticism to new and possibly strange solution proposals will evaporate, especially if a sufficient founder group that provides a demonstrably effective solution can be established. As unlikely and counter-intuitive as this proposition may at first appear, it will in fact be blockchain-based online gaming that provide an effective solution this problem.

Meanwhile, the disabled economy will force businesses to step up efforts to switch to fully automated AI systems to replace human labor. There will be massive research efforts to develop AI technologies, to the point where AI will be applied recursively to develop next generation AI. At that point, AI will rapidly and completely displace human economic activity, until average incomes and employment levels settle towards zero, en masse. At that point, there will be no traditional human-based economy left to go back to, even if and when the pandemic problem is medically solved. And of course, there will be other calamities in the pipeline, such civil violence and global warming.

Additionally, with the dwindling purchasing power of the majority of the population, there will be a reduced demand for products and services as well. So, supply and demand will take simultaneous hits. This will further downsize business economic opportunities and accelerate further unemployment. This will become a rapid and destructive negative feedback loop. How quickly or slowly a medical solution to this pandemic is forthcoming, will have no effect on the eventual ultimate outcome. The end-game will be the same, sooner or later.

People will need a totally new economy to provide subsistence level food, water, and shelter. Humans being humans, society will collectively seek social engagement. The only activity that will remain that allows one human to provide value to another human, while maintain maximal social distancing, will be through a virtual online environment. On-line social networking, gaming, and entertainment will be the only game in town.

### Automation Economics

Robotics, AI, and automation will continue to advance, following a Moore's Law exponential curve (actually a logistic curve in the long term). This is true for any technology where development and innovation feeds on the current state of that same technology. Many traditional jobs have already been eliminated as a result of AI and robotics. But it is not just low-skilled workers being affected. Many highly skilled workers are now being pushed aside as well. This is happening in the engineering, sciences, and medical fields, as well as in law, accounting, and business. Eventually, all human activity will become, in relative terms, less productive, less precise, and ultimately of less economic value, to other humans, in comparison to these new AI-based alternatives.

The human capabilities that will endure the longest are based on social interactions, relationships, and friendships. Online role-playing games will eventually be one of the last economic activities still standing. For many, it will become their only remaining career and income opportunity.

### Karma Crypto Token

Karma crypto token will incentivizes development and community participation in this project. Karma will be distributed to users based on time spent interacting within the game. This will be a reverse-income-tax or a guaranteed basic income.  It would represent a reversal of a traditional Central Bank, such as the US Federal Reserve. Instead of a Central Bank creating fiat money and handing it to the private banking system to lend back to the government with interest (weird system), it would instead, reward players directly. Committed players would benefit the most. There will be exchange between Karma and real-world currencies at prevailing market exchange rates.

Note that Bitcoin was a direct response to the 2008 world financial collapse that grew out of secrecy, corruption, and self-dealing. In a similar way, Karma could become a response to the Covid-19 pandemic and the resulting global economic collapse.

## Collective Philanthropy

TODO

## An Example Game: The ʻOumuamua Backstory

NOTE: This platform is a pluggable game architecture. Anyone can create a game that runs in this platform. The features that they all have in common is the underlying decentralized structure and shared Ethereum blockchain. This backstory describes an example of a game that could run in this distributed game engine.

On 19 October 2017, ʻOumuamua became the first detected interstellar object passing through our Solar System. In 2025, it is discovered to be of intergalactic origin, and after extensive analysis, it becomes apparent that it was designed and deployed by a distant advanced civilization to provide access to a wormhole nexus network known as "Yggdrasil" that leads to many other galaxies in our universe. It was designed by "Óðinn Father of All" to be a mathematical puzzle, so that any life form intelligent enough to solve it would be capable of using it to travel and communicate anywhere through space and time, virtually instantaneously.

Ultimately, this nexus network enables space-time exploration, which first becomes technologically feasible for humanity in 2030, and after another 20 years of intensive robot and AI assisted technological development, in 2050, the first humans and their robot companions begin to travel in space-time via the wormhole nexus network. Many distant worlds are explored and much technology is obtained, such as ultra-powerful quantum computing devices, obtained from many other highly advanced inter-galactic societies. These technologies are communicated back to earth via nexus network quantum entanglement, which rapidly accelerates further technological developments on earth. These technological advancements exponentially accelerate the rate of human egress during the Exodus phase.

### Game Play Level-1: "Exodus Level"

By 2050, humanity has utterly and irreversibly destroyed the ecology and economy on earth. However, the new-found ultra-powerful technologies learned from other cosmic cultures rapidly accelerate new science and computing devices on earth, making it possible to safely escape the fatal and unequivocal earthly global collapse. This is the time period known as the "Exodus".

Each player begins at Level-1 game play as part of this mass exodus from earth around 2055. If the player accumulates sufficient karma crypto token value (gained via battle, theft, deception, trade, etc.) before death (due to battle, starvation, accident, disease, etc.), then they progress to Level-2. If they do not achieve sufficient karma in Level-1, they are reincarnated back into Level-1, and retain their previously accumulated karma token value (which could be negative). Note that trickle down karma (also known as "Manna") is provided as an inverted tax (i.e. GMI, or "Guaranteed Minimum Income"), that supports a subsistence level life style. Players are incentivized to increase their wealth in more effective and proactive ways, which usually involves risk and karma stake/expenditure, to get ahead in the game towards Level-2. Karma crypto token value is gained by way of battle, theft, deception, and trade via smart contracts between players. Note that karma is transacted via smart contracts on the Ethereum blockchain in the real world which represents value that can be taken out-of-game at prevailing exchange rates.

### Game Play Level-2: "Spiritual Level"

After millions of years, an enormous multiverse becomes heavily traveled and populated by the hybrid descendants of the original human and robotic Exodus of 2055 (along with many alien species from other galaxies). Much of the original true earthly Exodus story is lost or corrupted, and eventually becomes a large fragmented religious construct, known as the "Humanity". It is based on assorted holy scriptures (mostly apocryphal) that evolve into what is collectively known as the "Human Testament".

A splinter group of one priestly caste in the Humanity religion makes periodic pilgrimages back to earth (which is totally uninhabitable it this point). Eventually they discover ancient archeological records on earth that refer to the "Church of the SubGenius" (see: https://en.wikipedia.org/wiki/Church_of_the_SubGenius), which it develops into the "Human Testament 2.0". This forms the basis of a pervasive and powerful religion of enormous political importance in many regions of the multiverse. Many other minor fragmented groups spin off in other religious directions, based on other ancient scriptural discoveries. One of these, for example, is Discordianism (https://en.wikipedia.org/wiki/Discordianism). Others are based on Scientology, various Cargo Cults, and the writings of Joseph Smith, Ayn Rand, Michel Foucault, Noam Chomsky, Karl Marx, and Snorri Sturluson.

Karma crypto token value is gained by way of battle, theft, deception, and trade, but also, providing consulting services and mercenary services to other players can be profitable. Additionally, deals can be made with religious leaders and spiritual oracle bots to provide propaganda and apologetics on behalf of various religious movements to prosthelytize other players via smart contracts.

Upon death in Level-2, if the player does not achieve sufficient karma, they are reincarnated back into Level-2, retaining their accumulated karma. If a player dies with sufficient karma, they metamorphose into a deity in Level-3.

### Game Play Level-3 "Valhalla Level"

In Level-3, players discover deeper truths about the cosmos and consciousness. Eventually they discover the computational fabric of reality, which they discover can be hacked, to tamper with reality. In this way, Level-3 players are actually the immortal gods who control aspects of Level-1 and Level-2 game play for mortal players. For this reason, Level-3 god players are worshiped by Level-1 and Level-2 mortal players. Mortal players are incentivized to voluntarily worship these god players primarily due to the benefit and harm they can impose on mortal players. When a Level-3 god communicates with a Level-1 or Level-2 player, they are experienced as auditory and visual hallucinations. It is very risky for mortal players to not heed these godly communications and act accordingly. This is because a god player can manipulate win-and-loss as well as life-and-death outcomes for lesser mortal players (in capricious ways). In return for their worship, gods may manage and administer game play outcomes for lesser mortal players in a benevolent manner. Note that god players may be kind or cruel, forgiving or vindictive. It is their arbitrary choice.

However, god players are incentivized to not harm or kill-off mortal players too frequently. This is because the number of living devotees that a god has conscripted determines their own karma accumulation, which represents real world crypto value. Also, killing always costs some karma which is calculated in mysterious ways. If one god attempts to inflict harm on a mortal, another more powerful god (with more karma) can be invoked to mitigate that harm. High karma gods have more influence and therefore greater earning power going forward. In this way there are more powerful and less powerful gods, thus, the pantheon of gods is a competitive and gamified realm.

Note that deities earn karma by accumulating followers via smart contracts, in addition to the other forms of revenue generating activities described in Level-1 and Level-2.

### Special Events: The Wild Hunt and Ragnarök

Special invitation-only events will be scheduled exclusively for god players that involve supernatural hunts and cosmic battles...

* The Wild Hunt - See: https://en.wikipedia.org/wiki/Wild_Hunt
* Ragnarök Battle - See: https://en.wikipedia.org/wiki/Ragnar%C3%B6k

## Extended Vision

A persistent virtual world in a MMRPG (massively multiplayer role-playing game) is the perfect platform for my ideas on bridging between the virtual world and the physical world. Many MMRPGs already feature in-game virtual careers, professions, markets, and economies. I want to explore ways of extending that out into a real-world blockchain to support a crypto-currency-based real-world financial game-theoretic society. A virtual-physical hybrid platform would result. Some new professions will evolve on this hybrid platform, as some enterprising and creative players devise markets and services, so that real human players can provide useful paid-for serves to other humans in the real world.
All we need to do is provide the hybrid blockchain platform and programmability, and then let the community do the rest.

Example professions would be consulting and training, in areas related to game play strategy as well as real-world education topics, like history and calculus. Imagine merging a Coursera-like MOOC into EVE Online. Another service offering could be a decentralized currency exchange to make an Ethereum game token fungible and liquid with other financial assets. Sort of like EVE Online combined with Ethereum and Binance. Social networking capabilities could be incorporated as well. Sort of like Facebook, but more decentralized and less corrupt, along the lines of Steemit (a blockchain-based blogging and social media website). The result is a Game, a MOOC, a Social Network, and a crypto-token. Ideas from UBI (Universal Basic Income) would implement a virtual reverse taxation, which would seed the economy on an ongoing basis. Many issues to work out to ensure fairness and usability. Do you want to help with this project?

## Game Causality Engine

My plan does not involve transferring ownership of individual in-game objects. That would be an in-game accounting nightmare and the volume of transactions would be too high for most blockchains today. It would also be too detailed and boring for a player to deal with in a typical MMORPG environment. Player actions need to be much higher level and strategic. Much coarser grained.

Instead, each high-level action taken by a player is scored and the consequences that result simply increase or decrease various player properties (health, power, karma, etc.) associated with that player. After each player action, the current game state and player properties are updated (Causality Engine). The updated game state snapshot and associated player properties are stored as a transaction record in a distributed database (Cosmos DB). Game state is stored as a cryptographic hash and metadata related to that action (e.g. player identities involved, action taken, updated player properties, etc.) are recorded in each database record. Only the hash of this data record is actually stored on an immutable public blockchain (probably Ethereum) purely for the purpose of immutability to keep hackers from cheating game mechanics. This aspect of blockchain usage has nothing to do with in-game crypto tokens (the player property known as "karma" is used for that purpose).

All player properties are used to varying degrees in calculating various outcomes of each subsequent player interaction within the game. Each such outcome is calculated using a Markov Matrix containing state transition probabilities. These probabilities represent (at a macroscopic level) all possible causality laws that determine all future game state outcomes in game-based virtual reality. These state transition probabilities can be adjusted, within reason, by god players if they are willing to spend their own karma to do so. Various player properties affect stochastic outcomes that result from player actions, according to this Markov process. For example, the Health property influences the risk of dying as a result of any given action that may be taken. Another example is power, which influences the heuristics of gaining or losing various player properties (i.e. power, karma, or life, etc.), in activities (e.g. battle, exploration, etc.).

The karma property is special in that it is the only player property that represents intrinsic in-game token value, which is defined by a smart contract. Karma is spent or wagered in various situations as a means of pursuing further karma wealth gain. As a result, karma may be gained or lost in each player action. Exchanging to external crypto currencies and tokens is entirely outside the realm of the game itself, but to the degree that the in-game karma token accrues value to actual players, it would presumably become exchangeable via external exchanges.

## Development Plan

I am just starting this project so not much done yet. I started with an ASP.NET Core website with Blazor WebAssembly and SignalR. It will eventually use ION (MS blockchain-based Identity Overlay Network) for decentralized authentication, Unity3D for game engine, and the Nethereum library to interact with smart contracts on the Ethereum blockchain network. These smart contracts will bridge between the persistent game state and the real world in interesting economic ways. It will be an MMRPG style game, like EVE Online. Game play will implement a stochastic Markov process with configurable rules and constraints. God players can inflence the probabilities in this Markov process. Non-player entities (friend and foe) and advisory chat bots will be AI driven using GANS and reinforcement learning algorithms. Players can communicate and collaborate with other players and participate in Ethereum-based smart contracts via a dashboard UI.

Just as the code for this project is open source, the backstory, graphic art, music, and sound effects are also all open source. Everyone is welcome to contribute or fork code, story, audio and art. Initially the story is only a glimmer of a hint of a concept. Hopefully others can supply the creativity to help move it forward.

The hyper-deity, known as Odin (Óðinn), in code, is a collection of smart contracts, which are designed to adjust economic factors and support player engagement to improve overall game enjoyment and stability. It is implemented in a carefully crafted set of Ethereum-based smart contracts. It automatically tweaks game engine parameters and probabilities to keep the game play stable for all players and prevents certain winner-takes-all scenarios and various dead-end states. Recall that in the backstory, it is "Odin" who creates the ʻOumuamua interstellar object to enable the connection between the present time and place with the distant future and distant destinations in the multiverse. So, "Odin" represents both the central programmatic manager component in the game software infrastructure as well as the key ruler character in the underlying backstory.

## Time Travel Limitations

Based on currently understood general relativity and quantum mechanics, and also in the interest of the plausibility of the game backstory, the nexus wormhole only permits time travel back and forth between points in time subsequent to the moment when such time travel is initiated. You can freely travel to the future, and you can then return to the present. However, you cannot initiate any trip that leads into the past relative to the time that the trip is initiated. If you could, that would imply many thought experiments with nasty logical contradictions, such as what would happen to you if you were able to go back in time and kill one of your own direct ancestors? This possibility would also ruin many aspects of the plausibility of the backstory for the game, because players could hypothetically go back in time and destroy the game that they were in. That is simply not a plausible storyline.

## The Althing and Big Bang Banishment

In actual fact, direct backward time travel is technically possible according to certain solutions in general relativity, but they only appear in extremely bizarre situations, such as within a rotating black hole. If you found yourself in such an environment, you would forever then be cut off from the rest of the universe including all other players in the game, never to be heard from again. There is no way out of such a black hole predicament. That is used to deal with repeat offenders that attempt to cheat the game or who are socially abhorrent within the game. Players could then petition Odin to make a smart contract executive decision to deal with the incorrigibly offensive player to just "accidently" run into such as rotating black hole that directly transports that player back to the singularity known as the big bang, approximately 13.77 billion years ago, losing all karma accumulated up to that point. I would recommend that this "feature" be applied in the most sparingly manner, since censorship itself tends to be an evil when abused. This feature would be implemented by way of actual physical world human intervention, by way of a petition calling for a game wide referendum vote.

This voting mechanism for banning players back to the big bang is known as the Althing (Alþing) and it takes place in a mystical but beautiful open-air parliament known as the Thingvellir (Þingvellir).

## Programming Topics

* [https://docs.microsoft.com/en-us/aspnet/signalr](https://docs.microsoft.com/en-us/aspnet/signalr)
* [https://webplatform.github.io/docs/concepts/Internet_and_Web/webrtc](https://webplatform.github.io/docs/concepts/Internet_and_Web/webrtc)
* [http://blazorhelpwebsite.com/Blog/tabid/61/EntryId/4324/Connecting-Blazor-to-Azure-SignalR-Service-updated-to-Preview-8.aspx](http://blazorhelpwebsite.com/Blog/tabid/61/EntryId/4324/Connecting-Blazor-to-Azure-SignalR-Service-updated-to-Preview-8.aspx)
* [https://docs.microsoft.com/en-us/aspnet/core/blazor/?view=aspnetcore-3.1](https://docs.microsoft.com/en-us/aspnet/core/blazor/?view=aspnetcore-3.1)
* [https://azure.microsoft.com/en-us/services/functions](https://azure.microsoft.com/en-us/services/functions)
* [https://github.com/decentralized-identity/ion](https://github.com/decentralized-identity/ion)
* [https://docs.microsoft.com/en-us/aspnet/core/tutorials/signalr-blazor-webassembly?view=aspnetcore-3.1&tabs=visual-studio](https://docs.microsoft.com/en-us/aspnet/core/tutorials/signalr-blazor-webassembly?view=aspnetcore-3.1&tabs=visual-studio)
* [https://docs.unity3d.com/Manual/Webgl-Server-configuration-for-WebAssembly-streaming.html](https://docs.unity3d.com/Manual/Webgl-Server-configuration-for-WebAssembly-streaming.html)
* [http://docs.nethereum.com/en/latest](http://docs.nethereum.com/en/latest)
* [https://github.com/ewasm/design](https://github.com/ewasm/design)
* [https://ethereum.org/en/developers](https://ethereum.org/en/developers)
* [https://docs.microsoft.com/en-us/azure/notification-hubs/notification-hubs-push-notification-overview](https://docs.microsoft.com/en-us/azure/notification-hubs/notification-hubs-push-notification-overview)
* [https://docs.microsoft.com/en-us/azure/cosmos-db/introduction](https://docs.microsoft.com/en-us/azure/cosmos-db/introduction)


