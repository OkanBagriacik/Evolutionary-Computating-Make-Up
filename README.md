# Portfolio Optimization by using Genetic Algorithm
Buying and selling stocks is a very interesting thing. Because stocks can make investors get big profits, but vice versa. To get a big profit, investors need to analyze in predicting stock prices. However, predicting stock prices is a difficult thing to do because stock prices fluctuate rapidly all the time. So that investors need to predict the stock price as short as possible.

Portfolio optimization method is one of the areas that attract the most attention and arouse curiosity in the financial field. Mathematicians and statisticians have regularly tried to find the ideal solution on this topic. This optimization method has been possible since the use of the genetic algorithm. A model was developed using specific stock market data.

![0103-6513-prod-30-e20190144-gf02](https://user-images.githubusercontent.com/48045619/123410221-bbb70f80-d5b7-11eb-8ddf-78635938afa2.jpg)


1.Read the data and combine them into one dataframe.

2.Calculate the historical returns for 3 months, 6 months, 12 months, 24 months and 36 months for each of the stocks.

3.Define Gene (Scalar): A fraction of the total capital assigned to a stock.

4.Define Chromosome (1D Array): Set of genes i.e. fractions of total capital assigned to each stock.
  Check! Sum of each chromosome should be equal to 1.

5.Generate Initial Population (2D Array): A set of randomly generated chromosomes.

6.Fitness function (Define a Function): The Sharpe ratio, S, is a measure for quantifying the performance (Fitness) of the portfolio which works on "Maximisation of return (mean) and minimisation of risk (Variance) simultaneously" and is computed as follows:
S = (µ − r)/σ
Here µ is the return of the portfolio over a specified period or Mean portfolio return, r is the risk-free rate over the same period and σ is the standard deviation of the returns over the specified period or Standard deviation of portfolio return. Mean portfolio return = Mean Return * Fractions of Total Capital (Chromosome). Risk-free rate = 0.0697 ( as per google) Standard deviation of portfolio return = (chromosome * Standard deviation)**2 + Covariance * Respective weights in chromosome.

7.Select Elite Population (Define a Function): It filters the elite chromosomes which have highest returns, which was calculated in fitness function.
8.Mutation: A function that will perform mutation in a chromosome. Randomly we shall choose 2 numbers between 0, 5 and those elements we shall swap.

9.Crossover: Heuristic crossover or Blend Crossover uses the ﬁtness values of two parent chromosomes to ascertain the direction of the search. It moves from worst parent to best parent. The oﬀspring are created according to the equation: Off_spring A = Best Parent + β ∗ ( Best Parent − Worst Parent) Off_spring B = Worst Parent - β ∗ ( Best Parent − Worst Parent)
  Where β is a random number between 0 and 1.
This crossover type is good for real-valued genomes.

10.Next Generation (define a Function): A function which does mutation,mating or crossover based on a probability and builds a new generation of chromosomes.

11.Iterate the process: Iterate the whole process till their is no change in maximum returns or for fixed number of iterations.
