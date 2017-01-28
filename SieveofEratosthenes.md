#Sieve of Eratosthenes

Finding all prime numbers up to `a` using the Sieve of Eratosthenes:
```R
a <- 1000000

primesfn <- function(sieve, set) {
   p <- set[1]
   n <- set[length(set)]
   if (p^2 > n)
      return(c(sieve, set))
   else {
      set <- set[set %% p != 0] 
      sieve <- c(sieve, p)
      return(primesfn(sieve, set))
  }
}

primes <- primesfn(c(),2:a)
```

How many prime numbers are less than `a`?
```R
length(primes)
# [1] 78498
```

Let `x < a` , is `x` a prime number?
```R
x <- 999931 
is.element(x,primes)
# [1] TRUE

x <- 1000
is.element(x,primes)
# [1] FALSE
```

What is the `k-th` prime?
```R
k <- 100
primes[k]
# [1] 541
```
