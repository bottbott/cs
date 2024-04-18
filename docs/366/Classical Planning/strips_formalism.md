The Stanford Research Institute Problem Solver (STRIPS) formalism is a formal
way of stating a planning problem for solving by the solver.

The problem must be described with several parts:

- **Finite set of propositions** $ P $ - defines what is true in this world
- **Initial state** $ I \subseteq P $ - the starting state of the world
- **Goal state** $ G \subseteq P $ - the desired state of the world
- **Actions** $ A $ - a set of actions that can be taken. Each action has a
    pre-condition and effect (additions and deletions). ($ pre_a, add_a, del_a
    $)
    - $ pre_a $ - a set of propositions that must be true for the action to be
        taken
    - $ add_a $ - a set of propositions that will be true after the action is
        taken
    - $ del_a $ - a set of propositions that will be false after the action is
        taken
- **Cost function** $ c: A \rightarrow \mathbb{R}_0^+ $ - a function that
    assigns a cost to each action


A problem is solvable if there is a set of actions that transform the initial
state into the goal state. 

The combination of propositions form a state space. One of the combinations is
our initial state, and then we need to search from there to find a path to the
goal state. However, the state space contains all of the combinations and so
there can be states in the space that do not make sense to the solving of the
problem. 