# 1
## a
$$

L(\mu,\sigma^{2}|x_{1},\dots,x_{n})=\Pi_{i=1}^nf(x_{i}|\mu,\sigma^{2})
$$
$$
L(\mu,\sigma^{2}|x_{1},\dots,x_{n})=\Pi_{i=1}^n \frac{1}{\sqrt{ 2\sigma^{2} }}e^{-(x_{i}-\mu)^{2}/2\sigma^{2}}
$$
$$
=\boxed{\left( \frac{1}{\sigma \sqrt{ 2\pi }} \right)^ne^{-\frac{1}{2\sigma^{2}}\sum_{i=1}^n(x_{i}-\mu)^{2}}}
$$
## b
$$
L(\mu,\sigma^{2}|x_{1},\dots,x_{n})=\Pi_{i=1}^nf(x_{i}|\mu,\sigma^{2})
$$
$$
l(\mu,\sigma^{2}|x_{1},\dots,x_{n})=\sum_{i=1}^n\ln (f(x_{i}|\mu,\sigma^{2}))=\sum_{i=1}^n\ln\left[ \frac{1}{\sqrt{ 2\sigma^{2} }}e^{-\frac{(x-\mu)^{2}}{2\sigma^{2}}} \right]
$$
$$
=\frac{n}{2}\ln(2\sigma^{2})-\frac{1}{2\sigma^{2}}\sum_{i=1}^n(x_{i}-\mu)^{2}
$$
$$
\frac{{\partial l}}{\partial\mu}=\frac{1}{\sigma^{2}}\sum_{i=1}^nx_{i}-\hat{\mu}_{MLE}=0
$$
$$
\boxed{\hat{\mu}_{MLE}=\frac{\sum_{i=1}^nx_{i}}{n}}
$$
## c
$$
\hat{\mu}_{MLE}=\frac{\sum_{i=1}^nx_{i}}{n}=\bar{X}
$$
$$
\mathbb{E}[\hat{\mu}_{MLE}]=\mathbb{E}\left[ \frac{\sum_{i=1}^nx_{i}}{n}\right]=\frac{1}{n}\mathbb{E}[\sum_{i=1}^nx_{i}]
$$
$$
\frac{1}{n}\sum_{i=1}^n \mathbb{E}[X_{i}]
$$
$$
\text{Since the }X_{i} \text{ are IID R.V, each of the }X_{i} \text{ have the same expectation}
$$
$$
=\frac{1}{n}\times n \times\mathbb{E}[X]
$$
$$
\therefore  \mathbb{E}[\bar{X}]=\mathbb{E}[X]
$$
$$
\boxed{\therefore \mathbb{E}[\hat{\mu}_{MLE}]=\mu}
$$
$$
\text{Bias = }(\mathbb{E}[\hat{\mu}_{MLE}]-\mu)^{2}=(\mu-\mu)^{2}=0
$$
$$
\boxed{\text{Therefore, the estimator of }\hat{\mu}_{MLE} \text{ is unbiased}}
$$
## d
$$
\hat{\mu}_{MLE}=\bar{X}=\frac{\sum_{i=1}^nx_{i}}{n}
$$
$$
\text{Var}\left[ \frac{1}{n}\sum_{i=1}^nx_{i} \right]=\frac{1}{n^{2}}\text{Var}\left[ \sum_{i=1}^nx_{i} \right]=\frac{1}{n^{2}}\sum_{i=1}^n\text{Var}[X_{i}]
$$
$$
\text{Since the }X_{i} \text{ are IID R.V, they share the same variance}
$$
$$
= \frac{1}{n^{2}}\times n\times \text{Var}[X]=\frac{\text{Var}[X]}{n}
$$
$$
\boxed{\therefore \text{Var}[\hat{\mu}_{MLE}]=\frac{\text{Var}[X]}{n}=\frac{\sigma^{2}}{n}}
$$
$$
\lim_{ n \to \infty } \frac{\sigma^{2}}{n}=0
$$
$$
\boxed{\therefore \text{The estimator } \hat{\mu}_{MLE} \text{ is consistent}}
$$
## e
$$
L(\mu,\sigma^{2}|x_{1},\dots,x_{n})=\Pi_{i=1}^nf(x_{i}|\mu,\sigma^{2})
$$
$$
l(\mu,\sigma^{2}|x_{1},\dots,x_{n})=\sum_{i=1}^n\ln (f(x_{i}|\mu,\sigma^{2}))=\sum_{i=1}^n\ln\left[ \frac{1}{\sqrt{ 2\sigma^{2} }}e^{-\frac{(x-\mu)^{2}}{2\sigma^{2}}} \right]
$$
$$
=\frac{n}{2}\ln(2\sigma^{2})-\frac{1}{2\sigma^{2}}\sum_{i=1}^n(x_{i}-\mu)^{2}
$$
$$
\hat{\sigma^{2}}_{MLE}=\frac{{\partial l}}{d\sigma^{2}}=\frac{n}{4\sigma^{2}}+\frac{1}{{2\sigma^{2}}^{2}}\sum_{i=1}^n(x_{i}-\mu)^{2}=0
$$
$$
\hat{\sigma^{2}}_{MLE}=\frac{\sum_{i=1}^n(x_{i}-\mu)^{2}}{n}
$$
$$
\text{Using the fact that }\hat{\mu}_{MLE}=\bar{X}
$$
$$
\boxed{\hat{\sigma}_{MLE}=\sqrt{ \frac{1}{n} \sum_{i=1}^n(x_{i}-\bar{X})^{2}}}
$$
-  - - 
# 2
## a 
$$
\vec{x}=\begin{bmatrix}
x_{1} \\
\vdots \\
x_{n}
\end{bmatrix}
$$
$$
f(\vec{x})=\frac{1}{\sqrt{ {2\pi}^{d}\sum }}e^{-\frac{1}{2}(x-\theta)^{T}\sum^{-1}(x_{i}-\theta)}
$$
$$
L\left( \theta,\sum|x_{1},\dots,x_{n} \right)=\Pi_{i=1}^n\frac{1}{\sqrt{ {2\pi}^{d}\sum }}e^{-\frac{1}{2}(x-\theta)^{T}\sum^{-1}(x_{i}-\theta)}
$$
$$
=\boxed{\frac{1}{(2\pi)^{\frac{dn}{2}}|\sum|^{\frac{n}{2}}}e^{-\frac{1}{2}\sum_{i=1}^n(x_{i}-\theta)^{T}\sum^{-1}(x_{i}-\theta)}}
$$
## b
$$
l\left( \theta,\sum \right)=-\frac{dn}{2}\ln 2\pi-\frac{n}{2}\ln|\sum|-\frac{1}{2} \sum_{i=1}^n(x_{i}-\theta)^{T} \frac{1}{\sum}(x_{i}-\theta)
$$
$$
\frac{\partial l}{d\theta}=-\frac{1}{2}\sum_{i=1}^n(x_{i}-\hat{\theta}_{MLE})^{T} \frac{1}{\sum}=0
$$
$$
=\sum_{i=1}^nx_{i}=\hat{\theta}_{MLE} \times n
$$
$$
\boxed{\hat{\theta}_{MLE}=\frac{\sum_{i=1}^nx_{i}}{n}=\bar{X}}
$$
## c
$$
\mathbb{E}[\hat{\theta}_{MLE}]=\mathbb{E}[\bar{X}]=\mathbb{E}[X]\text{, using the fact from the previous question}
$$
$$
\boxed{\therefore \mathbb{E}[\hat{\theta}_{MLE}]=\theta \text{, and therefore is unbiased}}
$$
## d 
$$
\text{Var}[\hat{\theta}_{MLE}]=\text{Var}[\bar{X}]=\frac{1}{n}\text{Var}[X]\text{, using the fact from the previous question}
$$
$$
\frac{1}{n}\text{Var}[X]=\frac{1}{n}\sum
$$
$$
\lim_{ n \to \infty } \frac{1}{n}\sum=0
$$
$$
\boxed{\therefore \text{ consistent}}
$$
## e
$$
l\left( \theta,\sum \right)=-\frac{dn}{2}\ln 2\pi-\frac{n}{2}\ln|\sum|-\frac{1}{2} \sum_{i=1}^n(x_{i}-\theta)^{T} \frac{1}{\sum}(x_{i}-\theta)
$$
$$
\frac{{\partial l}}{\partial \sum}=-\frac{n}{2\sum}+\frac{1}{2{\sum}^{2}} \sum_{i=1}^n(x_{i}-\theta)^T(x_{i}-\theta)
$$
$$
\text{Since }\hat{\theta}_{MLE}=\bar{X}
$$
$$
\boxed{\hat{\sum}_{MLE}=\frac{1}{n}\sum_{i=1}^n(x_{i}-\bar{X})^T(x_{i}-\bar{X})}
$$
- - - 
# 3
## a
$$
\boxed{x_{i}\sim  \text{Exp}(\theta)=f_{x}(x)=\theta e^{-\theta x}; \text{ x} \in[0, \infty]}
$$
## b
$$
\boxed{\text{The time until the next red car is spotted on the highway by an observer}}
$$
## c
$$
L(\theta|x_{1},\dots,x_{n})=\Pi_{i=1}^n\theta e^{-\theta x_{i}}=\theta^{n}e^{-\theta \sum_{i=1}^nx_{i}}
$$
$$
l(\theta|x_{1},\dots,x_{n})=n \ln \theta-\theta \sum_{i=1}^nx_{i}
$$
$$
\frac{{\partial l}}{\partial \theta}=\frac{n}{\hat{\theta}_{MLE}}-\sum_{i=1}^nx_{i}=0
$$
$$
\boxed{\hat{\theta}_{MLE}=\frac{n}{\sum_{i=1}^nx_{i}}=\frac{1}{\bar{X}}}
$$
## d
$$
\boxed{\text{To compute }\hat{\theta }_{MLE}\text{ you can find the mean of the sample data and then take the reciprocal}}
$$
## e
$$
\text{for n datum: } \hat{\theta}_{MLE, n}=\frac{n}{\sum_{i=1}^nx_{i}}
$$
$$
\text{for n+1 datum: }\hat{\theta}_{MLE, n+1}=\frac{{n+1}}{\sum_{i=1}^{n+1}x_{i}}=\frac{{n+1}}{x_{n+1}+\sum_{i=1}^n x_{i}}
$$
$$
\boxed{\text{we can rewrite the above expression to } \frac{{n+1}}{x_{n+1}+\frac{n}{\hat{\theta}_{MLE, n}}}\text{ which is the rule for updating the MLE estimator}}
$$
- - - 
# 4
## a
$$
X \sim \text{Unif}(a, b)
$$
$$
f_{x}(x)=\frac{1}{b-a}\text{, where x} \in[a,b]
$$
$$
\text{Let }I_{[a, b]}(x)=\begin{cases}1; \text{ }x \in[a, b] \\
0; \text{ otherwise}
\end{cases}\text{ as the indicator function}
$$
$$
\text{then }f_{x}(x)=\frac{1}{b-a}\times I_{(a,b)}(x)
$$
$$
L(a, b|x_{1},\dots,x_{n})=\Pi_{i=1}^n \frac{1}{b-a}\times I_{[a,b]}(x)
$$
$$
=\left( \frac{1}{b-a} \right)^n\Pi_{i=1}^nI_{[a,b]}(x);\text{ }-\infty <a\leq x_{i}\leq b<\infty \rightarrow I=1, \text{otherwise 0}
$$
$$
\text{To maximize the estimator, we want }x_{i}\text{ to be between the bounds}
$$
$$
\therefore \hat{a}_{MLE}=\text{min }x_{i}, \hat{b}_{MLE}=\text{max }x_{i}
$$
$$
\vec{x}=[1.2,2.1, 1.2, 10.5, 5
]
$$
$$
\boxed{\hat{a}_{MLE}=1.2, \hat{b}_{MLE}=10.5}
$$
## b
$$
\text{If there are n data points drawn from the Uniform Distribution, }
$$
$$
\boxed{\therefore \hat{a}_{MLE}=\text{min }x_{i}, \hat{b}_{MLE}=\text{max }x_{i}, \text{of the dataset}}
$$
- - - 
# 5
## a
$$
\text{Given that the equation of the line for each point is }y_{i}=ax_{i}+b+\xi_{i}
$$
$$
Y_{i}\sim N(ax_{i}+b, \sigma^{2})
$$
$$
\boxed{f(y)= \frac{1}{\sqrt{ 2\pi \sigma^{2} }}e^{-1/2\times\frac{(y-(ax+b))^{2}}{\sigma^{2}}}}
$$
## b
$$
L((x_{i},y_{i})|a,b,x_{i},\sigma^{2})=\Pi_{i=1}^3 \frac{1}{\sqrt{ 2\pi \sigma^{2} }}e^{-1/2\times\frac{(y_{i}-(ax_{i}+b))^{2}}{\sigma^{2}}}
$$
$$
=(2\pi \sigma^{2})^{-\frac{3}{2}}e^{-\frac{1}{2\sigma^{2}}\sum_{i=1}^3(y_{i}-(ax_{i}+b))^{2}}
$$
$$
\text{Substituting in the three points, }(1,8),(3,2),(5,1),\text{ we get:}
$$
$$
\boxed{L((1,8),(3,2),(5,1)|a,b,x_{i},\sigma^{2})=(2\pi \sigma^{2})^{-\frac{3}{2}}e^{-\frac{1}{2\sigma^{2}}[(8-(a+b))^{2}+(2-(3a+b))^{2}+(1-(5a+b))^{2}]}}
$$
$$
\text{Substituting the points for the log-likelihood:}
$$
$$
l(a,b,x_{i},\sigma^{2}|(x_{1},y_{1}),(x_{2},y_{2}),(x_{3},y_{3}))=-\frac{3}{2}\ln (2\pi \sigma^{2})-\frac{1}{2\sigma^{2}}\sum_{i=1}^3(y_{i}-(ax_{i}+b))^{2}
$$
$$
\boxed{l((1,8),(3,2),(5,1)|a,b,x_{i},\sigma^{2})=(2\pi \sigma^{2})^{-\frac{3}{2}}-\frac{1}{2\sigma^{2}}[(8-(a+b))^{2}+(2-(3a+b))^{2}+(1-(5a+b))^{2}]}
$$
## c
 $$
\frac{{\partial l}}{\partial a}=2(8-(a+b))(-1)+2(2-(3a+b))(-3)+2(1-(5a+b))(-5)
$$
$$
\text{Setting this equal to 0, we get }
$$
$$
70\hat{a}_{MLE}=38-18b \rightarrow \hat{a}_{_{MLE}}=\frac{{19-9b}}{35}
$$
$$
\frac{{\partial l}}{\partial b}=2(8-(a+b))(-1)+2(2-(3a+b))(-1)+2(1-(5a+b))(-1)
$$
$$
\text{Setting this equal to 0, we get}
$$

$$
6\hat{b}_{MLE}=22-18a \rightarrow \hat{b}_{MLE}=\frac{{11-9a}}{3}
$$
$$
\text{Solving this system of equations}
$$
$$
\hat{a}_{MLE}=\frac{{19-9\left( \frac{{11-9\hat{a}_{MLE}}}{3} \right)}}{35}=\frac{{-14+27\hat{a}_{MLE}}}{35}
$$
$$
\boxed{\hat{a}_{MLE}=-\frac{7}{4}}
$$
$$
\hat{b}_{MLE}=\frac{{11-9\left( \frac{{19-9\hat{b}_{MLE}}}{35} \right)}}{3}=\frac{{11+\frac{63}{4}}}{3}
$$
$$
\boxed{\hat{b}_{MLE}=\frac{107}{12}}
$$
## d
$$
L(a, b, \sigma|x_{1},\dots,x_{n})=\Pi_{i=1}^n \frac{1}{\sqrt{ 2\pi \sigma^{2} }}e^{-\frac{1}{2\sigma^{2}}(y_{i}-(ax_{i}+b))^{2}}
$$
$$
\boxed{l(a, b, \sigma|x_{1},\dots,x_{n})=- \frac{n}{2}\ln (2\pi \sigma^{2})-\frac{1}{2}\sum_{i=1}^n[y_{i}-(ax_{i}+b)]^{2}}
$$
## e
![[Pasted image 20250411211452.png]]











