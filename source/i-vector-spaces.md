---
share: true
---
#notes
[[0-primer|<- Primer]]    [[ii-linear-maps|Linear Maps ->]]
## Primer
As discussed in the heading primer, linear algebra is a field that studies "linear systems". They're any system (equations, functions, algorithms etc.) that *linearly* take take an input to an output, in the fashion of the linear function $y=mx+b$.
In engineering courses, clarifying what this means using hand-on demonstrations; or perhaps first discussing where these systems appear and how to solve them makes sense. A math oriented course delays this for a bit however, by digressing to really dig into the question "but what *is* a linear system"?
We will use the language of set theory; we claim that a "linear system" is "*some linear* function between *some* sets". The question boils down to specifying what *some linear* functions and *some* sets we're precisely talking about.

To define this *linearity*, it's helpful to take another look at the linear function $z=ax+by$. What is this function really doing? It "scales" the input $x$ by $a$, $y$ by $b$, then adds them together. This means that for the *some* sets we're dealing with, at the very least we want to be able to *define the operations* of *scaling* and *addition*. An important distinction is to make sure we don't mistake scaling for multiplication; $y=x*x=x^2$ for example isn't linear.
What happens when we define such operations upon a set is that we obtain a **vector space**, and call its elements **vectors**. The naming is related to the vector from physics, anything with a direction and magnitude; it happens that you can add two vectors together and scale them, so the set of all (physical) vectors forms a (mathematical) vector space.
<br/ >

## Vector Spaces
Before discussing the formal definition of vectors in linear algebra, here's a quick recap on the intuitive idea of what a vector is.
- **Resource** : The Euclidean vector in Euclidean space is the archetype of vectors, and many of its properties are generalised into abstract ones. Euclidean vectors are frequently described as "an object with magnitude and direction".
- **Resource** : This [video](https://www.youtube.com/watch?v=fNk_zzaMoSs&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=1) by 3b1b gives two concrete examples and links them to the abstract 'mathematician's' idea of a vector.
- **Resource** : Many instances of data are represented by vectors, as computers are designed to solve problems with linear algebra. In neural networks, input data and output data are considered vectors.
- *Optional* : Vectors have their historical roots in the 'physicist's' idea of a vector, summarised by the aphorism "vectors transform like a vector"; highlighting the intuitive geometric properties of a vector (in relation to a "covector"). Mathematical physics books like Section 1.2 of [[#^533296|Arfken and Weber]] give a rough idea on what this means, but here are some [blogposts](https://www.physicsforums.com/threads/what-does-it-mean-transforms-like-a-vector.699407/post-4431505) and [PSE posts](https://physics.stackexchange.com/questions/155878/what-does-it-mean-to-transform-as-a-scalar-or-vector)) that delve further into this for food for thought.
- *Optional* : In differential geometry, vectors are no longer considered as related to a vector space; instead they're defined through "differential operators". There's a great [article](https://yk-liu.github.io/2018/Vectors-and-One-Forms-on-Manifold/) and [blogpost](https://www.physicsforums.com/threads/tangent-space-in-manifolds-how-do-we-exactly-define.685722/post-4348331) on the topic, and Ch. 12, 14, 15 of [[#^4dff5c|The Road to Reality]] gives a nice introduction to the topic.
<br />

In linear algebra, vectors are *defined* to be an element of a **vector space**.
- **Definition** : [[d-vector-space#D Vector Space|Vector Space]], with [[d-vector-space#Remarks|remarks]]
<br />

A majority of problems in this section consists of either confirming if a given set, scalar and operations *forms a vector space*, or proving if *certain properties* hold in all vector spaces.
- **Statement** : [[s-properties-of-vector-spaces#Summary|Properties of Vector Spaces]], with [[s-properties-of-vector-spaces#Remarks|remarks]]
<br />

The abstract nature of the definition gives several non-intuitive examples of vector spaces, which makes linear algebra greatly applicable.

[[1-matrix-notation|Matrices]] and vectors in Euclidean space are one of the most extensively used examples of vector spaces and vectors. Some notation conventions and definitions are worth mentioning in a linear algebra context. 
- **Resource** : Column vectors are 
- **Resource** : [Einstein notation](https://aditya-sengupta.github.io/expository/einstein.pdf).
<br />

**PSET I**

[[pset-i|PSET Link]]

## Linear Combination and Bases
A very useful concept that exists in Euclidean space is the "coordinate axis". This allows us to easily assign any point on a map to a set of coordinates and vice versa, which is very advantageous in abstract vector spaces where vectors can be rather fickle to describe otherwise. This also hints at simplifying "coordinate transformations"; instead of rotating the entire space, we can obtain the same result by simply rotating the coordinate axes.

To formalise "coordinate axes", we start off with the easier direction, going from a set of coordinates to a point. Given any *collection of vectors*, a **linear combination** maps a *set of coordinates* to a *specific vector*.
- **Definition** : [[d-linear-combination#D Linear Combination|Linear combination]], with [[d-linear-combination#Remarks|remarks]]
- **Resource** : This [video](https://www.youtube.com/watch?v=k7RM-ot2NWY&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=2) by 3b1b gives a visual representation on what this means in a Euclidean space context. 
<br />

It's quite clear that not any collection will behave like *coordinate axes*; two reasonable conditions we have are that *every point* in space can be expressed as a linear combination, and that this expression is *unique*. If either fail, mapping a point to a set of coordinates would be impossible. 
In this special case that both hold, we call this collection a **basis** of the vector space.
- **Definition** : Basis
- **Resource** : An [article](https://mikebeneschan.medium.com/how-to-understand-basis-linear-algebra-27a3bc759ae9) that explains bases with an analogy about colour.
<br />

The questions we can ask related to bases are the following;
- Given a collection of vectors, how can we confirm if it's a basis of the vector space?
- What happens to a generating/linearly independent collection of vectors/basis when we add/remove vectors?
- Given a vector space, can we guarantee it has a basis? Is there a systematic method to construct one?
- Can we find a property that all bases of a vector space share?
<br />

### **Generating and Linearly Independent Collections**
Given that we've already defined what a basis is, you could apply it directly to check whether a collection is a basis of the vector space or not. A cleaner and more concise way however, is to consider the "two reasonable conditions" separately; for any collection, if *every point* in the space can be expressed as a linear combination we say it's **generating**, and if every possible expression is *unique* we say it's **linearly independent**.
- **Definition** : Generating Collection
- **Definition** : Linearly Independent Collection
- **Statement** : Equivalent Expressions of Generating and Linearly Independent
<br />

From this, we can conclude a collection of vectors is a *basis if and only if it's generating and linearly independent*.
- **Statement** : Basis Iff Generating and Linearly Independent
<br />

A useful notion to describe the generating property is **span**, which denotes the set of all vectors that *can* be expressed as a linear combination of a collection of vectors. If the span of a collection equals the entire space, it generates the space.
- **Definition** : Span
<br />

Note that while the generating condition explicitly depends on whether the span of the collection equals the *entire* space or not (thus being a *relative* property), linearly independent collections are linearly independent regardless of whatever space they're embedded in (as long as the space actually does contain the collection).
- Embedded spaces
<br />

### **Adding and Removing Vectors to Collections**
Now we are prepared to answer the second question; what happens when we add or remove vectors to a collection of vectors? 
Let us begin by defining an important class of vector spaces; any vector space that can be generated by some finite collection is finite dimensional. 
- **Definition** : [[d-findim-vs#D Finite Dimensional Vector Space|Finite Dimensional]], with [[d-findim-vs#Remark|remarks]]
<br />

We continue by stating a few "obvious" statements; a generating collection upon *adding more vectors is still generating*, and a linearly independent collection upon *removing vectors is still linearly independent*.
- **Statement** : Adding and Removing Vectors to Collections
<br />

Then we state an important lemma that in a linearly dependent collection, there exists an element that can be expressed as a linear combination of the rest, and that removing this element from the collection doesn't change its span. This is the crux of manipulating collections of vectors.
- **Statement** : Linearly Dependent can be Reduced to Linearly Dependent
<br />

The next result is rather surprising; any finite generating collection of vectors can be reduced to a basis. We use exhaustion to cut down the collection until it's linearly independent while keeping its generating property.
- **Statement** : Generating can be Reduced to Basis
<br />

This result implies something even stronger; for any *finite-dimensional* vector space, we can guarantee the *existence of a finite basis*. We simply combine the assumption that the vector space is generated by some finite collection, and the statement above.
- **Statement** : Every Finite Dimensional has a Basis
- *Optional* : What about infinite dimensional spaces? It turns out that there's a [[1-basis-arb-vs|theorem]] that guarantees the existence of a basis for arbitrary vector spaces; the proof involves starkly different methods however, and in many cases (such as the vector space $\mathbb{R}$ over $\mathbb{Q}$) explicitly finding the basis is impossible.
- *Optional* : 
<br />

Similarly, for *finite-dimensional* vector spaces any finite linearly independent collection can be *extended to a basis*. We append to the linearly independent collection a basis of this vector space so it is generating, and use the same lemma as above to remove elements until it becomes a basis.
- **Statement** : Linearly Independent can be Extended to Basis
<br />

To summarise, we have answered the third question; given a finite generating collection of a vector space, we have guaranteed the existence of a basis, and also a method of obtaining it via reducing it to become linearly independent.
<br />

### **Dimension**
The previous section should've hinted to you that length is quite an important property of collections; perhaps even that all bases have the same length. This is a tempting argument to make; in Euclidean space, it makes sense that 2D spaces have two coordinate axes, 3D spaces have three, so on and so forth. It so happens that this is true for finite-dimensional vector spaces, and can even be obtained using the results from the previous section.
- **Statement** : [[s-bases-equal-length#S Bases Have Equal Length|Bases have Equal Length I]]
<br />

A more elegant method is available however; first we state another important lemma that in a finite-dimensional vector space, that any linearly independent collection is shorter or equal in size compared to generating collections.
- **Statement** : Linearly Independent Shorter or Equal than Generating
<br />

Finally, observe that given two bases we can use the inequality above twice to conclude their lengths are equal. 
- **Statement** : [[s-bases-equal-length|Bases have Equal Length II]]
<br />

Because this "length of bases" is no longer dependent on which basis we choose, it is rightfully a property of a finite-dimensional vector space itself, which we call the **dimension** of this vector space.
- **Definition** : [[d-dimension#D Dimension|Dimension]], with [[d-dimension#Remarks|remarks]]
<br />

Dimensions greatly reduce the amount of effort we need to put in say, determining whether a collection is a basis of a vector space or not; the length comparison lemma between linearly independent and generating collections does as well.
We can also prove interesting results about dimensions.
- **Statement** : Linearly Independent of Right Length is Basis
- **Statement** : Generating of Right Length is Basis
<br />

## Subspaces
There's generally one vector space associated with each interpretation of what a vector is. You might have noticed however, that some spaces are subsets of others; this prompts us to ask questions like "can a vector space be reduced/extended to a new vector space?" or "can we check if a subset is a vector space?" Subspaces allow us to ask these questions in a more formal manner.

A **subspace** is a vector space "contained within another", and implicitly shares the operations and scalar field. 
- **Definition** : Subspace
<br />

Because the actual operations are not changed, only a few considerations need to be made to ensure a subset is a subspace.
This is where the condition of *closure* becomes relevant, as it is conceptually possible to have two elements from a subset that map to an element not in that subset (but still in the larger initial space).
- **Statement** : Subspace Test
<br />

Subspaces have a natural connection with the span of a collection of vectors. If the collection were to be linearly independent, then the collection would be a basis of the subspace it generates.
- **Statement** : Span of Collection is Subspace
<br />

### **Direct Sums**
**Direct sums**, are a powerful tool to apply subspaces; a space is a direct sum of two subspaces if every element can be uniquely represented by a sum of an element from each subspace.  A direct sum can be interpreted as "extending a subspace into another dimension", like the direct sum between two subspaces of $\mathbb{R}^3$, $\mathbb{R}^2\oplus\mathbb{R}$.
- **Definition** : [[d-direct-sum|Direct Sum]]
- **Statement** : Direct Sum of Subspaces is Subspace
- **Statement** : Direct Sum Implies Unique Sum Representation
<br />

We can construct new subspaces through direct sums of subspaces, but the surprising fact is that given a subspace, we can decompose the vector space into a direct sum involving this subspace. We call the "remainder" the **complementary subspace.** This decomposition is extremely useful, and as in this [article](https://brilliant.org/wiki/subspace/), the idea of subspaces is prevalent across several areas of math.
- **Statement** : Decomposition into Direct Sum (Existence of Complementary Subspace)
<br />

Finally, there are equations involving the dimension of the sum of subspaces, which should remind you of the cardinality of the union of sets. 
- **Statement** : [[s-dimension-sum-subspace#Summary|Dimension of Sum of Subspaces]], with [[s-dimension-sum-subspace#Remarks|remarks]]
<br />

## PSET II

[[pset-ii|PSET Link]]

[[0-primer|<- Primer]]    [[ii-linear-maps|Linear Maps ->]]