---
title: 编译原理小结
date: 2019-10-07 00:00:00
tags:
	- compilation principle
	- course
categories:
	- course
---
[TOC]
# Chapter 1

>   None

# Chapter 2 Language & Syntax Description

## Grammar & Language

>   1.  Alphabet
>
>     Non-empty set of symbols，usually expressed in $\Sigma$、$V$ or Other Upper-case Greece Letter
>
>   2.  Symbol (Character)
>
>     Elements in alphabet, finest elements in a language
>
>   3.  String
>
>     Finite sequence of symbols in the Alphabet.
>
>     Notes: Null-string is string without any symbol, written as e。
>
>   > 1. A = {$\alpha_1$,$\alpha_2$,…} B ={$\beta_1$,$\beta_2$}
>   >
>   >    AB = $\{\alpha\beta|\alpha\in A\ and\ \beta \in B\}$
>   >
>   >    $A^0=\{\epsilon\}$
>   >
>   > 2. Closure
>   >
>   >    $A^*=A^0\cup A^1\cup A^2...$
>   >
>   > 3. Positive closure
>   >
>   >    $A^+=A^1\cup A^2 \cup A^3...$
>
>   4.  Sentence
>
>      A set of strings based on symbols in the Alphabet in  certain construction rules
>
>   5.  Language
>
>      Sets of sentences in the Alphabet.
>
>      Notes: By convention, a symbol is expressed as a,b,c,…；a string is expressed as $\alpha$,$\beta$,$\gamma$…；a set of strings is expressed in A,B,C….

* Grammar
  * Grammar(G)
  * None-terminal symbol($V_N$)
  * Terminal symbol($V_T$)
  * Start symbol(S)
  * Production(P)
    * <Sentence>→<subject><Predicate>
    * $A\rightarrow \alpha$
  * Derivation(Leftmost & Rightmost)
  * Reduction
  * Sentential form,  Sentence & Language
  * Recursive definition of grammar rules
  * Extended notations of grammar rules
* Formal definition
  * Grammar
    * **quadruple** ($V_N,V_T,P,S$)
  * Catalog of grammars
    * 0-type grammar (Phrase grammar or grammar without limitation)
      * to any production $\alpha\rightarrow\beta$ in P $(\alpha\in V^+,\beta\in V^*)$ ,there is at least  a non-terminal symbol in $\alpha$
    * 1-type grammar (context-sensitive grammar or length-added grammar)
      * to any production $\alpha\rightarrow\beta$ in P, there is the limitation of $|\beta|\ge|\alpha|$ **expect for $S\rightarrow\epsilon$,if $S\rightarrow\epsilon$, S can not appear in the right side for any production.
      * for any production $\alpha\rightarrow\beta$ in P, $\alpha A\beta\rightarrow\alpha\gamma\beta\ (\alpha,\beta\in V^*)$ expect for $S\rightarrow\epsilon$
    * 2-type grammar (context-free grammar)
      * Every production in P is of the form $A\rightarrow\beta$ where $A\in V_N,\beta\in V^*$
    * 3-type grammar (Regular grammar, right-linear grammar or left-linear grammar)
      * Every production in P is of the form $A\rightarrow\alpha B,A\rightarrow\alpha$, or $A\rightarrow B\alpha$,$A\rightarrow\alpha$,where $A$,$B\in V_N,\alpha\in V_T^*$

🚧under construction🚧
