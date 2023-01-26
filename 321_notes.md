# 24 Jan

##### [Cache Design](https://github.com/vaughn-arctic/321_Notes/edit/main/321_notes.md#cache-design)
##### [I/O Techniques](https://github.com/vaughn-arctic/321_Notes/edit/main/321_notes.md#io-techniques-direct-memory-access)

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


