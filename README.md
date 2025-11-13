# Two Monte Carlo Models

## Simple Model: Estimating Pi ($\pi$)

This model uses randomness to find a physical constant. The core idea is to compare the area of a circle to the area of the square that contains it.

How the Model Works

- The Setup: Imagine a perfect square "dartboard." Inside this square, a circle is drawn that perfectly touches all four sides.
- The "Knowns": We know the area of the square (let's say its side is 2 units, so its area is $2 \times 2 = 4$). We also know the formula for the circle's area is $\pi \cdot r^2$ (its radius is 1, so the area is just $\pi$). The ratio of the areas is $\text{Area}_{\text{Circle}} / \text{Area}_{\text{Square}} = \pi / 4$.
- The Simulation: We "throw" thousands of "darts" (random points) at the square. We generate a random (x, y) coordinate for each dart.
- The Test: For each dart, we check if it landed inside the circle. We do this by calculating its distance from the center. If the distance is less than the radius (1), it's a "hit."
- The Result: We count the total number of darts thrown (total) and the number of darts that landed inside the circle (hits).
- The Calculation: The ratio of hits / total should be approximately the same as the ratio of the areas ($\pi / 4$).

Therefore, $\pi \approx 4 \cdot (\text{hits} / \text{total})$.

The more darts we throw, the closer our estimate of $\pi$ gets to the true value. This demonstrates the Law of Large Numbers.

## Complex Model: Financial Project Forecasting

This model is used to determine the probability of a project being profitable when many of its key inputs are uncertain.

The core idea is to stop using single "best guesses" (like "Revenue will be $1M") and instead use probability distributions (like "Revenue is most likely $1M, but could be anywhere from $700k to $1.2M").

How the Model Works
1. The Setup: A company wants to know the 5-year profit for a new product. The profit is calculated with a formula: Profit = (Revenue - Operating_Costs) * 5 - Initial_Investment

2. The Problem: The Initial_Investment, Revenue, and Operating_Costs are not known for sure.

3. Defining Distributions: Instead of single numbers, the model defines a range of possibilities for each variable:

  - Initial Investment: A normal distribution (bell curve) centered at $500,000, since it's likely to be close to that but could be a bit higher or lower.

  - Annual Revenue: A uniform distribution (equal chance) between $200,000 and $300,000, reflecting market uncertainty.

  - Annual Operating Costs: A triangular distribution (with a most likely, min, and max value) centered at $150,000.

4. The Simulation (One Trial): The model runs one scenario. It randomly pulls one value from each distribution (e.g., Investment=$510k, Revenue=$220k, Costs=$160k) and calculates the profit for that single trial.

5. The Loop: The model repeats this simulation 10,000 times. Each time, it gets a different set of random inputs and a different final profit. Some trials might result in a $100,000 profit, while others might result in a $75,000 loss.

6. The Result: The model produces a list of 10,000 possible profit outcomes.

7. The Analysis: This list is plotted on a histogram, which shows the distribution of possible profits. From this, you can answer critical business questions:

What is the average expected profit?

What is the probability of losing money? (e.g., "In 3,100 of the 10,000 trials, the profit was negative, so there is a 31% chance of losing money.")

What is the most likely range of outcomes (e.g., 90% chance the final profit is between -$80,000 and +$210,000).
