---
title: Terminology & Concepts
deprecated: false
hidden: false
metadata:
  robots: index
---
## Core Concepts

### **Tenant (Operator / Casino)**
A **Tenant**, also referred to as an **Operator**, is a casino platform that hosts games from multiple game providers.  
The Operator is responsible for:
- Managing players
- Maintaining player wallets and balances
- Handling game selection and gameplay flow

**Example:**  
**Rebet** ([https://rebet.app](https://rebet.app)) is a casino operator that allows players to:
- Browse available games
- Launch a selected game
- Play using their wallet balance  

All player, wallet, and gameplay orchestration is handled by the Operator.

---

### **GCP (Game Content Provider)**
The **Game Content Provider (GCP)** is responsible for building and owning the games.  
The Operator integrates these games and makes them available to players for gameplay.

---

### **RGS (Remote Gaming Server)**
The **Remote Gaming Server (RGS)** is operated by the Game Provider and manages both **frontend and backend game logic**.

RGS responsibilities include:
- Providing the game **launch URL**
- Handling **player authentication**
- Processing **bet, win, and rollback transactions**
- Managing game configurations and gameplay rules
- Communicating with the Operator (Tenant) during gameplay

---

## Technical Terms

- **`playerState`**  
  Represents the current state of a player.  
  During authorization, the Operator receives the player state and validates:
  - `freeSpins`
  - `lastBet`
  - `freeSpinsWinAmount`

- **`gameState`**  
  Represents the current state of an ongoing game round.

- **`code`**  
  Unique game code used to fetch a game’s configuration.

---

From the next sections, we will walk through the **step-by-step integration process** between the Operator and the RGS.