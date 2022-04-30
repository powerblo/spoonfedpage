---
share: true
---
#definition
# D : Vector Space
A **vector space** is a set $V$ and a [[r-scalar-field|scalar field]] $\mathbb{F}$ with two [[r-operations|operations]], *addition* (+) and *scalar multiplication* ($\cdot$) that the following properties hold;
- **Commutativity** : (For all $u,v\in V$) $u+v=v+u$
- **Associativity I** : (For all $u,v,w\in V$) $(u+v)+w=u+(v+w)$
- **Associativity II** : (For all $v\in V, a,b\in\mathbb{F}$) $(ab)\cdot v=a\cdot(b\cdot v)$
- **Additive Identity** : There exists an element $0_V\in V$ such that (for all $v\in V$) $v+0_V=v$. ^31a50e
- **Additive Inverse** : For all $v\in V$, there exists an element $(-v)\in V$ such that $v+(-v)=0_V$.
- **Multiplicative Identity** : For the multiplicative identity $1_\mathbb{F}\in\mathbb{F}$, (for all $v\in V$) $1_F\cdot v=v$
- **Distributivity I** : (For all $a\in\mathbb{F}, u,v\in V$) $a\cdot(u+v)=a\cdot u+a\cdot v$
- **Distributivity II** : (For all $a,b\in\mathbb{F}, v\in V$) $(a+b)\cdot v=a\cdot v+b\cdot v$

# Remarks
- A vector is defined to be an element of a vector space; which means even when we refer to an element $v\in V$, we implicitly acknoweldge the two operations.
- Scalar multiplication and multiplication in the field are written with different notation in this definition for clarify; it is convention to write scalar multiplication without $\cdot$.
- The vector space consisting solely of the additional identity $\{0\}$ is referred to as the trivial vector space. ^49ab4e
- The field $\mathbb{F}$ itself can be considered a vector space over $\mathbb{F}$.
# Related
- Algebraic Structure
- Algebra
- Module