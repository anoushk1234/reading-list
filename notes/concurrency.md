# Concurrency in Rust

### 3 ways to go about it
- Fork Join Parallelism
- Shared Mutable State
- Channels

### Fork Join Parallelism
You can split up the task into chunks and run each chunk on a seperate thread. To fork means to start a new thread and to join is to wait for it to finish.

- easy to implement
- no shared state so no locks etc
- can speed up any cpu bound task even after thread results have to be aggregated once all threads have executed
- produces deterministic results although im not sure about how race conditions are handled

