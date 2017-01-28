#Sieve of Eratosthenes

Finding all prime numbers up to `a` using the Sieve of Eratosthenes:
```R
a <- 1000000

primosfn <- function(criba, conjunto) {
   p <- conjunto[1]
   n <- conjunto[length(conjunto)]
   if (p^2 > n)
      return(c(criba, conjunto))
   else {
      conjunto <- conjunto[conjunto %% p != 0] 
      criba <- c(criba, p)
      return(primosfn(criba, conjunto))
  }
}

primos <- primosfn(c(),2:a)
```

How many prime numbers are less than `a`?
```R
length(primos)
# [1] 78498
```

Let x < a , is x a prime number?
```R
x <- 999931 
is.element(x,primos)
# [1] TRUE

x <- 1000
is.element(x,primos)
# [1] FALSE
```

What is the k-th prime?
```R
k <- 100
primos[k]
# [1] 541
```
