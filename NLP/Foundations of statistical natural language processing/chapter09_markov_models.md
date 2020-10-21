# Chapter 9: Markov Models

## 9.1. Markov Models

A sequence of random variables that aren't independent, the value of each variable depends on previous elements in the sequence. How far do we look?

A sequence fulfilling the stationarity and limited horizon is said to be a Markov chain, or to have the Markov property. A markov can also be represented by a state diagram. Markov models can be thought of as a nondeterministic finite state automaton with probabilities attached to each arc. In a visible MM, we know what states the machine is passing through.

Probabilities and formulas in p320

## 9.2. Hidden Markov Models

We assume that the MM starts in an initial state. In HMMs, we need to consider all paths that might be taken through the model, and then sum over them. 

We can use HMMs to represent the choice of whether to use the unigram, bigram or trigram probabilities.

## 9.3. The three fundamental questions for HMMs

1. Given a model, how to efficiently compute how likely a certain observation is?
2. Given the observation sequence and a model, how to choose a state sequence that best explains the observations?
3. Given an observation sequence and a space of possible models foud by varying the model parameters, how to find the model that best explains the observed data?

Solutions in p326-

Forward procedure, Trellis' algorithm, backward procedure, Viterbi algorithm
