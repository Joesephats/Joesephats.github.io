'''mermaid

stateDiagram

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

'''