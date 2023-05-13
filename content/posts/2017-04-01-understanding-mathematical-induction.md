+++
title = "Understanding Mathematical Induction"
author = ["bijay"]
date = 2017-04-01
draft = false
math = true
+++

Mathematical induction (aka Principle of Mathematical Induction) is a powerful technique in mathematics used to prove statements that are true for infinitely many [natural numbers](https://en.wikipedia.org/wiki/Natural_number).
Formally, the principle of mathematical induction is stated as:

<div class="mdframed">

For \\(n \in \mathbb{N}\\), let \\(P(n)\\) be a predicate. If

-   Base Case: \\(P(0)\\) is true, and
-   Inductive Step: Assuming \\(P(n)\\) is true show \\(P(n) \implies P(n + 1)\\) holds.

then

-   \\(P(m)\\) is true for all \\(m \in \mathbb{N}\\)

</div>

This is called a formal definition. Mathematicians try to make formal definition as simple as possible, but hidden behind this simplicity is a picture that
often gets missed. For instance, in the inductive step why do we assume the very thing that we are trying to prove \\(P(n)\\) to be true? Isn't that circular?


## Closer look at the definition {#closer-look-at-the-definition}

To gain a deeper understanding of mathematical induction we'll have to squeeze its formal definition word by word. Let's begin!

> For \\(n \in \mathbb{N}\\), let \\(P(n)\\) be a predicate. If

Notice that the definition only considers \\(n \in \mathbb{N}\\). So, sets that don't have a [bijection](https://en.wikipedia.org/wiki/Bijection) with \\(\mathbb{N}\\) are not considered.
For our purposes, we will not dive into the meaning of natural numbers.

> Base Case: \\(P(0)\\) is true, and

Also called the **Base Case**, at first look this seems self-explanatory. What is there other than the requirement that the predicate be true for \\(n = 0\\). But lurking behind is the question,
"Why does \\(0\\) exist?", "What if there is no element \\(0\\)?", "What gurantees the existence of \\(0\\)?"
Isn't making sense? Don't worry, we will cover it again in more detail. For now, let's just be aware that we have an unanswered
question. [Keeping in mind that we have ambiguity in our model of understanding, let's proceed further](https://www.azquotes.com/quote/556118).

> Inductive Step: Assuming \\(P(n)\\) is true show \\(P(n) \implies P(n + 1)\\) holds.

This mathematical expression with an arrow pointing from one predicate to another is called an implication. Implication, \\(A \implies B\\) (read as \\(A\\) implies \\(B\\)),
is itself a predicate which when translated to English means: If \\(A\\) is true then \\(B\\) is true. (Notice the **IF**)
It evaluates to true when whenever \\(A\\) is true \\(B\\) is also true or when \\(A\\) is false (in this case the truthfulness of \\(B\\) does not matter).

When talking about implications, mathematicians often use the words _holds_ to mean true and _does not hold_ to mean false.
This part of the definition requires the implication \\(P(n) \implies P(n+1)\\) to hold assuming \\(P(n)\\) is true.

This is the heart of the induction often called the inductive step. Notice that there is no claim of any sort stating the truthfulness of \\(P(n)\\) or \\(P(n+1)\\).
Except requring us to assume \\(P(n)\\) (also called the induction hypothesis) to be true (more on that later) all it is saying is that the implication should hold.

> then
>
> \\(P(m)\\) is true for all \\(m \in \mathbb{N}\\)

This is the final claim of the truthfulness of the predicate \\(P\\) for \\(m \in \mathbb{N}\\).
If the above steps are true, then the predicate \\(P\\) is true for all \\(m \in \mathbb{N}\\).
But why? Why is it enough to show that predicate \\(P\\) is true for all \\(m \in \mathbb{N}\\)?

Now we have more (but different) questions to answer.


## Why understand mathematical induction? {#why-understand-mathematical-induction}

Besides getting better at mathematics, it help us to better reason about algorithms that run our modern digitalized society.
Mathematical induction can be used to ensure that:

-   The system operating on a nuclear power plant does not go into the meltdown state
-   The medical equipments such as X-Ray doesn't harm the patient.
-   The auto-pilot does not crash the airplane.

So as you can see, it's quite important. Especially given that much of our society now runs on digitalized systems which by definition is discrete.


## Natural Numbers {#natural-numbers}

Mathematical induction can be thought of as an axiomatic property of the natural numbers.
To apply the principle of mathematical induction on a set \\(S\\), there must exist a bijection \\(f: \mathbb{N} \to S\\). In other words, set \\(S\\) must have the same
[cardinality](https://en.wikipedia.org/wiki/Cardinality) as the natural numbers; equivalently speaking \\(S\\) must be a [countable set](https://en.wikipedia.org/wiki/Countable_set).

The set of real numbers, \\(\mathbb{R}\\), is [uncountable](https://en.wikipedia.org/wiki/Uncountable_set). So, the mathematical induction can not be applied on it.
However, the sets \\(\mathbb{Z}\\) and \\(\mathbb{Q}\\) are countable, so the mathematical induction can be applied on it.

Why is mathematical induction use restricted to natural numbers only? Why not other sets that have a different cardinality than that of \\(\mathbb{N}\\)?
The answer is [Well-Ordering Principle](https://en.wikipedia.org/wiki/Well-ordering_principle). For our purposes, we will take the Well-Ordering Principle as an [axiom](https://en.wikipedia.org/wiki/Axiom).


## The Inductive Step {#the-inductive-step}

> Inductive Step: Assuming \\(P(n)\\) is true show \\(P(n) \implies P(n + 1)\\) holds.

The confusing part is assuming \\(P(n)\\) to be true. How can we assume the very thing we are trying to prove?
But the more you think about the implication \\(P(n) \implies P(n+1)\\), the more clear it becomes.
All that we are trying to show is that the implication holds. For the implication \\(P(n) \implies P(n+1)\\) to hold it must be one of the two cases:

-   \\(P(n)\\) is false.
-   Whenever \\(P(n)\\) is true, \\(P(n + 1)\\) is also true.

Now, let us examine the first case: \\(P(n)\\) is false. In this case the implication \\(P(n) \implies P(n+1)\\) **does** evaluate to true. But, this does not make sense
because we are _**claiming**_ something that we are trying to prove.

Second case: Whenever \\(P(n)\\) is true, \\(P(n + 1)\\) is also true. In this case to prove the implication we have to start with \\(P(n)\\) as true and then show that \\(P(n + 1)\\)
is true. Notice that nothing about truthfulness of \\(P(n)\\) is being claimed. We just start with \\(P(n)\\) as true soley for the purposes of showing the implication.


## Why does it work? {#why-does-it-work}

Only two questions remain now:

-   what gurantees the existence of the base case?
-   why does induction work?

There are many ways to answer this. The most trivial way is to assume the principle of mathematical induction as an axiom. In that case both of our questions are solved.
What remains is to prove other equivalent statements as a consequence of this axiom, one of which is the Well-Ordering Principle.

In this article I am going to do the opposite. We'll take the Well-Ordering Principle as an axiom to prove mathematical induction.


### Well-Ordering Principle {#well-ordering-principle}

> Every nonempty set of nonnegative integers has a smallest element.

Notice that the Well-Ordering Principle requires the set to be non-empty. This means that the Well-Ordering Principle is false for the empty set.
Also, it requires the set to only have nonnegative integers \\(n \in \mathbb{N}\\).


### Existence of the base case {#existence-of-the-base-case}

Consider \\(c = \min\\{\mathbb{S}\\}\\) (\\(S\\) is a set with bijection \\(f: \mathbb{N} \to S\\)).
The existence of \\(c\\) is guranteed by the Well-Ordering Principle.


### Proof of the mathematical induction {#proof-of-the-mathematical-induction}

That's right! We are going to prove the proof technique mathematical induction.

We are going to prove it by showing contradiction.

Let's redefine \\(P(n)\\) as  \\(S\_{n}=\\{ s\_{0}, \dots, s\_{n} \\}\\), and let \\(S = \cup\_{n \in \mathbb{N}} S\_{n}\\). Clearly, \\(S \sub \mathbb{N}\\).
Now let us rephrase the principle of mathematical induction with this new definition.

<div class="mdframed">

Let \\(S\\) be a subset of \\(\mathbb{N}\\) such that:

1.  \\(0 \in S\\),
2.  \\(k \in S \implies (k + 1) \in S\\)

    then

3.  \\(S = \mathbb{N}\\)

</div>

Now suppose (for contradiction) \\(S\\) exists with given properties in the principle of induction, but \\(S \neq \mathbb{N}\\).
Then \\(A = \mathbb{N} - S\\) is non-empty and has a least element by Well-Ordering Principle, call it \\(n\\).

Notice, \\(n > 0\\) because \\(0 \in S\\) so \\(0 \in A\\) by the definition of \\(A\\).
Consider \\(n - 1\\), it is not in \\(A\\) because \\(n\\) is the least element, so \\(n -1 \in S\\). But by the property B) of \\(S\\),
\\((n - 1) + 1 \in S\\) which implies \\(n \in S\\). A contradiction.

Therefore, \\(S = \mathbb{N}\\) which means that the principle of mathematical induction holds.
