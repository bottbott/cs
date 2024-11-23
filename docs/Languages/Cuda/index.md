## Cuda API

CudaMalloc

- takes a pointer to a pointer of memory and the size of the memory to allocate. In the code that we got originally it was cast from something** to void**. But I came across some online threads talking about not needing to do that in modern CUDA.
  CudaMemcpy
  CudaFree

## cudagdb commands

## Topics

### cpu vs gpu

The biggest difference that we have is the number of processing units where calculations can be performed and the layout of memory. A modern CPU is more advanced than it's predecessors and has more than one core, but no large amount as it is designed for general purpose, but a GPU has thousands of cores and is designed for performing many parallel computations/instructions.

Memory in the CPU is laid out as a cache hierarchy with a few caches. The GPU has a global memory and then shared memory that is shared between threads in a block. There is shared memory that is assigned to each streaming multiprocessor and it is logically subdivided into shared memory for each block.

### gpu architecture

#### Streaming Multiprocessor (SM)

##### Processing Unit

A streaming multi processor has multiple streaming processing units that share control logic and an instruction cache. Each processing unit handles a thread, and the thread can handle a single point of data.

##### Shared Memory

Eac of the Streaming Multiprocessor units has memory that is assigned to it, and of that memory it is shared between the threads of a block, but not between blocks. The shared memory is faster than the global memory, but is limited in size.

### Global Memory

The global memory is the largest memory and is shared between all the streaming multiprocessors. It is the slowest memory.

### Threads

A thread is the smallest unit of execution. Threads are executed on a processing unit in the streaming multiprocessor. Threads are grouped into blocks. Each block shares memory and those threads can communicate with each other via this shared memory.

## Blocks

A block is a collection of threads. It may be 1,2,3d in dimension. The dimensions tend to correspond to the dimensions of the data that is being processed. A streaming multiprocessor has a maximum number of blocks it may be assigned, and the blocks may be distributed between the SMs at a number up to the maximum number of blocks that may be assigned to the SM.

## Grid

A grid is connected to the kernel. It specifies a 1,2,3d dimension of blocks. It specifies a corresponding logical region in the GPU where the threads will be executed.

## Warp

Warps are another logical subdividing of threads AFTER a block has been assigned to a streaming multiprocessor. Typically the number of streaming processors is less than the number of threads in a block, so the threads are divided into warps. The threads in a warp are executed in lockstep.

This was a point of confusion because I had imagined that as soon as a block was assigned to a streaming multiprocessor that they would all be executed together, but they aren't. They are divided into warps and executed depending on the GPU implementation. Some GPUs can process more than one warp at a time.

This discrepancy allows for time to latency to be hidden since there is some delay in processing each of the warps. Accesses to global memory can be mitigated since only some of the warps are processed at a time out of the block.
