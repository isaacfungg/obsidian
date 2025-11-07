***
#### Misses
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
**Write-through:**
* Writes go to cache _and_ main memory simultaneously → slower writes, but data is always consistent.  
* Hits
	* Data is written to both cache and the source
	* Latency = latency to write data source (parallel)
**Write-back (write-behind):**
* Writes only update cache initially, then write to memory later → faster, but risk of data loss on failure.
* Hits:
	* Data is written only to the cache
	* Dirty bit in the cache line is set to 1
	* Latency = latency to write to the cache
**Write-allocate:** 
* On a write miss, the block is loaded into cache first, then written — common with write-back.
* Miss:
	* Acts like a read miss; read cache line from the source into the cache
**No-write-allocate:** 
* On a write miss, data is written directly to memory, not cached — common with write-through.
* Miss:
	* Data is written to the source
	* Cache is checked but unchanged

#### Strided Access


#### Anatomy of Addresses and Cache Lines
**Address**
* Offset
	* Selects starting byte in a cache line
	* #' bits = log2 (cache line size)
* Index
	* Selects a cache set
	* #' bits = log2 (# sets in the cache)
* Tag
	* Identifies line in a set using associative lookup
	* #' bits = Everything left in address

**Cache Lines**
* Valid bit
	* 1 iff line contains valid date
	* 0 if none of the other data/metadata is useful
* Tag:
	* Used to determine precisely which address is stored in a cache line
	* For a hit, the tag bits in the address must match the tag bits in a slot's metadata in the set indicated by the address's index bits
* Dirty Bit:
	* 1 iff line contains dirty data (Writeback only)