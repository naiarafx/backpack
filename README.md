# Define data
v <- c(11,32,18,27,5,36,18,42,43) # valor
p <- c(9,34,15,27,7,34,18,43,42) # peso
P <- 150 # peso max
n <- lengh(v) # numero de itens

# Define fitness function
mochila <- function(x) {
  f <- sum(x * v)
  penalty <- sum(p) * abs(sum(x * p) - P)
  f - penalty
}

# Rn SGA
SGA <- ga(type="binary",
  fitness=mochila,
  nBits=n,
  maxiter=100, # Max de geracoes
  run=200,     # parar se nao melhorar
  popSize-=100, 
  seed=101)
