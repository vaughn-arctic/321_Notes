

##### [Cache Design](https://github.com/vaughn-arctic/321_Notes/edit/main/321_notes.md#cache-design)
##### [I/O Techniques](https://github.com/vaughn-arctic/321_Notes/edit/main/321_notes.md#io-techniques-direct-memory-access)
##### [Lab 1 Q/As](https://github.com/vaughn-arctic/321_Notes/edit/main/321_notes.md#lab-1)
##### [OS Objectives](https://github.com/vaughn-arctic/321_Notes/edit/main/321_notes.md#operating-systems-objectives-and-functions)
##### [Process Description and control](https://github.com/vaughn-arctic/321_Notes/edit/main/321_notes.md#process-description-and-control)


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


# Jan 31

##### Lab 1 answers
>!. Faster access time, greater cost per bit, 
Greater capacity, smaller cost per bit, 
Greater capacity, slower access speed<br>
>2. That is because the processor will be waiting every time it wants to access the main memory as it is slower than the processor.<br>
>3... Correct <br>
>4. EAT = 0.9 (10) + 0.1 [ 0.8 (10 + 100) + 0.2 (10 + 100 + 10000) ]<br>
> ............         success     fail [ success() + fail() ] <br>
> OR EAT = 10 + 0.1 (100) + 0.02 (10000) = 220ns<br>
> .......baseline + chance of failure (time cost) <br>

###practice 0.9(10) + .1( 0.85( 10 + 50) + 0.15 ( 0.8 ( 10 + 50 + 100) + 0.2 ( 10 + 50 + 100 +10000 ) ) ) ) 

update group project [here](https://docs.google.com/spreadsheets/d/1wK4asShsy8apOGWDbOScW8pcrbp3Z7oG4v_p8f99yYk/edit?usp=sharing)

### Operating Systems Objectives and Functions
- program the controls execution
- interface between application and hardware
-  convenience, efficiency, ability to evolve (scalability) 

Provided services
1. program development
2. program execution 
3. access i/o devices
4. file/system access
5. error detection

<img width="749" alt="image" src="https://user-images.githubusercontent.com/70354960/215863741-5ca28cdc-f73c-4c40-92c0-5a293630447e.png">

#### Key interfaces
API - sharing data at the user
>defines access in source code at high level

ABI - Binary - 
>defines how data structures are accessed at low level 

ISA - Instruction set architecture

#### Resource  management
>Takes place in main memory. Includes the kernel and other portions of the OS. Responsible for controlling computer's resources: I/O, memory, process execution

### Evolution of OS
- Hardware upgrades
- New types of hardware
- new services
- Fixes

test | table
-- | -- 
fuck | me

four stages
1. Serial Procssing
  - no poerating systmes... direct infterface with hardware
  - physical queue in to conduct processes
  - do one task then the next
2. simple bash systems
  - maximize processer utilization
  - uses a monitor (software for scheduling jobs) 
  - submits instructions to computer operator who batches jobs sequentially
    - operator submits entire batch (of jobs) on input device to monitor
  - Each program is constructed to branch back to the monitor when it completes processing
    - at this point monitor begins next program
  - results of each job sent to output device
  - User mode
    - user program exucutes in user mode
    - certain areas of memory are protected from user access
    - certain instructions may not be executured
  - Kernel mode (main kernel)
    - Privlidge instructions
    - essentially sysadmin
3. Multiprogrammed Batch Systems
  - Processor often idle in simple batch
    - sequentional instructions cause lot of idle time in between jobs
  - Allow processor to be switch between the various programs/jobs in its memory while waiting for another program
  - Still only runs 1 process at a time 
  - ![image align = "center"](https://user-images.githubusercontent.com/70354960/215867217-74ad2962-fcd9-4c86-9c00-b191d04d58ec.png)
4. Time sharing systems
  - Multiprograming can be used to handle multiple interactive jobs, "Time Sharing" processor time is shared among users
  - Multiple users simultaneously access the system through terminals, the OS interleaving the execution of each user program in short bursts
  - Time Slicing
    - Clock interuppts at intervals, the OS regains control and can assign the process to another user
    - Thus at regular time intervals, the current user would be blocked and another user loaded in
    - <img width="850" alt="image" align = "center" src="https://user-images.githubusercontent.com/70354960/215868338-0d5a573c-0060-4631-a14b-f21942daf202.png">

### Major Achievements
+ Processes
  + Another word for job
  + > a program in execution, instance of a program running on a computer
  + entitiy can be assigned to and executed on a processor
  + unit of activity - a sequential thread of execution, current state or associated set of system resources (Ram allocation, hardware uses, etc.) 
+ Process Components
  + executable program, associated data needed by the program, execution context of the program
  + "Context" includes all info the OS needs to manage and execute the process (priority, waiting for I/O even) 
  + <img width="371" alt="image" align="center" src="https://user-images.githubusercontent.com/70354960/215869584-98020525-dba4-46d3-a33e-2f79e9cd8562.png">
+ Memory management
  + proces isolation
  + automatic allocation and management
  + suport of modular programming 
  + Protection/Access control
  + Long term storage
  + >Typically OS meet these requirments with birtual memomry and file system facilities
+ information protection and security
+ scheduling resource management

# Feb 7 

### Process description and control

#### what is a process
- progam in execution 
- instance of program running on a computer
- entity can be assigned and executed on a processor
- unit of activity
  - current state
  
>The OS must interleave the execution of multiple processess, to maximize processor utilization while providing reasonable response time

> The OS must allocate resources to processes in accordance with a specific policy while at the same time avoiding deadlock
>  - policy is user defined

#### essential elements of a process
- codes
- data
- process control block (PCB)
  - created by the OS
  - used to track execution status
  - key to that allows support for multiprogramming, timesharing etcs

#### Looking at Process Control Block (PCB) 

- identifier
  - a unique ID
- state
  - running state, waiting state, termingating, etc.... 
- priority
  - importance level in order of processing 
- program counter
  - points to the address of the next instruction to be executed
- mem pointer
  - points to code and data associated with the process
- context data
  - data present in the regesiters in the processor while executing 
- I/O status info
  - oustatning I/O requests, I/O devices (disk drives) 
- accounting info
  - may include processor time and clock time used

> it is possible to nitterupt a process and resume execuition later
> The process control block is the keel tool that enables OS to support multiprogramming and to provide for multiprocessing

#### process states

1. Two state process model 
  - process the control block between running - not running
  - The que is a FIFO list, 
    - each process in the que is given a certain amount of time in turn to execute, then returns to the end of the queue
2. 5-state process model 
  * running
    - process currently being exectuire
  * ready
    - process prepared to execute when given the oppurtuntiy
  * blocked/waiting
    - cannot execute until some even occurs
  * new
    - just been created and not addmitted to the executable pool 
  * exit
    - released from the executable pool
<br>

#### Process description

Fundamentally we can think of the OS as the -> entity that manages the use of system resousreces by process

#### OS INfotrmation
- constructions and maintains info about each entity it manages
- 4 types 
  - memoery
    - used to keep track of main and virtual memory
    - processes are mainted on the virtual memomry or simple swapping mechanismw
  - i/o devices
    - used by OS to mangage I?O devices
    - at any time I/O devices may be aailabe or assigned to a particular processesw 
    - needs to know status of I/O
  - file
    - existence and location of files
    - current states
  - process 
    - process location : need for suffiecent memory on the stack
    - process attributes


#### Process Control Structures
> collection of program, data, stack, and attriburs is called the proccess image

The process image<br>
- a great deal of info about each process
- each process is assigned a uniquq ID
- process statw inforamtion
- process controll information 

#### Linux Process ID
> each process in linux is has a unique id -> PID <br>
> arranged as a tree where parent processes are ppid<br>
> getpid() getppid() = systemcalls
>   - these need headers to operatio
>   - #include<stdio.h>
> 


# COMMMITT YOUR CHANGES !!!!!
# FEB 21
###
Notes for these are in lab tutorial <br>
code is in the ubuntu multipass home directory
