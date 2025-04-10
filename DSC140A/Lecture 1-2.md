# Prediction

![[Pasted image 20250410000534.png]]

# Distributions

## Normal Distribution
$$
X \sim \text{Normal } (\mu, \sigma^{2})
$$
$$
f(x) = \frac{1}{\sqrt{ 2\pi \sigma^{2} }}e^{(-\frac{(x-\mu)^{2})}{2\sigma^{2}})}
$$
$$
x \in(-\infty, \infty)
$$
![[Pasted image 20250410001552.png]]
Can model 
- height
- measurement error (noise)
## Lognormal 
$$
X \sim \text{Lognormal } (\mu, \sigma^{2})
$$
$$
f(x) = \frac{1}{\sigma \sqrt{ 2\pi \sigma^{2} }}e^{(-\frac{(\log(x)-\mu)^{2})}{2\sigma^{2}})}
$$
$$
x \in [0, \infty)
$$
$$
X \sim \text{exp}(\mu+\sigma Z)
$$
$$
\text{where } Z\sim \text{Normal(0, 1)}
$$
![[Pasted image 20250410001959.png]]
Can Model
- income
- quantities that have a fat tail but must be positive

## Exponential
![[Pasted image 20250410002108.png]]

## Bernoulli
### PMF:
$$
Pr(X=x)=p^x(1-p)^{1-x}
$$
$$
x \in \{0, 1\}
$$
Can model
- repay loan in 2 years
- any probabilistic outcome (non-zero chance of 0 or 1)
## Binomial
### PMF
$$
Pr(X=x) = {n \choose x}p^x(1-p)^{n-x}
$$
$$
x in \{0, 1, \dots ,n\}
$$
$$
X = \sum_{i=1}^nZ_{i}
$$
$$
\text{where } Z_{i} \sim \text{Bernouli(p)} 
$$
![[Pasted image 20250410002621.png]]
Can Model
- number of late payments over last year (n = 12 months)
- number of successes in n trials with n known

## Poisson
$$
X \sim \text{Poisson}(\lambda)
$$
### PMF
$$
Pr(X=x) = \frac{\lambda^xe^{-\lambda}}{x!}
$$
$$
x \in \{0, 1, 2, 3, \dots\}
$$
![[Pasted image 20250410002946.png]]
Can model
- number of ad clicks, site visits, etc
- number of events with n known
- - - 
# Prediction with Parametric Distributions
1. Choose Parametric Distribution for Output of Interest
$$
y_{i} = \text{score for student i on PS1} \in\{0, 1,2,\dots,7\}
$$
$$
y_{i} \sim \text{Binomial(n, p)}=\text{Binomial(7, p)}
$$
2. Express Distribution Parameters using Features
$$
x_{i}=\text{student i in study group} 
$$
$$
y_{i} \sim \text{Binomial}(7, p(x_{i}))
$$

- - - 
# Maximum Likelihood Estimation
I have a special coin, what is the probability that it will land heads?
Flipping a few times...
1 1 0 1 1
$$
p = \frac{4}{5}
$$
Data: $D=\{x_{1}, x_{2}, \dots,x_{n}\}$ iid
Parametric Distribution: $x_{i} \sim \text{Bernouli}(\theta)$
### MLE for Bernoulli
$$
p_{r}(X=x|\theta)=\theta^{x_{i}}(1-\theta)^{1-x_{i}}
$$
This is saying that when $x_{i}=0 \rightarrow \theta$,  $x_{i}=0 \rightarrow 1-\theta$
$$
L(\theta)=P_{r}(D|\theta)=P_{r}(x_{1},x_{2},\dots,x_{n}|\theta)=P_{r}(x_{1}|\theta)\times P_{r}(x_{2}|\theta)\times P_{r}(x_{n}|\theta)
$$
$$
= \Pi_{i=1}^nP_{r}(x_{i}|\theta)
$$
$$
\hat{\theta}_{MLE} \in {\text{argmax }L(\theta)}_{\theta \in[0, 1]}
$$
$$
l(\theta)=\sum_{i=1}^n\log Pr_{x_{i}|\theta}=\sum_{i=1}^n\log (\theta^{x_{i}}(1-\theta)^{1-x_{i}})
$$
$$
=\sum_{i=1}^nx_{i}\log \theta+(1-x_{i})\log(1-\theta)
$$
$$
=\log \theta \sum_{i=1}^nx_{i}+\log(1-\theta)\sum_{i=1}^n 1-x_{i}
$$
$$
=\log \theta \sum_{i=1}^n x_{i} + \log(1-\theta)\left( n - \sum_{i=1}^nx_{i} \right)
$$
$$
\log \theta \sum_{i=1}^nx_{i}+n\log(1-\theta)-\log(1-\theta)\sum_{i=1}^nx_{i}
$$
$$
\hat{\theta}_{MLE} = \frac{\partial l(\theta)}{\partial \theta} = 0
$$
$$
\frac{1}{\theta}\sum_{i=1}^nx_{i}-\frac{n}{1-\theta}+\frac{\sum_{i=1}^nx_{i}}{1-\theta} = 0
$$
$$
\frac{1-\theta}{\theta}=\frac{-\sum_{i=1}^nx_{i}+n}{\sum x_{i}}
$$
$$
\frac{1}{\theta}-1=-1+\frac{n}{\sum x_{i}}
$$
$$
\boxed{\hat{\theta}_{MLE}=\frac{\sum_{i=1}^nx_{i}}{n}}
$$
### MLE for Normal
$$
L(\theta)=\Pi_{i=1}^nf(x_{i}|\theta)
$$
$$
l(\theta)=\sum_{i=1}^n\log (f(x_{i}|\theta))=\sum_{i=1}^n\ln\left[ \frac{1}{\sqrt{ 2\sigma^{2} }}e^{-\frac{(x-\mu)^{2}}{2\sigma^{2}}} \right]
$$
$$
=\frac{n}{2}\ln(2\sigma^{2})-\frac{1}{2\sigma^{2}}\sum_{i=1}^n(x_{i}-\mu)^{2}
$$
$$
\hat{\mu}_{MLE}=\frac{1}{\sigma^{2}}\sum_{i=1}^nx_{i}-\mu=0
$$
$$
\hat{\mu}_{MLE}=\frac{\sum_{i=1}^nx_{i}}{n}
$$
$$
\hat{\sigma^{2}}_{MLE}=\frac{n}{4\sigma^{2}}+\frac{1}{{2\sigma^{2}}^{2}}\sum_{i=1}^n(x_{i}-\mu)^{2}=0
$$
$$
\hat{\sigma^{2}}_{MLE}=\frac{\sum_{i=1}^n(x_{i}-\mu)^{2}}{n}
$$
Since $\hat{\theta}_{MLE}=(\hat{\mu}_{MLE},\hat{\sigma^{2}}_{MLE})$
$$
\boxed{\hat{\theta_{MLE}}=\left( \frac{\sum_{i=1}^nx_{i}}{n} ,\frac{\sum_{i=1}^n(x_{i}-\mu)^{2}}{n}\right)}
$$


- - - 
# Sampling Distributions
![[Pasted image 20250410014845.png]]
![[Pasted image 20250410014915.png]]
$$
\text{Theorem: }\boxed{\hat{\theta}_{MLE}\sim \text{Normal}\left(\theta, \frac{1}{n}\text{Var}(\hat{\theta}_{MLE})\right)} \text{ as n} \rightarrow \infty
$$
1. $\mathbb{E}(\hat{\theta}_{MLE})=\theta \rightarrow \text{Bias}(\hat{\theta}_{MLE})=(\mathbb{E}(\hat{\theta}_{MLE})-\theta)^{2}=0$
2. $\frac{1}{n}\text{Var}(\hat{\theta}_{MLE})=0 \rightarrow \hat{\theta}_{MLE}=\theta$

