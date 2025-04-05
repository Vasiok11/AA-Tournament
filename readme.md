# The Apex Predator Strategy

## Overview
The "womp_womp" strategy is designed to maximize points through strategic defection against unpredictable opponents, with occasional cooperation only when mathematically advantageous.

## Strategy Logic

### Core Principles
The strategy operates on the following key principles:

1. **Defection Dominance**: Against random or unpredictable opponents, defection consistently yields higher expected value, which forms the foundation of this strategy.

2. **Minimal Cooperation**: The algorithm employs cooperation sparingly and only in specific scenarios:
   - Initial move (to establish baseline)
   - When detecting highly predictable cooperative patterns
   - As part of periodic cycles to prevent opponent adaptation

3. **Opponent Classification**: The algorithm tracks opponent behavior to determine:
   - Cooperation rate (rarely used to justify cooperation)
   - Pattern predictability (used to exploit consistent behaviors)
   - Response to our previous moves (to detect adaptability)

4. **Ruthless Optimization**: The primary goal is point maximization rather than mutual benefit, leading to significantly more defections than cooperations.

### Decision Workflow

1. First move is always cooperation to establish a baseline
2. Calculate opponent's cooperation statistics for classification
3. Apply aggressive defection as the default strategy (60-80% of moves)
4. Inject periodic cooperation only when strategically beneficial:
   - To reset a potentially beneficial pattern
   - To exploit certain predictable opponent behaviors
   - Based on game phase considerations
5. Against random opponents, maintain heavy defection bias for mathematical advantage