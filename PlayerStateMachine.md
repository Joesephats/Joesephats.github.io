# Player State Machine

```mermaid
stateDiagram-v2

    Idle --> Walk
    Idle --> Run
    Idle --> Jump
    Idle --> Attack
    Walk --> Attack
    Walk --> Idle
    Walk --> Jump
    Walk --> Run
    Run --> Dash_Attack
    Run --> Idle
    Run --> Walk
    Run --> Jump
    Jump --> Jump_Attack
    Jump --> Idle
    Jump --> Walk
    Jump --> Run
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

    state "Jump Attack" as Jump_Attack
    state "Dash Attack" as Dash_Attack
```
The recovery state prevents input for a short time, then moves to the idle state.
```mermaid
stateDiagram-v2
    Recovery --> Idle
```

