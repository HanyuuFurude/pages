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

## Language & syntax description

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
* Grammar Simplification
  * delete productions like $P\rightarrow P$
  * delete productions who can not be used in the derivations
  * delete productions who can not derive a terminal string
* Construct context-free grammar without ε-production
  * it should follow conditions as followings
    * If there is the production S→ε of the form in P, S should not appear in right-side of any production, where S is the start symbol of the grammar;
    * There are no other ε-productions in P
  * How to construct
    * $G=(V_N,V_T,P,S)\rightarrow G'=(V'_N,V'_T,P',S')$
    * find out all non-terminal symbols that can derive ε after some steps, and put them into the set $V_0$
    *   construct the P’s set of productions of G’ as following steps:
      1. If an symbol in $V_0$ appears in the right side of a production, change the production into two production respectively; put the new productions into P
      2. put the productions relating to the symbol into P’ except for ε-production relating to the symbol
      3. if there exists the production of the form $S\rightarrow \epsilon$ in P,change the production into $S’\rightarrow \epsilon |S$ and put them into  $P’$,let $S’$ be the start symbol of $G’$, let $V’_N=V_N\cup \{S'\}$
* Syntax tree and ambiguity of a grammar
  * Basic terms in a syntax tree
    * Sub-tree
    * Pruning sub-tree
    * Sentential form

# Chapter 3 Lexical analysis

## Approaches to implement a lexical analyzer

* Simple approach

  * Construct a diagram that illustrates the structure of the tokens of the source language , and then to hand-translate the diagram into a program for finding tokens

    >  Efficient lexical analyzers can be produced in this manner

* Pattern-directed programming approach

  * Pattern Matching technique

  * Specify and design program that execute actions triggered by patterns in strings

  * Introduce a pattern-action language called Lex for specifying lexical analyzers

    - Patterns are specified by regular expressions
- A compiler for Lex can generate an efficient finite automation recognizer for the regular expressions
  
* First phase of a compiler

  1. Main task

     * To read the input characters 
     * To produce a sequence of tokens used by the parser for syntax analysis
     * As an assistant of parser

  2. Interaction of lexical analyzer with parser

     ![image-20191112003646409](/CompilationPrinciple/image-20191112003646409.png)

     

3. 、Processes in lexical analyzers

   *　Scanning
     *　Pre-processing
       * Strip out comments and white space
       * Macro functions
   *　Correlating error messages from compiler with source program
     *　A line number can be associated with an error message
   *　Lexical analysis

4. Terms of the lexical analyzer

   1. Token 
      * Types of words in source program
      * Keywords, operators, identifiers, constants, literal strings, punctuation symbols(such as commas,semicolons)
   2. Lexeme
      1. Actual words in source program
   3. Pattern
      1. A rule describing the set of lexemes that can represent a particular token in source program
      2. **Relation** {<.<=,>,>=,==,<>}

5. Attributes for Token

   1. A pointer to the symbol-table entry in which the information about the token is kept

   >  E.g E=M*C**2

    <**id**, pointer to symbol-table entry for E>

    <**assign_op**,>

   <**id**, pointer to symbol-table entry for M>

   <**multi_op**,>

   <**id**, pointer to symbol-table entry for C>

   <**exp_op**,>

   <**num**,integer value 2>
   
6. Lexical Errors

    *   Deleting an extraneous character
    *   Inserting a missing character
    *   Replacing an incorrect character by a correct character
    *   Transposing two adjacent characters(such as , fi=>if)
    *   Pre-scanning 

7.  Input Buffering
    *   Two-buffer input scheme to look ahead on the input and identify tokens
    *   Buffer pairs
    *   Sentinels(Guards)

🚧under construction🚧
