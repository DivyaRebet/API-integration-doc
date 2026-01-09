---
title: Terminology & Concepts
deprecated: false
hidden: true
metadata:
  robots: index
---
## Terms

**Tenant**: Casino (Operator/Wallet) which hosts games from multiple game providers, it manages players, their balance through wallet and game play

For example: Rebet (https://rebet.app) is the casino operator which manages players to choose a game from available games and play a particular game with their balance. All that is managed by Operator (Tenant).

**GCP (Game Content Provider)**: GCP is the game provider, which builds the complete games. And operator manages their game for gameplay.

**RGS (Remote Gaming Server)**: RGS manages all the games Front-end and Back-end logic of Game Provider. It helps in game's `launch url` , `authentication, transactions, rollback cases`with Tenant (Operator) and manages game-play configurations

<br />

## Technical Terms

`playerState`: The current state of the player. During authorisation, we receive player state and check `freeSpins`, `lastBet`, `freeSpinsWinAmount`.

`gameState`: The current state of the game round.

`code`: Game code for getting a game's configuration

From next couple of pages we will start integration steps.
