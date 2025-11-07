***
**Compulsory**
* On first access to an object, you take a miss; there is little you can do about it

**Capacity**
* You are touching more data than can fit in the cache
* If your cache were larger, you would have fewer misses

**Conflict**
* In most caches, there only a limited number of places in the cache in which you can put a particular piece of data

#### Cache Design Decisions
**Blocksize/Linesize**
* The amount of data that should be returned
**Eviction and Replacement Policy**
* What to do I run out of space
**Cache Organization**
* What is in my cache
* Where do i put things in my cache

#### Writing
**Write-through:** writes go to cache _and_ main memory simultaneously → slower writes, but data is always consistent.  
**Write-back (write-behind):** writes only update cache initially, then write to memory later → faster, but risk of data loss on failure.
**Write-allocate:** on a write miss, the block is loaded into cache first, then written — common with write-back.
**No-write-allocate:** on a write miss, data is written directly to memory, not cached — common with write-through.

#### Anatomy of Addresses and Cache Lines
