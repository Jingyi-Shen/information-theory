+ Entropy: a lower bound on the minimal achievable code length for the random variable. 
---
+ Mutual information:
  - $$ I(X, Y) = \displaystyle\sum_{x}\sum_{y}p(x,y)\log{\frac{p(x,y)}{p(x)p(y)}}$$
  - $$ I(X, Y) = H(X)+H(Y)-H(X,Y) $$
    implies $I(X, Y)$ measures the average number of bits (log in base 2) that can be gained by a joint compression of X and Y versus independent compression that ignores their possible correlations. 
  - $$ I(X, Y)=H(X)-H(X|Y)=H(Y)-H(Y|X) $$
    mutual information is the reduction in the uncertainty of X due to the knowledge of Y
  - $$ I(X_1,..,X_n) = \displaystyle\sum_{x_1,...,x_n}p(x_1,...,x_n)\log{\frac{p(x_1,...,x_n)}{p(x_1)...p(x_n)}}$$
  - $$ I(X_1,..,X_n) = \displaystyle\sum_{i=1}^{n}H(X_i)-H(X_1,...,X_n)$$
  - $$ I(X_1,..,X_{n+1}) = I(X_1,..,X_n) + I(X_1,..,X_n;X_{n+1})$$
  - groupings of $\chi=\{x_1,x_2,...,x_{|\chi|}\}$ into groups $\Tau=\{t_1,t_2,...,t_{\Tau}\}$, $t_k \subset\chi$ (exhaustive and mutually exclusive groups), mutual information:
  $$I(X;Y)=I(p(x,y))=I(p(t,y))+\sum_tp(t)I(p(x,y|t))$$
---
+ Kullback-Leibler divergence (KLD):
  - $$ D_{KL}(P||Q) = -\sum_{i}P(i)\ln{\frac{Q(i)}{P(i)}} = \sum_{i}P(i)\ln{\frac{P(i)}{Q(i)}}$$
  - not a metric, not symmetric and not satisfy the  triangle inequality
  - coding inefficiency of assuming the distribution is $Q$ when the true distribution is $P$. 
    - If we have the true distribution $P$, we can construct a code for X with an average distribution length $H(X)=H(P)$. If we use the code for distribution $Q$, we need $H(P)+D_{KL}(P||Q)$ bits on average to describe the random variable.
  - $$I(X;Y) = D_{KL}(p(x,y)||p(x)p(y))$$
  - non-negative and is zero iff $P=Q$.
---
+ Jensen-Shannon (JS) divergence:
  - $$JS_\Pi(p_1,p_2)=\pi_1D_{KL}(p_1||\bar{p})+\pi_2D_{KL}(p_2||\bar{p})$$ 
    where $\Pi=\{\pi_1,\pi_2\}$, $0<\pi_1,\pi_2<1$, $\pi_1+\pi_2=1$ and $\bar{p}=\pi_1p_1+\pi_2p_2$
  - $$JS_\Pi(p_1,p_2)=H(\bar{p})-\pi_1H(p_1)-\pi_2H(p_2)$$
  - non-negative and is zero iff $p_1=p_2$.
  - not a metric, symmetric but not satisfy the triangle inequality. 
  - a bounded divergence measure (since ML is bounded); KL is not bounded. 
  - $$JS_\Pi(p_1,..,p_n)=H(\bar{p})-\sum_{i=1}^{n}\pi_iH(p_i)$$
    where $\Pi=\{\pi_1,..,\pi_n\}$, $0<\pi_i<1$, $\sum_{i=1}^{n}\pi_i=1$ and $\bar{p}=\sum_{i=1}^{n}\pi_ip_i$
  - if we take weights in $\Pi$ as the prior probabilities $p(x)$, the mutual information between X and Y is the JS divergence between all the conditional distributions $p(y|x)$. 
    + using $\pi_i=p(x_i)$, $p_i=p(y|x_i)$, $n=|\chi|$, and $p(y)=\sum_{x}p(x)p(y|x)=\sum_{i=1}^{n}\pi_ip_i=\bar{p}$
    + $$I(X;Y)=H(p(y))-\sum_{x}p(x)H(p(y|x))=H(\bar{p})-\sum_{i=1}^{n}\pi_iH(p_i)=JS_\Pi(p_1,...,p_n)$$
      - take words and docs as example, if all the conditional word distributions are the same (all docs have similiar relative word frequencies), JS is zero. There is no information between X and Y, knowing the words in the chosen doc is useless. 
      - On the other hand, if conditional word distributions are very different, JS is relatively high. In this case, more info between X and Y; knowing the words will help identify the doc. 
      - a bounded divergence measure
    
---
+ relevant versus irrelevant
  -  find partitions of the words; the distinctions inside each cluster of words are irrelevant, while among clusters are informative and relevant. (IB, page 14) $\Longrightarrow$ a 'good' partition, words with similiar conditional distributions over the doc are grouped together, corresponds to a high I(p(t,y)) value. 












   
