# stat4ds-homework-1-solved
**TO GET THIS SOLUTION VISIT:** [Stat4DS Homework 1 Solved](https://www.ankitcodinghub.com/product/stat4ds-homework-1-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;93915&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;Stat4DS Homework 1 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (1 vote)    </div>
    </div>
<div class="page" title="Page 1">
<div class="layoutArea">
<div class="column">
Exercise 1: Randomize this. . .

1. Background: Random Projections for Data Sketching (more info)

Imagine a network switch which must process dozens of gigabytes per second, and may only have a few kilobytes or megabytes of fast memory available. Imagine also that, from the huge amount of traffic passing by the switch, we wish to compute basic stats like the number of distinct traffic flows (source/destination pairs) traversing the switch, the variability of the packet sizes, etc. Lots of data to process, not a lot of space: the perfect recipe for an epic infrastructural failure.

Streaming model of computation to the rescue! The model aims to capture scenarios in which a computing device with a very limited amount of storage must process a huge amount of data, and must compute some aggregate summary statistics about that data.

Let us formalize this model using a frequency vector x.

The raw stream is a growing sequence of indices Dn = (i1,i2,…,ik,…,in), where each ik ∈ {data-alphabet} = {1,…,d}, where d, the size of the “data-alphabet”, may be very large. For our developments, think d way larger than n, possibly infinite! At an abstract level, the goal is to initialize, store and update sequentially1 the frequency vector x = [x1, . . . , xd]T with

xj = {number of indices ik in Dn equal to j} = cardinality􏰮{k : ik = j}􏰯, j ∈ {1,…,d},

and then to output some properties of x at the end of the stream, such as its length, or the number of non-zero entries, etc.

</div>
</div>
<div class="layoutArea">
<div class="column">
If the algorithm were to maintain x explicitly, it could initialize x(0) ← [0, 0, . . . , 0]T, then, at each step k, it receives the index ik and just increments x(k−1) by 1 to get the updated frequency vector x(k). Notice that, in terms of notation, x ≡ x(n).

</div>
</div>
<div class="layoutArea">
<div class="column">
ik

Given this sequential, explicit representation of x at the end of the stream, one can easily compute the desired properties.

</div>
</div>
<div class="layoutArea">
<div class="column">
1That is, on-the-fly, just by “looking” at each ik as they appear without storing the raw data in Dn at any step. 1

</div>
</div>
</div>
<div class="page" title="Page 2">
<div class="layoutArea">
<div class="column">
So far the problem is trivial. The algorithm can explicitly store the frequency vector x, or even the entire sequence (i1 , . . . , in ), and compute any desired function of those objects. What makes the model interesting are the following desiderata:

This list rules out trivial solutions. Remarkably, numerous interesting summary statistics can still be computed under this restrictive observational model if we allow for randomized algorithms that output approximate answers.

2. The Algorithm: “length” matters. . .

Here we will focus on a simple randomized algorithm to evaluate the length (a.k.a. l2 norm) of x, namely ∥x∥ = 􏱉􏰶di=1 x2i .

The idea of the algorithm is very simple: instead of storing x explicitly, we will store a dimensionality reduced form of x. Dimensionality reduction is the process of mapping a high dimensional dataset to a lower dimensional space, while preserving much of the important structure – in this exercise, its length ∥x∥. In statistics and machine learning, this often refers to the process of finding a few directions in which a high dimensional random vector has maximimum variance. Principal component analysis is a standard technique but with a different “preservation target”.

Now, how do we get this compressed version of x? Simple: random projection! Why? Because there’s a neat result known as Johnson-Lindenstrauss lemma which assures that, with high probability (w.r.t. the randomization), a well designed random projection will (almost) preserve pairwise distances and lengths between data points. Of course random projections are central in many other applications, and compressed sensing was one of the big, fascinating thing not too long ago.

Here for you the basic steps:

1. Let’s start by selecting a tuning parameter p, the “size” of the projection, with p &lt;&lt; n &lt;&lt; d.

2. Define L to be a (p × d) random (projection) matrix whose entries are drawn independently as N1(0, 1/p).

3. The algorithm will maintain only the p-dimensional vector y (after its obvious initialization y(0)), defined at step k as

y(k) =L·x(k).

At time step k, the algorithm receives the index ik = j with j ∈ {1, . . . , d}, so implicitly the jth coordinate of x(k−1)

increases by 1 to get x(k). The corresponding explicit change to obtain y(k) is to add the jth column of L to y(k−1).

So if we set p to a value of the order 1/ε2, then, at the end of the stream, ∥y∥ gives a (1 + ε) approximation of ∥x∥ with constant probability. Or, if we want y(k) to give an accurate estimate at each time steps, we can take p = Θ(log(n)/ε2). Remark: please notice the remarkable fact that p, the suggested dimension of the projection/embedding, ignores completely the (presumably huge or even infinite) alphabet size d!

3. The Exercise: Comment every line of code and result you get!

􏰺 Your job 􏰺

<ol>
<li>Show the validity of the update step (i.e., the one you need to code): increasing by 1 the jth coordinate of x(k−1)
corresponds to add the jth column of L to y(k−1).
</li>
<li>Use R to generate the matrix L many times (say M = 1000) and setup a suitable simulation study to double-check the JL-lemma. You must play around with different values of d, n, ε and p (just a few, well chosen values, will be enough). The raw stream Dn = (i1, . . . , in) can be fixed or randomized too, but notice that the probability appearing in Equation
(1) simply accounts for the uncertainty implied by the randomness of L – that’s why I stressed that you must generate “many times” L. . .
</li>
</ol>
3. The main and only object being updated by the algorithm is the vector y. This vector consumes p ∼ log(n)/ε2 words of space, so. . . have we achieved our goal? Explain.

</div>
</div>
<div class="section">
<div class="layoutArea">
<div class="column">
1. The algorithm should never explicitly store the whole data stream Dn = (i1 , . . . , in ).

2. The algorithm should never explicitly build and maintain the frequency vector x.

3. The algorithm only see one index ik per round…btw, that’s the very idea of a streaming algorithm! 4. The algorithm should use O(log(n)) words of space to process the entire stream Dn.

</div>
</div>
</div>
<div class="section">
<div class="layoutArea">
<div class="column">
The Johnson-Lindenstrauss lemma (JL) then says that, for every tolerance ε &gt; 0 we pick,

Pr 􏰴(1 − ε) · ∥x∥ 􏰼 ∥y∥ 􏰼 (1 + ε) · ∥x∥􏰵 􏰻 1 − e−ε2·p. (1)

</div>
</div>
</div>
<div class="layoutArea">
<div class="column">
2

</div>
</div>
</div>
<div class="page" title="Page 3">
<div class="layoutArea">
<div class="column">
Exercise 2: Faraway, So Close!

1. Background: Statistical Distances and Losses (more info)

Suppose that X is a random vector in Rm with distribution PX and Y is another random vector in Rm with distribution PY then, for p 􏰻 1, the p–Wasserstein distance based on the ground distance d is defined as

􏱅􏱈 􏱆1/p Wd,p(PX,PY ) ≡ Wd,p(X,Y ) = inf d(x,y)p dJ(x,y) ,

J Rm×Rm

where the infimum is over all joint distributions J having PX and PY as given marginals. . . sounds complicated, does it? Anyway, these optimal transport techniques are extremely useful and widespread nowdays with tons of “. . . truly marvelous Machine Learning applications, which this homework is too narrow to contain…’’.

Nevertheless, when m = 1, that is for univariate distributions, things simplify quite a bit and it can be shown that, by picking the L1 metric (i.e. the absolute distance) as ground distance, we obtain

0

F−1(·) are essentially their associated quantile functions. Y

2. The Learning Framework

</div>
</div>
<div class="layoutArea">
<div class="column">
􏱅􏱈 1 p 􏱆1/p 􏰽􏰽F−1(z)−F−1(z)􏰽􏰽 dz

</div>
</div>
<div class="layoutArea">
<div class="column">
WL1,p(PX,PY)=

where FX(·) and FY (·) are the cumulative distribution functions of PX and PY , respectively and, consequently, F−1(·) and

</div>
</div>
<div class="layoutArea">
<div class="column">
<ol>
<li>Think about FX (·) as the true population model and assume that X ∼ Beta(α, β) for some value of (α, β) that you will choose (read about this flexible parametric family with bounded support at page 54-56 of our Gallery).

Let f(·) denote the associated true density and F−1(·) its quantile function.</li>
<li>Think about FY (·) = FY (· ; θ) as an approximation to FX (·) that you need to tune/optimize with respect to the parameter vector θ in order to achieve some specific goal.

For this exercise we will consider a stepwise function (just like an histogram), whose density can be described as follow:

• Divide the inteval [0, 1], the support of f (·), into bins of length h: there are N ≈ 1/h bins. Denote the bins by {B1,…,BN}.

• The approximating density is then

f(x;θ) = 􏰷N πj 1(x ∈ Bj), 􏰸h

j=1

where θ = (h,π1,…,πN) and 1(x ∈ Bj) is the indicator function of the jth bin.
</li>
<li>Assume that we are working under perfect information, meaning that we can access/query the true model.</li>
</ol>
3. The Exercise: Comment every line of code and result you get!

􏰺 Your job 􏰺

1. For a fixed h, what kind of constrains we need to impose over the parameter vector (π1,…,πN) for f(x;θ) to be a legit

density?

</div>
</div>
<div class="layoutArea">
<div class="column">
􏰸 􏰸−1

Bj 􏰸

</div>
</div>
<div class="layoutArea">
<div class="column">
2. Implement f(x;θ) and its corresponding quantile function, say F (x;θ), in R

</div>
</div>
<div class="layoutArea">
<div class="column">
XY

</div>
<div class="column">
,

</div>
</div>
<div class="layoutArea">
<div class="column">
3. Pick a specific (α,β) pair and, for any h &gt; 0, fix πj = 􏱇 f(x)dx. Notice that now f(·;θ) depends on a single

</div>
</div>
<div class="layoutArea">
<div class="column">
tuning parameter, the binwidth h. For this reason, let’s simplify the notation and use fh(·) and F−1(·) to denote the h

approximant density and its quantile function respectively.

Let ε &gt; 0 be an approximation level you are targeting in terms of p = 1 Wasserstein distance, meaning that you’re looking for the largest binwidth h (i.e. the coarsest approximation) such that

</div>
</div>
<div class="layoutArea">
<div class="column">
􏰮 􏰯 􏱅􏱈1􏰽 −1 􏰽 􏱆 􏰸􏰸

</div>
</div>
<div class="layoutArea">
<div class="column">
WL1,1 f,fh = 􏰽􏰽F−1(z)−Fh (z)􏰽􏰽dz 􏰼ε 0

</div>
</div>
<div class="layoutArea">
<div class="column">
Use any (reasonable) technique you like, to study how h varies with ε (. . . and properly comment the results). 4. (Bonus). Repeat the previous point letting (π1, . . . , πN ) free to vary (quite harder!). Compare the results.

</div>
</div>
<div class="layoutArea">
<div class="column">
3

</div>
</div>
</div>
