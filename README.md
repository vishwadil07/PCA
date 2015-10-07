het.mat <- polycor::hetcor(sapply(data, as.factor))$cor
kmo <- KMO(het.mat)
fit <-  psych::principal(het.mat,nfactors = 6,rotate = "varimax")
load <- xtable::xtable(unclass(fit$loadings))
plot(fit$values, type="b", ylab="Eigenvalues",
     xlab="Component", lab=c(10,10,10))
