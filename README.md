Bailey-MiniSAT

A modification of (the MapleSAT derivative of) MiniSAT to allow deeper clause inspection and new heuristics.

I wanted a better heuristic for how much extra learned structure setting a given variable was likely to produce, as well as whether we should assign it true or false in our search.

State of the art SAT solvers like MiniSAT and MapleSAT "watch" only 2 literals in each clause, so that on a typical update most clauses don't have to be inspected. 2 literals are all that's required to ensure "unit propagation" occurs properly. However, by expanding the watch to 3 literals per clause, I was able to produce statistics about how many propagations a given variable assignment is expected to produce, as well as a rough "probability (truth) estimate" for the variables before they're set.