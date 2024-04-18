Simulated annealing combines the ideas of hill climbing and random walks. Hill
climbings efficacy depends on the region of the search space it starts in, and
random walks have no guidance at all if they do land in an optimal region. 

Simulated annealing is typically paired with random restarts to avoid getting
stuck in local minima and explore the search space more effectively.

Search is set according to a schedule and the random walks have higher 
probability, and then the schedule is adjusted towards more hill climbing. 

## Simulated Annealing Parameters
- **Beta** - puts focus on the hill climbing
- **Temperature** - puts focus on the random walk

## Temperature Schedule
- **Initial Temperature** - $ T_0 $
- **Iteration adjustment** - $ \alpha * i $
- Formula: $ T_i = \frac{T_0}{1 + \alpha * i} $