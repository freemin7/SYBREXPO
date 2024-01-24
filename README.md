# SYBREXPO
SYnthetic BRanching EXecution POlicy - A sketch of a mathematical optimization software framework

SYBREXPO could converge against being an resource-use aware meta-optimizer service operating on algorithms for optimization and constraint satisfaction problems.

## Motivation

Some mathematical optimisation or constraint satisfaction problems have multiple equivalent formulations which can be solved by different approaches. Those transformations also take resources. It often requires human intervention to perform those transformation. Even worse sharing information between different formulations is often error prone or impossible. When running different algorithms using shared resources it is often very difficult to efficiently make use of those resources. To make good decisions optimzation algorithms need to be interruptable, transparent about their progress and be able to make prediction about their likely progress and their resource needs. To inform good heuristics data about execution need to be collected.

## Synthetic execution

Synthetic execution is a form of abstract interpretation which evaluates possible execution traces of multi-algorithms on a model of computation to gain insight on resource use and progress speed with algorithm specific heuristic informed by problem specific properties.

## Oversolving

There are many possible execution traces which could solve a mathematical problem. Oversolving is executing more traces than necessary to find an solution in order get a better sample of the behaviour of the search space of execution traces. Those traces can be used to inform heuristics for other problems or be used to verify results.
