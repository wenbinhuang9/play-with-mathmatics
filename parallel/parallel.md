## What is parallel 

Execute tasks concurrently to  fastern the time. 

## Why

We use the parallel to improve the time effciency.  So we can have parallel computing. 

## Where 

Time-sharing operating system, process is abstrated for time sharing system, so process is really a great abstraction. 

Multithreads computing is a kind of parallel.

Multicores computing is also a another kind of parallel. 

## Parallel programming model 

### Directed acyclic graph model  (DAG)

It is modeled by the graph theorem, DAG. 

DAG is a very simple and great model, can be simplily used for parallel computing. 

We can use graph to model the partial order of tasks.

And use topological sort to execute the task .

### Resource Pool model

When making the parallel computing, it is usual to new a thread pools to execute a bunch of tasks.

## Problems in parallel program. 

### Race condition 

Race condition is the most famous problem in the parallel .

What is the race condition problem ? The result in a shared memory is relying on the execution orders of processes. 

#### Solution for the race condition ?

Synchornization? But what is synchronization ?

Lock 

Optimisitic lock 

Pessimistic lock

### Cooperation between processes. 

When two processes cooperate together to finish a common goal. 

What's the cooperated mechanism?  Wait and notify !!!!! 


### Semaphore 

Semaphore is used for the use of pool resource synchronization. 


## Parallel architecture ? 

What is the parallel architecture ? 


## task oriented parallel architecture 

### tasks executed sequentially 

The tasks are executed sequentially. The ouput of the current task will be used as the input of next task.

### Tasks executed concurrently 

All tasks are independent, so they can be executed concurrently, this is the most simple parallel model 

### Fork-Join model 

Tasks are forked, and join in a point until all tasks are completed

### DAG

Directed acyclic graph is the most general model for tasks execution.  













