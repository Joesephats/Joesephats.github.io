# Player State Machine

```mermaid
stateDiagram-v2

    Idle --> Walk
    Idle --> Run
    Idle --> Jump
    Idle --> Attack
    Walk --> Attack
    Walk --> Idle
    Run --> Dash_Attack
    Run --> Idle
    Jump --> Jump_Attack
    Jump --> Idle
    Attack --> Recovery
    Jump_Attack --> Recovery
    Dash_Attack --> Recovery
    Recovery --> Idle

    state "Jump Attack" as Jump_Attack
    state "Dash Attack" as Dash_Attack
```

The player has multiple states that control the player's animation and velocity.\
\
The attack states also check for hits, and move to the recovery state.
```mermaid
stateDiagram-v2
    Attack --> Recovery
    Jump_Attack --> Recovery
    Dash_Attack --> Recovery
```
The recovery state prevents input for a short time, then moves to the idle state.

