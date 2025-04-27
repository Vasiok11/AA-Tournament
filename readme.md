# The Womp Womp Strategy (Round 2)

## Overview
Building on the "womp_womp" strategy from Round 1, this enhanced version introduces opponent selection capabilities to maximize points in the Iterated Prisoner's Dilemma tournament. The strategy continues to employ strategic defection with calculated cooperation, now with the added dimension of choosing the most profitable opponents.

## Strategy Logic

### Core Principles
The strategy operates on the following key principles:

1. **Defection Dominance**: Against random or unpredictable opponents, defection consistently yields higher expected value, which remains the foundation of this strategy.

2. **Minimal Cooperation**: The algorithm employs cooperation sparingly and only in specific scenarios:
   - Initial move (to establish baseline)
   - When detecting highly predictable cooperative patterns
   - As part of periodic cycles to prevent opponent adaptation

3. **Opponent Classification**: The algorithm tracks opponent behavior to determine:
   - Cooperation rate (rarely used to justify cooperation)
   - Pattern predictability (used to exploit consistent behaviors)
   - Response to our previous moves (to detect adaptability)

4. **Ruthless Optimization**: The primary goal is point maximization rather than mutual benefit, leading to significantly more defections than cooperations.

### Round 2 Enhancements

5. **Opponent Selection Strategy**: The algorithm now intelligently selects which opponents to play against:
   - Prioritizes opponents with high cooperation rates (more exploitable)
   - Calculates expected value from each potential opponent based on past interactions
   - Balances exploitation of known profitable opponents with exploration of new ones

6. **Profitability Scoring**: Each opponent receives a score based on:
   - Average points earned per round against them
   - Their historical cooperation rate
   - Number of rounds already played with them

### Decision Workflow

1. **Move Determination**: 
   - First move is always cooperation to establish a baseline
   - Calculate opponent's cooperation statistics for classification
   - Apply aggressive defection as the default strategy
   - Inject periodic cooperation only when strategically beneficial

2. **Opponent Selection**:
   - Prioritize completely new opponents if available (exploration)
   - Calculate profitability scores for all previously encountered opponents


The strategy aims to identify and repeatedly engage with the most exploitable opponents while maintaining the  defection-based approach from Round 1.