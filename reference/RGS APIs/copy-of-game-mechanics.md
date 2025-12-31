---
title: Operator APIs
excerpt: >-
  Explore the core gameplay flow, including player authorization, game
  initialization, wagering actions, and retrieval of game history.
deprecated: false
hidden: true
metadata:
  robots: index
---
<Columns layout="auto">
  <Column>
    <Accordion title="🔐 Authorize Player" icon="user-check">
      Verifies the player and initiates a new game session.
    </Accordion>
  </Column>
  <Column>
    <Accordion title="⚙️ Game Settings (Initial Configuration)" icon="cogs">
      Returns the initial game configuration required to begin gameplay.
    </Accordion>
  </Column>
  <Column>
    <Accordion title="🎲 Wager (Spin / Bet)" icon="dice">
      Executes a spin or wager action during gameplay.
    </Accordion>
  </Column>
  <Column>
    <Accordion title="📜 Game History" icon="history">
      Retrieves past wagers and outcomes for a specific game session.
    </Accordion>
  </Column>
</Columns>

These endpoints are typically called in sequence during an active game session.