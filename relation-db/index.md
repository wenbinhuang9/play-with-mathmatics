## Why index

Index is used to fasten query for performance improvement. Index is just like bookmark, which fastern query the specified page and content. 

## How many kinds of index

There are majorly two kinds of index, sequential sorted index and hash index.

Sequential sorted index can be implemented by tree structure, which support sorting. While hash index is very similar to hashtable, which is based on hash data structure


As for the other classification, there are sparse index and dense index.  Each search key will be shown in the index. While for the sparse index, only part of keys are shown in the index. 

There is a trade-off between space-efficiency and query performance for sparse index and dense index. 

## Index update 

We should maintain index when search key is updated. As updatation can be implicitely implemented by insertion and deletion, So I only talk about insertion and deletion.

### Insertion for dense index

- If the serach key not exists, just insert it
- If the search key exists,  why here has two condition, I can't understand here ? 


### insertion for sparse index 
Always focus on the first record of a block. 

When a first record of a block is updated. update to index.

When a new block is created, insert it to index. 

### deletion for dense index 

Just mark it to be deleted? 
 

### deletion for sparse index 
