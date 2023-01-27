

##### [Cache Design](https://github.com/vaughn-arctic/321_Notes/edit/main/321_notes.md#cache-design)
##### [I/O Techniques](https://github.com/vaughn-arctic/321_Notes/edit/main/321_notes.md#io-techniques-direct-memory-access)
##### [Lab 1 Q/As](https://github.com/vaughn-arctic/321_Notes/edit/main/321_notes.md#lab-1)


# 24 JAN
>Cognative  -----     Affectibe  -----   PSYCHOMOTOR!!!!<br />
>  L1 ------------- L1--------------              L1     (Basic Learning)<br>
>  L2.... (Comprehension)<br>
>  L3.... (Application)<br>
>  L4..... (Analysis)<br>
>  L5.....(Harder)<br>
>  L6.... (Creation).  Only humans can create<br>

## Research

Master Journal List.... 

Different options of submission
Willing to improve... we gone get published boi


# 26 JAN
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
### Cache Design

###### Main categories are
1. cache size
2. block size
3. mapping function <br>Direct Mapping <br> Associated Mapping <br> some other type (couldn't hear him) 
4. replecement algorithm <br> OS can't just remove data <br> Must keep all data active in tempory until application is closed <br> replacement algorithm deals with freeing up space (FIFO, FILO...etc) 
5. write policy <br>  - Considerations of updating changes across all memomry <br> - Write-through (update all memomery) <br> - write-back (temp change in the cache) <br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ~ sequential updates as needed
6. number of cache levels

#### I/O Techniques (Direct Memory Access) 
When the processor encounters an instruction relating to I/O, it executes that instrution by issuing a command to the correct I/O module

1. Progammed I/O <br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Processor periodigly checks the I/O module intil the instruction is complete  <br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;this seerly degrades performance level since I/O takes control and centrel processor is idle until I/O instruction completes <br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Processor must periodically check for completion flag, I/O doesn't communicate 
2. Interrupt-Driven I/O <br>
  - Processer issues I/O command and continues doing other work 
  - The I/o module will interrupt the processor when it is done
  - Processor executes data transfer than resumes previous process<br>
  - More effiecent than Programmed I/O since processor can remain at work, however load is on processer to transfer I/O data
3. Direct Memory Access (DMA) 
  - In previous 2 methods transfer rate is limited by process / processor becomes tied up with I/O
  - DMA perfomed by seperate module on the system bus or incorporated into I/O <br> 
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; MEM < - > CPU < - > I/O (OLD WAY)
  - Direct access transfers the entire block of data directly to and from memory without going through processor <br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Processor only involved in begging and end of transfer (Also runs slower when access to the system bus is required) 
<br><br>

#### Multiprocessor and Multicore
SMP is a stand alone computer system that: <br> 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; two or more similar processsers <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; share main memomry <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; share I/O device access <br> 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; All processors can perform same function

> Performance - Tasks can be done in parallel <br> 
> Availability - single failure does not stop<br>
> Scalability<br><br><br>

more than 1 core on a silicon die. also include L2 and L3 cache <br> 
QUESTIONS
1. Multicore processor (simple shit) 
2. Processor Main Mem, I/O module, System bus
3. instruction steps = fetch and request



### LAB 1 
> 1. Concerning the memory hierarchy, there is a trade-off among the three key characteristics: capacity, access time, and cost. What is the relationship between these three?
>They share a direct relationship, memory must be able to keep pace with access times while still remaining cost efficient
>
>2. What happens if a computer system only contains registers and main memory, but no cache? Justify your answer
>
>You really would not be able to execute anything as there would be nowhere to store the temporary data of the sub processes that comprise each large process. 
>The cache is what stages the transfer of data between the registers and main memory
>
>
>3. The replacement algorithm chooses (within the constraints of the mapping function) which block to replace when a new block is to be loaded into the cache and the cache already has all slots filled with other blocks. Suggest a strategy that has at least one advantage over the least-recently-used (LRU) algorithm. Justify your answer
>
>FIFO (First in First Out) While similar to the least recently used, this method would automatically remove older referenced blocks sequentially, removing the need for the hardware mechanisms required to identify LRU blocks
>
>4. Practice Problem:
>
>A computer has a cache, main memory, and a disk used for virtual Memory
>An access to the cache takes 10 ns
>An access to main memory takes 100 ns
>An access to the disk takes 10,000 ns
>Suppose the cache hit ratio is 0.9 and the main memory hit ratio is 0.8.
>What is the effective access time (EAT) in ns required to access a referenced word on this system?
>
>Cache time( hit rate)  + cache error rate(cache time + m/m time) + M/M error rate (cache time + M/M time + disk time) 
>
>10(0.9) + 0.1(10+100) + 0.2(10000+100+10) = 2042 ns 

