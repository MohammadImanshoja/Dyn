# Task: Population dynamics and model building

## Lotka-Volterra

Simple Predator-Prey relationships can be modeled using the Lotka-Volterra equation defined as:
\begin{align}
\frac{dX}{dt} &=  aX  - b XY  \qquad &a,b > 0\\
\frac{dY}{dt} &= -cY + d XY\qquad &c,d > 0,
\end{align}
where X is the prey, Y is the predator and a,b,c,d are parameters relating the two species.

Tasks:
 1. Using the Lotka-Volterra equation, run a stable (oscillating) simulation of the Predator-Prey relationship and plot it with the populations as a function of the time and the populations one over the other (that is e.g. prey over predator). Try to experiment with the parameters and the integration step sizes. Find some nice parameters and initial conditions.
 
 2. Extend the naive Lotka-Volterra function to the logistic Lotka-Volterra function:
\begin{align}
\frac{dX}{dt} &=  a(1 -\frac{X}{K})X  - b XY  \qquad &a,b,K > 0\\
\frac{dY}{dt} &= -cY + d XY\qquad &c,d > 0,
\end{align}
adding the carrying capacity K and again run a simulation for the system. Plot the populations one over another and as functions of the time. What can you see? Does the trajectory change? Can you find non-trivial fix points (numerically)? 
 3. Plot the vector fields for the two simulations with the population of the predators on the Y axis and the prey on the X axis. Mark the fixpoints in your plots. Use the streamplot from matplotlib. Color the arrows accoring to the speed of the vector.
 4. Food chain: 
    - Introduce a competing predator species to the equation. We call the new predator the uber-predator because it preys on the previous predator that now we call the weak predator. Apply the assumption that the weak predators do not decease due to natural causes but only by interaction with the uber-predator. The uber-predators do die of old age and obviously a sated uber-predator also likes to reproduce. The uber-predators ignore the prey (no interaction).
    Expand the model starting from the logistic Lotka-Volterra.
    - Estimate the parameters of your model so that you can fit the function in lotka_volterra_prey-predator-uberpredator.csv. A scoring function such as the sum of the difference squares might be a good starting point but any metric which allows for proper minimization is allowed. The carrying capacity is between 5 and 15. All the other parameters will be between 0.1 and 1.0.
    - Run a simulation until t = 50. Estimate the non-trivial fixpoint and calculate the error to the analytical solution.
    - Plot for each pair of species a plot with one species over the other.
    - <b>Bonus</b>: Introduce a second competing prey species. The two prey species are essentially the same in the way they interact with each other and thus have a shared carrying capacity and the parameter determining their interaction with each other is 0.5. Their interaction with the predators is the same only that the second prey is preyed upon half as often (and thus only nurtures the predator only half as often). Here is the twist: the second prey is only an evolved first prey. Through selective pressure the first prey evolved to be more resilient and evolution is unidirectional (no evolving back from the second prey to the first prey). The mutation rate from prey one to prey two is 0.01. Start the simulation assuming there are no evolved species yet at time t = 0.
    Using the parameters you estimated in task 4 plot a short simulation of the system (t = 10) with the species over time. Is there a species which dies out in the long run (t -> ∞)? Assume you cannot find that out from just plotting a long simulation. 



