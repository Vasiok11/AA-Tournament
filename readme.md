# Opportunistic Predator Strategy

## Overview
This repository contains an implementation of the "womp_womp" strategy for the Iterated Prisoner's Dilemma tournament. The algorithm is designed to maximize points by strategically balancing defection and cooperation based on opponent behavior patterns and mathematical expected value optimization.

## Strategy Logic

### Core Principles
The strategy operates on the following key principles:

1. **Expected Value Optimization**: Against random opponents, defection has a higher expected value than cooperation (3 points vs 2 points on average), so the default behavior favors defection.

2. **Opponent Classification**: The algorithm classifies opponents into three categories based on their cooperation rate:
   - Highly cooperative (>80% cooperation)
   - Moderately cooperative (50-80% cooperation)
   - Uncooperative (<50% cooperation)

3. **Adaptive Response**: Different response patterns are applied based on the opponent's classification:
   - Against highly cooperative opponents: Periodic defection (every 3rd move) to exploit their generosity
   - Against moderately cooperative opponents: Strategic mix of cooperation and defection
   - Against uncooperative opponents: Primarily defection with limited forgiveness

4. **Pattern Recognition**: The algorithm detects common patterns like:
   - Alternating moves (0,1,0,1...)
   - Tit-for-tat behavior (copying previous moves)

5. **Temporal Strategy**: Behavior changes based on the stage of the game:
   - Initial move: Cooperate to establish trust
   - Mid-game: Apply adaptive strategies based on opponent behavior
   - End-game: Increase defection frequency when the end is near

### Decision Workflow

1. First move is always cooperation to establish initial goodwill
2. Calculate opponent's overall cooperation rate and recent behavior trend
3. Determine if we're in the end-game phase (if round count is known)
4. Select strategy based on opponent classification:
   - For highly cooperative opponents: Exploit with periodic defection
   - For moderately cooperative opponents: Strategic mix of forgiveness and exploitation
   - For uncooperative opponents: Primarily defect with limited cooperation
5. Apply pattern recognition to detect and exploit predictable behaviors
6. In end-game, switch to more aggressive defection
7. Default to 60% defection / 40% cooperation ratio against uncertain opponents