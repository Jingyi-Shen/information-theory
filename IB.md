
+ Sufficient statistics
  - Cover and Thomas 1991
  - Definition
    1. Statistic: A statistic $T$ : $X$ → $T$ is a function of the data.
    2. Sufficient Statistic: for a model $\mathcal{P} = \lbrace \mathbb{P}_\theta : \theta \in \Omega \rbrace$, (has underlying parameter $\theta$), if for all $t$, the conditional distribution $X|T(x) = t$ does not depend on  $\theta$. Then, $T(X)=t$ is a Sufficient Statistic. 
        - Eg1: (Max of Uniform). Let $X_1, X_2, ..., X_n$ be i.i.d. according to uniform distribution $U(0, \theta)$. Then $T(x) = \max(X_1, ..., X_n)$ is sufficient. 
        - Intuition: given the maximum is fixed at $t$, then the remaining n−1 numbers are i.i.d random samples drawn from $U(0, t)$, $X|T(x) = t$ is independent of $\theta$, $T(x)$ is sufficient. 
        - Eg2: $T(x)=X$
        - Eg3: variable $Z$ is a sufficient statistic of $H$ for $Y$ , i.e. it contains the necessary information from $H$ to predict the class $Y$. 
          - we have: $I(H,Y)=I(H,Z)$, and $H(H|Y)=H(H|Z)$.
    3. minimal sufficient statistics: A sufficient statistic $T(X)$ is a MSS, for any other sufficient statistic $U(X)$, we can write $T(X)=g(U(X))$, i.e. $T(X)$ is a function of $U(X)$.
        - finest partition (size of $|U(X)|$ is no less than $|T(X)|$) --> a sufficient statistic that achieve the maximum data reduction.
        - $X$ --> $U(X)$ --> $T(X)=g(U(X))$ 
---
+ rate distortion theory
  - Let $T$ denote the discrete random variable which is a compressed representation of $X$. The mapping between $x$ and $t$ can be characterized by a conditional distribution $p(t|x)$, (induce a soft paartition of $X$). 
  - quality of compressed representation
  1. how compressed it is: the rate of code w.r.t. a channel transmitting between $X$ and $T$. We term the compression information: $I(T;X)$. Based on the joint distribution $p(x)p(t|x)$. 
      - Low values --> compact representations
        - in the extreme case, $T$ has just a single value, $I(T;X)=0$; 
      - high values --> redundant representations
        - if $T$ simply copies $X$, we have $I(T;X)=H(X)$, the upper bound of this term.
      - formal interpretation: the maxmial number of bits that can be reliably transmitted from $X$ to $T$.
      - $I(T;X)$ measures the compactness of new represenation $T$. 
        - aysmptotic equipartition property (AEP).
        - for each n-sequence of T syymbols there are $\approx 2^{nH(X|T)}$ possible equally likely $X$ (input) n-sequences. 
        - total number of possible $X$ is $\approx 2^{nH(X)}$
        - Need to ensure no two $X$ produce the same $T$ sequence. So the possible $X$ has to bee divided into subsets of size $\approx 2^{nH(X|T)}$, each subset corresponds to different $T$ sequence. Total # of clusters is upper bounded by $2^{n(H(X)-H(X|T))} = 2^{nI(T;X)}$. 
        - we can send at most $\approx 2^{nI(T;X)}$ distinguishable sequences of length $n$ from $X$ to $T$. 
        - ![image](url)

  2. additional constraints in rate distortion theory: define a distortion measure: distance between $X$ and $T$. 
      - smaller distortion: a better representation
      - the partition of $X$ induced by $p(t|x)$ has the expected distortion:
      $$\left\langle d(x,t)\right\rangle_{p(x)p(t|x)}=\sum_{x,t}p(x)p(t|x)d(x,t)$$
  
  - the rate-distortion function $R(D)$
    - the infimum (最大下界；定义为小于等于在S中的所有数的最大实数) of all rate $R$ under a given constraint on the average distortion $D$. 
    $$R(D)\equiv \min_{\{p(t|x):\left\langle d(x,t)\right\rangle\leq D\}}I(T;X)$$
    - $R(D)$ is the minimal achievable compression-information, where the minimization is over all the normalized $p(t|x)$ for which the distortion constraint is satisfied. 
    - higher $D$ values (more relaxed constraints) imply stronger compression level (lower $I(T;X)$).
    - $R(D)$ seperates the distortion-compression plane into achievable annd non-achievable regions. 
    - solve by introducing a Lagrange multiplier $\beta$, then minimize: 
    $$\mathcal{F}[p(t|x)]=I(T;X)+\beta \left\langle d(x,t)\right\rangle_{p(x)p(t|x)}$$ under the normalization constraints $\sum_tp(t|x)=1$,$\forall x \in X$
---
+ IB variational principle (an extension of rate distortion theoryy)

+ optimal (formal) solution to the IB principle

---