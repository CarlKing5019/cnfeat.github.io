---
layout: post
title: Peano axioms
date: 2017-05-21
categories: Math
tags: [Math, Notes]
description: A short note on Peano axioms.
---

陶哲轩实分析上有一句话
> 现代分析的一个非凡的成就就是，仅从皮亚诺公理加上集合论ZF公理出发，就可以构建数系，创造函数，并做我们通常所做的全部代数和微积分。


## 自然语言叙述


1. 0 是自然数.

2. 对于每一个自然数 $a$, 都有一个确定的后继 $a^{'}$ 也是自然数.

3. 对于每个自然数 $b$, $c$, $b=c$ 当且仅当 $b^{'}=c^{'}$.

4. 0 不是任何自然数的后继.

5. 任何关于自然数的命题, 如果证明了它对自然数 0 为真, 又假定它对自然数 $n$ 为真时可以证明它对 $n^{'}$ 也为真, 那么该命题对所有自然数为真.

## Mathematical definition

1. $0 \in \mathbb{N}$.
2. $n \in \mathbb{N} \Rightarrow n^{'} \in \mathbb{N}$.
3. $n^{'}\neq 0, \forall n$.
4. $n \neq m \Rightarrow n^{'} \neq m^{'}, \forall m, n \in \mathbb{N}$.
5. $\{P(0),P(n) \Rightarrow P(n^{'})\}\Rightarrow P(n), \forall n \in \mathbb{N}$



## Set-theoretic models

The Peano axioms can be derived from [set theoretic](https://en.wikipedia.org/wiki/Set_theory) constructions of the [natural numbers](https://en.wikipedia.org/wiki/Natural_number) and axioms of set theory such as the [ZF](https://en.wikipedia.org/wiki/Zermelo%E2%80%93Fraenkel_set_theory).

Define  $a^{'}\doteq a \cup\{a\}$.

1. $0 \doteq \{\}$
2. $1 \doteq 0 \cup \{0\} = \{\} \cup \{0\}=\{0\}$
3. $2 \doteq 1 \cup \{1\} = \{0\} \cup \{1\} = \{0,1\}$
4. $3 \doteq 2 \cup \{2\} = \{0,1\} \cup \{2\} = \{0,1,2\}$
5. $\cdots$
6. $\mathbb{N} \doteq \{0, 1, 2, 3,\cdots\} = \{0, \{0\}, \{0,1\}, \{0,1,2\} \}$

aha.

Define  $a^{'}\doteq a \cup\{a\}$.

1. $0 \doteq \Phi$
2. $1 \doteq 0\cup \{0\} = \Phi \cup \{\Phi\} = \{\Phi\}$
3. $2 \doteq 1 \cup \{1\} = \{\Phi\} \cup \{\{\Phi\}\} = \{\Phi,\{\Phi\}\}$
4. $3 \doteq 2 \cup \{2\} = \{\Phi,\{\Phi\}\} \cup \{\{\Phi,\{\Phi\}\}\} = \{\Phi,\{\Phi\},\{\Phi,\{\Phi\}\}\}$
5. $\cdots$
6. $\mathbb{N} \doteq \{0, 1, 2, 3, \cdots\}  = \{\Phi,  \{\Phi\}, \{ \Phi, \{\Phi\}\}, \{ \Phi,  \{\Phi\}, \{ \Phi, \{\Phi\}\}\},\cdots\}$

aha.

Define  $a^{'}\doteq \{a,e\}$.

1. $0 \doteq e$
2. $1 \doteq \{e\}$
3. $2 \doteq \{1,e\} = \{\{e\},e\}$
4. $3 \doteq \{2,e\} = \{\{\{e\},e\},e\}$
5. $\cdots$
6. $\mathbb{N} \doteq \{0, 1, 2, 3, \cdots\} = \{e, \{e\}, \{\{e\},e\}, \{\{\{e\},e\},e\} \} $

aha.

Define  $a^{'}\doteq \{e,a\}$.


1. $0 \doteq e$
2. $1 \doteq \{e\}$
3. $2 \doteq \{e,1\} = \{e,\{e\}\}$
4. $3 \doteq \{e,2\} = \{e, \{e,\{e\}\}\}$
5. $\cdots$
6. $\mathbb{N} \doteq \{0, 1, 2, 3, \cdots\} = \{e, \{e\}, \{e,\{e\}\}, \{e, \{e,\{e\}\}\}, \cdots \} $

# Peano algebra

## 加法定义
令 $m$ 和 $n$ 为自然数, 那么加法被定义为:
1. $0+m:=m$
2. $n^{'}+m:=(n+m)^{'}$

根据以上公理和定义，我们可以证明1+1=2如下：（这里为了方便分析，步骤会写得比较细）
证明：
1. 根据公理1和2，存在一个写作0++的自然数，并且因为公理3，所以0++≠0。 
2. 因为0++和0不同，所以我们可以用一个与符号“0”不同的符号“1”去表示（定义）0++，所以有1≠0。
3. 令m=1，根据加法定义的第1条，0+m=0+1=1。
4. 令n=0，根据加法定义的第2条，1+1=(0++)+1=(0+1)++，然后根据上一步的结果有1+1=(0+1)++=1++。
5. 根据公理3可知1+1=1++≠0。
6. 因为1≠0（第2步结果），根据公理4，可得1+1=1++≠0++=1，即1+1≠1。
7. 根据第5、6步，1+1既不等于0又不等于1，所以可以用一个与符号“0”和“1”都不同的符号“2”来表示，定义为1+1=2。

链接：<https://www.zhihu.com/question/55562202/answer/149149173>

