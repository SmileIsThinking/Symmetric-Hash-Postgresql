# Symmetric-Hash-Postgresql

Postgresql version: 8.1.7

Four files are modified to implement symmetric hash join to replace the hybrid hash join: 

In src/backend/executor/
{ nodeHashJoin.c: This file implements the hybrid hash join operator.
{ nodeHash.c: This file implements the hash operator, which builds a hash table. The existing
hybrid hash join operator expects its inner input to be a hash operator.


src/backend/optimizer/plan/
{ createplan.c: This file contains code the builds plans.


src/include/nodes/
{ execnodes.h: Contains the structure HashJoinState, which maintains the state of the hash join
during execution.


Only backend is included in this repo. However, it's easy to recontruct HashJoinState in execnodes.h after reading the modified source code.
